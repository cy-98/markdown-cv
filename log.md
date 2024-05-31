数值格式化

1. 需要处理本地化数字格式化
2. 需要处理本地化紧凑记数法
3. 需要处理本地化货币符号

国际化标准：
浏览器 API Intl 实现符合 ECAM-402 标准，15.2.3 章节中规定各国家本地化符号实现需要符合 CLDR 本地化标准。

CLDR 本地化标准：
CLDR 是由 Unicode Consoritum 维护的官方开源项目，旨在为软件开发者提供全球化和本地化所需的语言和地区数据，包括日期、时间、货币、数字、单位、名称等方面的信息
CLDR 中规定了本地化的各个符号在 unicode 中的编码规则，可以在 By-Type 章节中通过分类来查看各个符号以及其他本地化表示形式。
[图片]

TL;DR
@formatjs/intl 和 numeral 符合 ECAM-402 标准。
@formatjs/number-format 的 api 使用与浏览器一致，Lynx 环境不支持安装所需的 polyfill。numeral 包体更小，Lynx 环境可以稳定运行。

Lynx 不支持 Intl.numberFormat 以及 Number.toLocaleString 方法
有很多符合标准的第三方库可以用于实现 Intl.NumberFormat 的功能，以下是一些常用的库及其优缺点：

1. @formatjs/number-format 它提供了 ECMA-402 规范所定义的各种国际化 API，包括日期格式化、数字格式化、货币格式化、排序等等。该库的优点是符合标准，并且在浏览器和 Node.js 中都可以使用。缺点是库的大小比较大，需要引入多个 polyfill 来支持缺少 ECMA-402 规范的环境。
   @formatjs 的所有 polyfill 都依赖全局变量的 Intl 方法，目前 Lynx 环境引入 Polyfill 的初始化工作因缺失 Intl 变量导致失败。
   // polyfills
   "intl": "1.2.5", // 40.2KB
   "@formatjs/intl-numberformat": "8.7.0", // 49.4KB
   "@formatjs/intl-getcanonicallocales": "2.2.1", // 64.4KB
   "@formatjs/intl-pluralrules": "5.2.4", // 48KB
   "@formatjs/intl-locale": "3.3.2" // 172.9KB
2. format-number 库：该库是一个小巧的 JavaScript 库，用于格式化数字。它支持多种数字格式化选项，包括小数位数、千位分隔符、货币符号以及紧凑记数法等等。该库的优点是体积小，可以在浏览器和 Node.js 中使用。支持 ECMA-402 规范。
   const formatNumber = require('format-number');
   const number = 1234567890;
   // 美元格式化
   const usFormatter = formatNumber({
   locale: 'en-US',
   style: 'currency',
   currency: 'USD',
   compact: 'short',
   });
3. numeral.js 该库是一个用于格式化和操作数字的 JavaScript 库。它支持多种数字格式化选项，包括前缀、后缀、小数位数、千位分隔符、舍入方式等等。该库的优点是灵活性高，可以自定义格式化选项。缺点是没有 ECMA-402 规范的支持，因此可能会在某些环境下产生细微的差异。
   const numeral = require('numeral');
   const number = 1234567890;
   // 美元格式化
   numeral.register('locale', 'en', {
   delimiters: {
   thousands: ',',
   decimal: '.',
   },
   abbreviations: {
   thousand: 'K',
   million: 'M',
   billion: 'B',
   trillion: 'T',
   },
   currency: {
   symbol: '$',
   },
   });
4. currency.js,包体积偏大，重点处理货币格式化。API 简洁易于使用，支持货币数值复杂计算。
   const currency = require('currency.js');
   const amount = 123456789;
   const formatted = currency(amount, {
   symbol: '$',
   precision: 2,
   pattern: '!#',
   formatWithSymbol: true,
   useGrouping: true,
   increment: 1,
   useVedic: false,
   separator: ',',
   decimal: '.',
   errorOnInvalid: false,
   precisionMode: currency.precisionModes.HALF_UP,
   symbolPosition: currency.symbolPositions.START,
   negativePattern: '-!#'
   }).format(); // 使用默认选项进行本地化紧凑记数和格式化
   console.log(formatted); // 输出：$123.46M（在使用 "M" 作为数量级符号的情况下）

结论：

- @formatjs/number-format 能够按照 ECAM 标准解决格式化问题，支持数值分隔、紧凑记数、货币符号处理，与浏览器 api 使用一致，符合 CLDR 最新标准。
  - 支持数字格式化、紧凑记数、货币格式化
  - 支持本地化；符合 CLDR 标准
  - Weekly downloads: 386,531
- numeral.js 提供包括全球大部分主要语言和地区本地，支持数值分隔、紧凑记数、货币符号处理。但是需要手动声明展示前缀还是后缀。
  - 支持数字格式化、紧凑记数、货币格式化
  - 支持本地化；符合 CLDR 标准，但是由于版本原因可能与最新标准有些差异
  - 支持自定义和覆盖本地化标准
  - Size: 11kB
  - Weekly downloads: 1095,406
- format-number 需要手动注册本地化配置，包体非常小。
  - 不支持本地化；
  - 不支持紧凑记数；支持数字格式化、货币格式化
  - Size: 3.2kB
  - Weekly downloads: 26,060
- currency.js 不支持紧凑记数，比较好的支持本地化货币格式化和数量级分隔符。
  - 支持本地化
  - 不支持紧凑计数；支持数字格式化、货币格式化；
  - Size：36.2kB
  - Weekly downloads: 214,794

src/common/utils/number_format.ts
const getAssetsFormatFn =
(type: 'cash' | 'point' | undefined, currencySymbol: string = '', currencyUnit: string = '') =>
(
value?: number | string,
bigValueFormat?: boolean,
precision?: number,
): {
amount: string;
full: string;
cash: string;
} => {
const lang = getUserLanguage();
let countString = ' - ';
if (value !== undefined && value !== null && !Number.isNaN(Number(value))) {
const valueNum = Number(value);
const count = type === 'cash' ? valueNum / 100 : valueNum;
countString = count.toLocaleString(`${lang}-u-nu-latn`);
if (bigValueFormat && typeof Intl !== 'undefined') {
countString = new Intl.NumberFormat(`${lang}-u-nu-latn`, {
notation: 'compact',
maximumFractionDigits: precision ?? 1,
}).format(valueNum);
}
}
return {
amount: countString,
cash: currencySymbol ? currencySymbol + countString : countString + currencyUnit,
full: type === 'cash' ? currencySymbol + countString + currencyUnit : countString,
};
};
