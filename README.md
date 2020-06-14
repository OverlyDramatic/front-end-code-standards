# 前端代码规范

## 1. 前言

编写 WEB 前端编程规范的目的是为了统一产品在开发过程中的编码风格，以便于代码阅读和后期维护。本规范规定了使用 WEB 前端语言开发过程中的命名、注释、排版编码规则及 Web 前端项目开发中的编码规则。

### 1.1. 术语

规范：编程时强制必须遵守的原则。
建议：编程时必须加以参考的原则。
强制：编程时对规范的遵守程度。
实例：对此规范或建议给出的正或反方面的实际例子。
错误：不符合规范的编码方式。

## 2. 命名规范

### 2.1. 文件命名规范

文件命名遵循以下原则：

- .js、.ts 文件 统一使用驼峰命名法(camelCase)
  - 如：main.js、helloWorld.ts
- .css 等样式文件 统一使用短横线命名法(kebab-case)
  - 如：reset.css、hello-world.less
- .vue 文件 统一使用帕斯卡命名法(PascalCase)
  - 如：App.vue、HelloWorld.vue

### 2.2. js 内部命名规范

#### 2.2.1. 常量命名规范

常量名统一全部大写，单词间用下划线分隔，如：

```js
const INTERVAL = 20
const LIMIT_TIME = 30000

```

#### 2.2.2. 变量命名规范

变量名统一使用驼峰命名法(camelCase)，如：

```js
var time = 60
let helloWorld = "hello world! "

```

!!!注意!!! 私有变量名以下划线\_开头，如：

```js
var _tempData = []
let _defaultConfig = {}

```

#### 2.2.3. 函数命名规范

方法的命名一般采用动宾短语组成，即很好的表达出动作行为，让其他人在阅读代码时能够看到方法名称即可清晰的知道该方法处理的业务逻辑是什么。不可采用没有含义的单词或词组作为方法名称。方法命名采用小写字母开头，字母之间采用标准的驼峰式命名规范。方法名长度一般不超过 20 个字符，如果需要表达清楚含义，词组长度很长的时候，我们规定采用对部分单词简写拼接的方式组成方法名称，这样既能很好的表达出方法的含义，也能不至于方法名称过长造成阅读困难。

!!!强制!!! 方法命名方式：动作/行为 + 业务名称

函数统一使用驼峰命名法(camelCase)，如：

```js
function driveTheCar() {
  return "drive the car"
}

```

!!!建议!!! 后端提供的接口以 RESTful API 规范命名，因此建议前端发送 http 请求的 api 函数的命名方式：请求方法 + 业务名称，如：

```js
// 后端接口 get /userInfo
function getUserInfo() {
  doSomeThing()
}
// 后端接口 post /userInfo
function postUserInfo() {
  doSomeThing()
}
// 后端接口 put /userInfo
function putUserInfo() {
  doSomeThing()
}
// 后端接口 delete /userInfo
function deleteUserInfo() {
  doSomeThing()
}

```

## 3. 注释规范

注释的作用有两种，一种是屏蔽不需要执行的代码，一种是对代码进行解释说明。注释分为单行注释和多行注释。

### 3.1. 注释的重要性

注释在我们编写代码时虽然对我们的代码业务逻辑的执行没有任何的帮助，但却是我们在编码过程中不可缺少的一部分。一般情况下，注释占源程序的30%以上。其作用主要是通过注释提高源程序代码的可读性；使得程序条理清晰，易于区分代码行与注释行，方便后来的维护以及程序员的交流。

### 3.2. 注释风格

#### 3.2.1. 单行注释

- 双斜线后，必须跟一个空格
- 缩进与下一行代码保持一致
- 可位于一个代码行的末尾，与代码间隔一个空格

如：

```js
// 一个新函数
function fooBar() {
  // 功能代码
  doSomeThing()
}

```

#### 3.2.2. 多行注释

建议在以下情况下使用：
- 难于理解的代码段
- 可能存在错误的代码段
- 浏览器特殊的HACK代码
- 业务逻辑强相关的代码

其中，注释内容与*以一个空格分隔，如：

```js
/*
 * one space after '*'
 */
var x = 1;

```

#### 3.2.3. 文档注释

各类标签@param, @method等请参考usejsdoc和JSDoc Guide
建议在以下情况下使用：

- 所有常量
- 所有函数
- 所有类实例

如：

```js
/**
 * @func
 * @desc 一个带参数的函数
 * @param {string} a - 参数a
 * @param {number} b=1 - 参数b默认值为1
 * @param {string} c=1 - 参数c有两种支持的取值</br>1—表示x</br>2—表示xx
 * @param {object} d - 参数d为一个对象
 * @param {string} d.e - 参数d的e属性
 * @param {string} d.f - 参数d的f属性
 * @param {object[]} g - 参数g为一个对象数组
 * @param {string} g.h - 参数g数组中一项的h属性
 * @param {string} g.i - 参数g数组中一项的i属性
 * @param {string} [j] - 参数j是一个可选参数
 */
function foo(a, b, c, d, g, j) {
  doSomeThing()
}

```

## 4. 排版及编码规范

### 4.1. 统一编码格式

!!!强制!!! 为了防止代码在不同的编译器或导入其他人编写的代码出现中文乱码问题，我们对编码格式做统一规范，统一采用UTF-8 的编码格式。

## 5. 编程中应该注意的问题
