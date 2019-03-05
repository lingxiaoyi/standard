# JavaScript编码规范

**[VsCode 开发环境配置规范](./vscode_eslint_prettier.md)**

本规范主要参考[standardjs](https://standardjs.com/)的[rules](https://standardjs.com/rules-zhcn.html)再整合我们前端团队的一些开发习惯（自定义rules）而定制，前端开发人员必须遵守此规范进行JavaScript代码的编写。

掌握本规范的最好方法是安装（参考：[Eslint配置规范](./eslint_standard_rules.md)）并在自己的代码中使用它。

## 细则
### 1、使用4个空格进行缩进。【非强制】（保证同一个项目风格统一即可）
eslint: [indent](http://eslint.org/docs/rules/indent)
```javascript
// 4个空格
function hello (name) {
    console.log('hi', name);
}
```
### 2、除需要转义的情况外，字符串统一使用单引号。
eslint: [quotes](http://eslint.org/docs/rules/quotes)
```javascript
console.log('hello there');
$("<div class='box'>");
```
### 3、不要定义未使用的变量。
eslint: [no-unused-vars](http://eslint.org/docs/rules/no-unused-vars)
```javascript
function myFunction () {
    var result = something();   // ✗ avoid 
}
```
### 4、关键字后面加空格。
eslint: [keyword-spacing](http://eslint.org/docs/rules/keyword-spacing)
```javascript
if (condition) { ... }   // ✓ ok 
if(condition) { ... }    // ✗ avoid 
```
### 5、函数声明时括号与函数名间加空格。【非强制】
eslint: [space-before-function-paren](http://eslint.org/docs/rules/space-before-function-paren)
```javascript
if (condition) { ... }   // ✓ ok 
if(condition) { ... }    // ✗ avoid 
```
### 5、始终使用 === 替代 ==。
例外： `obj == null` 可以用来检查 null || undefined。

eslint: [eqeqeq](http://eslint.org/docs/rules/eqeqeq)
```javascript
if (name === 'John');   // ✓ ok 
if (name == 'John');    // ✗ avoid 
if (name !== 'John');   // ✓ ok 
if (name != 'John');    // ✗ avoid 
```
### 6、字符串拼接操作符 (Infix operators) 之间要留空格。
eslint: [space-infix-ops](http://eslint.org/docs/rules/space-infix-ops)
```javascript
// ✓ ok 
var x = 2;
var message = 'hello, ' + name + '!';
// ✗ avoid 
var x=2;
var message = 'hello, '+name+'!';
```
### 7、逗号后面加空格。
eslint: [comma-spacing](http://eslint.org/docs/rules/comma-spacing)
```javascript
// ✓ ok 
var list = [1, 2, 3, 4];
function greet (name, options) { ... }
// ✗ avoid 
var list = [1,2,3,4];
function greet (name,options) { ... }
```
### 8、else 关键字要与花括号保持在同一行。
eslint: [brace-style](http://eslint.org/docs/rules/brace-style)
```javascript
// ✓ ok 
if (condition) {
  // ... 
} else {
  // ... 
}
// ✗ avoid 
if (condition) {
  // ... 
}
else {
  // ... 
}
```
### 9、多行 if 语句的的括号不能省。
eslint: [curly](http://eslint.org/docs/rules/curly)
```javascript
// ✓ ok 
if (options.quiet !== true) console.log('done');
// ✓ ok 
if (options.quiet !== true) {
    console.log('done');
}
// ✗ avoid 
if (options.quiet !== true)
    console.log('done');
```
### 10、不要丢掉异常处理中err参数。
eslint: [handle-callback-err](http://eslint.org/docs/rules/handle-callback-err)
```javascript
// ✓ ok 
run(function (err) {
    if (err) {
        throw err;
    }
    window.alert('done');
})
// ✗ avoid 
run(function (err) {
    window.alert('done');
})
```
### 11、使用浏览器全局变量时加上 window. 前缀。
例外: `document`, `console` 和 `navigator`

eslint: [no-undef](http://eslint.org/docs/rules/no-undef)
```javascript
window.alert('hi');   // ✓ ok 
```
### 12、不允许有连续多行空行。
eslint: [no-multiple-empty-lines](http://eslint.org/docs/rules/no-multiple-empty-lines)
```javascript
// ✓ ok 
var value = 'hello world';
console.log(value);
// ✗ avoid 
var value = 'hello world';
 
 
console.log(value);
```
### 13、对于三元运算符 ? 和 : 与他们所负责的代码处于同一行
eslint: [operator-linebreak](http://eslint.org/docs/rules/operator-linebreak)
```javascript
// ✓ ok 
var location = env.development ? 'localhost' : 'www.api.com';
 
// ✓ ok 
var location = env.development
    ? 'localhost'
    : 'www.api.com';
 
// ✗ avoid 
var location = env.development ?
    'localhost' :
    'www.api.com';
```
### 14、每个 var 关键字单独声明一个变量。【warn】
eslint: [one-var](http://eslint.org/docs/rules/one-var)
```javascript
// ✓ ok 
var silent = true;
var verbose = true;
 
// ✗ avoid 
var silent = true, verbose = true;
 
// ✗ avoid 
var silent = true,
    verbose = true;
```
### 15、条件语句中赋值语句使用括号包起来。这样使得代码更加清晰可读，而不会认为是将条件判断语句的全等号（===）错写成了等号（=）。
eslint: [no-cond-assign](http://eslint.org/docs/rules/no-cond-assign)
```javascript
// ✓ ok 
while ((m = text.match(expr))) {
    // ... 
}
 
// ✗ avoid 
while (m = text.match(expr)) {
    // ... 
}
```
### 16、单行代码块两边加空格。
eslint: [block-spacing](http://eslint.org/docs/rules/block-spacing)
```javascript
function foo () {return true;}    // ✗ avoid 
function foo () { return true; }  // ✓ ok 
```
### 17、对于变量和函数名统一使用驼峰命名法。
eslint: [camelcase](http://eslint.org/docs/rules/camelcase)
```javascript
function my_function () { }    // ✗ avoid 
function myFunction () { }     // ✓ ok 
 
var my_var = 'hello';           // ✗ avoid 
var myVar = 'hello';            // ✓ ok 
```
### 18、不允许有多余的行末逗号。
eslint: [comma-dangle](http://eslint.org/docs/rules/comma-dangle)
```javascript
var obj = {
    message: 'hello',   // ✗ avoid 
}
```
### 19、始终将逗号置于行末。
eslint: [comma-style](http://eslint.org/docs/rules/comma-style)
```javascript
var obj = {
    foo: 'foo'
    ,bar: 'bar'   // ✗ avoid 
}
 
var obj = {
    foo: 'foo',
    bar: 'bar'   // ✓ ok 
}
```
### 20、点号操作符须与属性需在同一行。
eslint: [dot-location](http://eslint.org/docs/rules/dot-location)
```javascript
console.
    log('hello');  // ✗ avoid 
 
console
    .log('hello'); // ✓ ok 
```
### 21、文件末尾留一空行【非强制】。
elint: [eol-last](http://eslint.org/docs/rules/eol-last)

### 22、函数调用时标识符与括号间不留间隔。
eslint: [func-call-spacing](http://eslint.org/docs/rules/func-call-spacing)
```javascript
console.log ('hello'); // ✗ avoid 
console.log('hello');  // ✓ ok 
```
### 23、键值对当中冒号与值之间要留空白。
eslint: [key-spacing](http://eslint.org/docs/rules/key-spacing)
```javascript
var obj = { 'key' : 'value' }    // ✗ avoid 
var obj = { 'key' :'value' }     // ✗ avoid 
var obj = { 'key':'value' }      // ✗ avoid 
var obj = { 'key': 'value' }     // ✓ ok 
```
### 24、构造函数要以大写字母开头。
eslint: [new-cap](http://eslint.org/docs/rules/new-cap)
```javascript
function animal () {}
var dog = new animal();    // ✗ avoid 
 
function Animal () {}
var dog = new Animal();    // ✓ ok 
```
### 25、无参的构造函数调用时要带上括号。
eslint: [new-parens](http://eslint.org/docs/rules/new-parens)
```javascript
function Animal () {}
var dog = new Animal;    // ✗ avoid 
var dog = new Animal();  // ✓ ok 
```
### 26、对象中定义了存值器，一定要对应的定义取值器。
eslint: [accessor-pairs](http://eslint.org/docs/rules/accessor-pairs)
```javascript
var person = {
  set name (value) {    // ✗ avoid 
    this.name = value;
  }
}
 
var person = {
  set name (value) {
    this.name = value;
  },
  get name () {         // ✓ ok 
    return this.name;
  }
}
```
### 27、子类的构造器中一定要调用 super
eslint: [constructor-super](http://eslint.org/docs/rules/constructor-super)
```javascript
class Dog {
  constructor () {
    super();   // ✗ avoid 
  }
}
 
class Dog extends Mammal {
  constructor () {
    super();   // ✓ ok 
  }
}
```
### 28、使用数组字面量而不是构造器。
eslint: [no-array-constructor](http://eslint.org/docs/rules/no-array-constructor)
```javascript
var nums = new Array(1, 2, 3);   // ✗ avoid 
var nums = [1, 2, 3];            // ✓ ok 
```
### 29、避免使用 arguments.callee 和 arguments.caller。
eslint: [no-caller](http://eslint.org/docs/rules/no-caller)
```javascript
function foo (n) {
  if (n <= 0) return;
 
  arguments.callee(n - 1);   // ✗ avoid 
}
 
function foo (n) {
  if (n <= 0) return;
 
  foo(n - 1);
}
```
### 30、避免对类名重新赋值。
eslint: [no-class-assign](http://eslint.org/docs/rules/no-class-assign)
```javascript
class Dog {}
Dog = 'Fido'    // ✗ avoid 
```
### 31、避免修改使用 const 声明的变量。
eslint: [no-const-assign](http://eslint.org/docs/rules/no-const-assign)
```javascript
const score = 100;
score = 125;       // ✗ avoid 
```
### 32、避免使用常量作为条件表达式的条件（循环语句除外）。
eslint: [no-constant-condition](http://eslint.org/docs/rules/no-constant-condition)
```javascript
if (false) {    // ✗ avoid 
  // ... 
}
 
if (x === 0) {  // ✓ ok 
  // ... 
}
 
while (true) {  // ✓ ok 
  // ... 
}
```
### 33、正则中不要使用控制符。
eslint: [no-control-regex](http://eslint.org/docs/rules/no-control-regex)
```javascript
var pattern = /\x1f/;    // ✗ avoid 
var pattern = /\x20/;    // ✓ ok 
```
### 34、不要使用 debugger。
eslint: [no-debugger](http://eslint.org/docs/rules/no-debugger)
```javascript
function sum (a, b) {
  debugger;      // ✗ avoid 
  return a + b;
}
```
### 35、不要对变量使用 delete 操作。
eslint: [no-delete-var](http://eslint.org/docs/rules/no-delete-var)
```javascript
var name;
delete name;     // ✗ avoid 
```
### 36、不要定义冗余的函数参数。
eslint: [no-dupe-args](http://eslint.org/docs/rules/no-dupe-args)
```javascript
function sum (a, b, a) {  // ✗ avoid 
  // ... 
}
 
function sum (a, b, c) {  // ✓ ok 
  // ... 
}
```
### 37、类中不要定义冗余的属性。
eslint: [no-dupe-class-members](http://eslint.org/docs/rules/no-dupe-class-members)
```javascript
class Dog {
  bark () {}
  bark () {}    // ✗ avoid 
}
```
### 38、对象字面量中不要定义重复的属性。
eslint: [no-dupe-keys](http://eslint.org/docs/rules/no-dupe-keys)
```javascript
var user = {
  name: 'Jane Doe',
  name: 'John Doe'    // ✗ avoid 
}
```
### 39、switch 语句中不要定义重复的 case 分支。
eslint: [no-duplicate-case](http://eslint.org/docs/rules/no-duplicate-case)
```javascript
switch (id) {
  case 1:
    // ... 
  case 1:     // ✗ avoid 
}
```
### 40、同一模块有多个导入时一次性写完。
eslint: [no-duplicate-imports](http://eslint.org/docs/rules/no-duplicate-imports)
```javascript
import { myFunc1 } from 'module';
import { myFunc2 } from 'module';          // ✗ avoid 
 
import { myFunc1, myFunc2 } from 'module'; // ✓ ok 
```
### 41、正则中不要使用空字符。
eslint: [no-empty-character-class](http://eslint.org/docs/rules/no-empty-character-class)
```javascript
const myRegex = /^abc[]/;      // ✗ avoid 
const myRegex = /^abc[a-z]/;   // ✓ ok 
```
### 41、不要解构空值。
eslint: [no-empty-pattern](http://eslint.org/docs/rules/no-empty-pattern)
```javascript
const { a: {} } = foo;         // ✗ avoid 
const { a: { b } } = foo;      // ✓ ok 
```
### 42、不要使用 eval()。
eslint: [no-eval](http://eslint.org/docs/rules/no-eval)
```javascript
eval( "var result = user." + propName ); // ✗ avoid 
var result = user[propName];             // ✓ ok 
```
### 43、catch 中不要对错误重新赋值。
eslint: [no-ex-assign](http://eslint.org/docs/rules/no-ex-assign)
```javascript
try {
  // ... 
} catch (e) {
  e = 'new value';             // ✗ avoid 
}
 
try {
  // ... 
} catch (e) {
  const newVal = 'new value';  // ✓ ok 
}
```
### 44、不要扩展原生对象。
eslint: [no-extend-native](http://eslint.org/docs/rules/no-extend-native)
```javascript
Object.prototype.age = 21;     // ✗ avoid 
```
### 45、避免多余的函数上下文绑定。
eslint: [no-extra-bind](http://eslint.org/docs/rules/no-extra-bind)
```javascript
const name = function () {
  getName();
}.bind(user);    // ✗ avoid 
 
const name = function () {
  this.getName();
}.bind(user);    // ✓ ok 
```
### 46、避免不必要的布尔转换。
eslint: [no-extra-boolean-cast](http://eslint.org/docs/rules/no-extra-boolean-cast)
```javascript
const result = true;
if (!!result) {   // ✗ avoid 
  // ... 
}
 
const result = true;
if (result) {     // ✓ ok 
  // ... 
}
```
### 47、不要使用多余的括号包裹函数。
eslint: [no-extra-parens](http://eslint.org/docs/rules/no-extra-parens)
```javascript
const myFunc = (function () { });   // ✗ avoid 
const myFunc = function () { };     // ✓ ok 
```
### 48、switch 一定要使用 break 来将条件分支正常中断。
eslint: [no-fallthrough](http://eslint.org/docs/rules/no-fallthrough)
```javascript
switch (filter) {
  case 1:
    doSomething();    // ✗ avoid 
  case 2:
    doSomethingElse();
}
 
switch (filter) {
  case 1:
    doSomething();
    break           // ✓ ok 
  case 2:
    doSomethingElse();
}
 
switch (filter) {
  case 1:
    doSomething();
    // fallthrough  // ✓ ok 
  case 2:
    doSomethingElse();
}
```
### 49、不要省去小数点前面的0。
eslint: [no-floating-decimal](http://eslint.org/docs/rules/no-floating-decimal)
```javascript
const discount = .5;      // ✗ avoid 
const discount = 0.5;     // ✓ ok 
```
### 50、避免对声明过的函数重新赋值。
eslint: [no-func-assign](http://eslint.org/docs/rules/no-func-assign)
```javascript
function myFunc () { }
myFunc = myOtherFunc;    // ✗ avoid 
```
### 51、不要对全局只读对象重新赋值。
eslint: [no-global-assign](http://eslint.org/docs/rules/no-global-assign)
```javascript
window = {}     // ✗ avoid 
```
### 52、注意隐式的 eval()。
eslint: [no-implied-eval](http://eslint.org/docs/rules/no-implied-eval)
```javascript
setTimeout("alert('Hello world')")                   // ✗ avoid 
setTimeout(function () { alert('Hello world') })     // ✓ ok 
```
### 53、嵌套的代码块中禁止再定义函数。
eslint: [no-inner-declarations](http://eslint.org/docs/rules/no-inner-declarations)
```javascript
if (authenticated) {
    function setAuthUser () {}    // ✗ avoid 
}
```
### 54、不要向 RegExp 构造器传入非法的正则表达式。
eslint: [no-invalid-regexp](http://eslint.org/docs/rules/no-invalid-regexp)
```javascript
RegExp('[a-z')    // ✗ avoid 
RegExp('[a-z]')   // ✓ ok 
```
### 55、不要使用非法的空白符。
eslint: [no-irregular-whitespace](http://eslint.org/docs/rules/no-irregular-whitespace)
```javascript
function myFunc () /*<NBSP>*/{}   // ✗ avoid 
```
### 56、禁止使用 __iterator__。
eslint: [no-iterator](http://eslint.org/docs/rules/no-iterator)
```javascript
Foo.prototype.__iterator__ = function () {}   // ✗ avoid 
```
### 57、外部变量不要与对象属性重名。
eslint: [no-label-var](http://eslint.org/docs/rules/no-label-var)
```javascript
var score = 100
function game () {
    score: 50         // ✗ avoid 
}
```
### 58、不要使用标签语句。
eslint: [no-labels](http://eslint.org/docs/rules/no-labels)
```javascript
label:
    while (true) {
        break label     // ✗ avoid 
    }
```
## 59、不要书写不必要的嵌套代码块。
eslint: [no-lone-blocks](http://eslint.org/docs/rules/no-lone-blocks)
```javascript
function myFunc () {
  {                   // ✗ avoid 
    myOtherFunc()
  }
}
 
function myFunc () {
  myOtherFunc()       // ✓ ok 
}
```
### 60、不要混合使用空格与制表符作为缩进。
eslint: [no-mixed-spaces-and-tabs](http://eslint.org/docs/rules/no-mixed-spaces-and-tabs)

### 61、除了缩进，不要使用多个空格。
eslint: [no-multi-spaces](http://eslint.org/docs/rules/no-multi-spaces)
```javascript
const id =    1234    // ✗ avoid 
const id = 1234       // ✓ ok 
```
### 62、不要使用多行字符串。
eslint: [no-multi-str](http://eslint.org/docs/rules/no-multi-str)
```javascript
const message = 'Hello \
                 world'     // ✗ avoid 
```
### 63、new 创建对象实例后需要赋值给变量。
eslint: [no-new](http://eslint.org/docs/rules/no-new)
```javascript
new Character()                     // ✗ avoid 
const character = new Character()   // ✓ ok 
```
### 64、禁止使用 Function 构造器。
eslint: [no-new-func](http://eslint.org/docs/rules/no-new-func)
```javascript
var sum = new Function('a', 'b', 'return a + b')    // ✗ avoid 
```
### 65、禁止使用 Object 构造器。
eslint: [no-new-object](http://eslint.org/docs/rules/no-new-object)
```javascript
let config = new Object()   // ✗ avoid 
```
### 66、禁止使用 new require。
eslint: [no-new-require](http://eslint.org/docs/rules/no-new-require)
```javascript
const myModule = new require('my-module')    // ✗ avoid 
```
### 67、禁止使用 Symbol 构造器。
eslint: [no-new-symbol](http://eslint.org/docs/rules/no-new-symbol)
```javascript
const foo = new Symbol('foo')   // ✗ avoid 
```
### 68、禁止使用原始包装器。
eslint: [no-new-wrappers](http://eslint.org/docs/rules/no-new-wrappers)
```javascript
const message = new String('hello')   // ✗ avoid 
```
### 69、不要将全局对象的属性作为函数调用。
eslint: [no-obj-calls](http://eslint.org/docs/rules/no-obj-calls)
```javascript
const math = Math()   // ✗ avoid 
```
### 70、不要使用八进制字面量。
eslint: [no-octal](http://eslint.org/docs/rules/no-octal)
```javascript
const num = 042     // ✗ avoid 
const num = '042'   // ✓ ok 
```
### 71、字符串字面量中也不要使用八进制转义字符。
eslint: [no-octal-escape](http://eslint.org/docs/rules/no-octal-escape)
```javascript
const copyright = 'Copyright \251'  // ✗ avoid 
```
### 72、使用 __dirname 和 __filename 时尽量避免使用字符串拼接。
eslint: [no-path-concat](http://eslint.org/docs/rules/no-path-concat)
```javascript
const pathToFile = __dirname + '/app.js'            // ✗ avoid 
const pathToFile = path.join(__dirname, 'app.js')   // ✓ ok 
```
### 73、使用 getPrototypeOf 来替代 __proto__。
eslint: [no-proto](http://eslint.org/docs/rules/no-proto)
```javascript
const foo = obj.__proto__               // ✗ avoid 
const foo = Object.getPrototypeOf(obj)  // ✓ ok 
```
### 74、不要重复声明变量。
eslint: [no-redeclare](http://eslint.org/docs/rules/no-redeclare)
```javascript
let name = 'John'
let name = 'Jane'     // ✗ avoid 
 
let name = 'John'
name = 'Jane'         // ✓ ok 
```
### 75、正则中避免使用多个空格。
eslint: [no-regex-spaces](http://eslint.org/docs/rules/no-regex-spaces)
```javascript
const regexp = /test   value/   // ✗ avoid 
 
const regexp = /test {3}value/  // ✓ ok 
const regexp = /test value/     // ✓ ok 
```
### 76、return 语句中的赋值必需有括号包裹。
eslint: [no-return-assign](http://eslint.org/docs/rules/no-return-assign)
```javascript
function sum (a, b) {
  return result = a + b     // ✗ avoid 
}
 
function sum (a, b) {
  return (result = a + b)   // ✓ ok 
}
```
### 77、避免将变量赋值给自己。
eslint: [no-self-assign](http://eslint.org/docs/rules/no-self-assign)
```javascript
name = name   // ✗ avoid 
```
### 78、避免将变量与自己进行比较操作。
esint: [no-self-compare](http://eslint.org/docs/rules/no-self-compare)
```javascript
if (score === score) {}   // ✗ avoid 
```
### 79、避免使用逗号操作符。
eslint: [no-sequences](http://eslint.org/docs/rules/no-sequences)
```javascript
if (doSomething(), !!test) {}   // ✗ avoid 
```
### 80、不要随意更改关键字的值。
eslint: [no-shadow-restricted-names](http://eslint.org/docs/rules/no-shadow-restricted-names)
```javascript
let undefined = 'value'     // ✗ avoid 
```
### 81、禁止使用稀疏数组（Sparse arrays）。
eslint: [no-sparse-arrays](http://eslint.org/docs/rules/no-sparse-arrays)
```javascript
let fruits = ['apple',, 'orange']       // ✗ avoid 
```
### 82、不要使用制表符。
eslint: [no-tabs](http://eslint.org/docs/rules/no-tabs)

### 83、正确使用 ES6 中的字符串模板。
eslint: [no-template-curly-in-string](http://eslint.org/docs/rules/no-template-curly-in-string)
```javascript
const message = 'Hello ${name}'   // ✗ avoid 
const message = `Hello ${name}`   // ✓ ok 
```
### 84、使用 this 前请确保 super() 已调用。
eslint: [no-this-before-super](http://eslint.org/docs/rules/no-this-before-super)
```javascript
class Dog extends Animal {
  constructor () {
    this.legs = 4     // ✗ avoid 
    super()
  }
}
```
### 85、用 throw 抛错时，抛出 Error 对象而不是字符串。
eslint: [no-throw-literal](http://eslint.org/docs/rules/no-throw-literal)
```javascript
throw 'error'               // ✗ avoid 
throw new Error('error')    // ✓ ok 
```
### 86、行末不留空格。
eslint: [no-trailing-spaces](http://eslint.org/docs/rules/no-trailing-spaces)

### 87、不要使用 undefined 来初始化变量。
eslint: [no-undef-init](http://eslint.org/docs/rules/no-undef-init)
```javascript
let name = undefined    // ✗ avoid 
 
let name
name = 'value'          // ✓ ok 
```
### 88、循环语句中注意更新循环变量。
eslint: [no-unmodified-loop-condition](http://eslint.org/docs/rules/no-unmodified-loop-condition)
```javascript
for (let i = 0; i < items.length; j++) {...}    // ✗ avoid 
for (let i = 0; i < items.length; i++) {...}    // ✓ ok 
```
### 89、如果有更好的实现，尽量不要使用三元表达式。
eslint: [no-unneeded-ternary](http://eslint.org/docs/rules/no-unneeded-ternary)
```javascript
let score = val ? val : 0     // ✗ avoid 
let score = val || 0          // ✓ ok 
```
### 90、return，throw，continue 和 break 后不要再跟代码。
eslint: [no-unreachable](http://eslint.org/docs/rules/no-unreachable)
```javascript
function doSomething () {
  return true
  console.log('never called')     // ✗ avoid 
}
```
### 91、finally 代码块中不要再改变程序执行流程。
eslint: [no-unsafe-finally](http://eslint.org/docs/rules/no-unsafe-finally)
```javascript
try {
  // ... 
} catch (e) {
  // ... 
} finally {
  return 42     // ✗ avoid 
}
```
### 91、关系运算符的左值不要做取反操作。
eslint: [no-unsafe-negation](http://eslint.org/docs/rules/no-unsafe-negation)
```javascript
if (!key in obj) {}       // ✗ avoid 
```
### 93、避免不必要的 .call() 和 .apply()。
eslint: [no-useless-call](http://eslint.org/docs/rules/no-useless-call)
```javascript
sum.call(null, 1, 2, 3)   // ✗ avoid 
```
### 94、避免使用不必要的计算值作对象属性。
eslint: [no-useless-computed-key](http://eslint.org/docs/rules/no-useless-computed-key)
```javascript
const user = { ['name']: 'John Doe' }   // ✗ avoid 
const user = { name: 'John Doe' }       // ✓ ok 
```
### 95、禁止多余的构造器。
eslint: [no-useless-constructor](http://eslint.org/docs/rules/no-useless-constructor)
```javascript
class Car {
    constructor () {      // ✗ avoid 
    }
}
```
### 96、禁止不必要的转义。
eslint: [no-useless-escape](http://eslint.org/docs/rules/no-useless-escape)
```javascript
let message = 'Hell\o'  // ✗ avoid 
```
### 97、import, export 和解构操作中，禁止赋值到同名变量。
eslint: [no-useless-rename](http://eslint.org/docs/rules/no-useless-rename)
```javascript
import { config as config } from './config'     // ✗ avoid 
import { config } from './config'               // ✓ ok 
```
### 98、属性前面不要加空格。
eslint: [no-whitespace-before-property](http://eslint.org/docs/rules/no-whitespace-before-property)
```javascript
user .name      // ✗ avoid 
user.name       // ✓ ok 
```
### 99、禁止使用 with。
eslint: [no-with](http://eslint.org/docs/rules/no-with)
```javascript
with (val) {...}    // ✗ avoid 
```
### 100、对象属性换行时注意统一代码风格。
eslint: [object-property-newline](http://eslint.org/docs/rules/object-property-newline)
```javascript
const user = {
    name: 'Jane Doe', age: 30,
    username: 'jdoe86'            // ✗ avoid 
}
 
const user = { name: 'Jane Doe', age: 30, username: 'jdoe86' }    // ✓ ok 
 
const user = {
    name: 'Jane Doe',
    age: 30,
    username: 'jdoe86'
}                                                                 // ✓ ok 
```
### 101、代码块中避免多余留白。
eslint: [padded-blocks](http://eslint.org/docs/rules/padded-blocks)
```javascript
if (user) {
                            // ✗ avoid 
    const name = getName()
 
}
 
if (user) {
    const name = getName()    // ✓ ok 
}
```
### 102、展开运算符与它的表达式间不要留空白。
eslint: [rest-spread-spacing](http://eslint.org/docs/rules/rest-spread-spacing)
```javascript
fn(... args)    // ✗ avoid 
fn(...args)     // ✓ ok 
```
### 103、遇到分号时空格要后留前不留。
eslint: [semi-spacing](http://eslint.org/docs/rules/semi-spacing)
```javascript
for (let i = 0 ;i < items.length ;i++) {...}    // ✗ avoid 
for (let i = 0; i < items.length; i++) {...}    // ✓ ok 
```
### 104、代码块首尾留空格。
eslint: [space-before-blocks](http://eslint.org/docs/rules/space-before-blocks)
```javascript
if (admin){...}     // ✗ avoid 
if (admin) {...}    // ✓ ok 
```
### 105、圆括号间不留空格。
eslint: [space-in-parens](http://eslint.org/docs/rules/space-in-parens)
```javascript
getName( name )     // ✗ avoid 
getName(name)       // ✓ ok 
```
### 106、一元运算符后面跟一个空格。
eslint: [space-unary-ops](http://eslint.org/docs/rules/space-unary-ops)
```javascript
typeof!admin        // ✗ avoid 
typeof !admin        // ✓ ok 
```
### 107、注释首尾留空格。
eslint: [spaced-comment](http://eslint.org/docs/rules/spaced-comment)
```javascript
//comment           // ✗ avoid 
// comment          // ✓ ok 
 
/*comment*/         // ✗ avoid 
/* comment */       // ✓ ok 
```
### 108、模板字符串中变量前后不加空格。
eslint: [template-curly-spacing](http://eslint.org/docs/rules/template-curly-spacing)
```javascript
const message = `Hello, ${ name }`    // ✗ avoid 
const message = `Hello, ${name}`      // ✓ ok 
```
### 109、检查 NaN 的正确姿势是使用 isNaN()。
eslint: [use-isnan](http://eslint.org/docs/rules/use-isnan)
```javascript
if (price === NaN) { }      // ✗ avoid 
if (isNaN(price)) { }       // ✓ ok 
```
### 110、用合法的字符串跟 typeof 进行比较操作。
eslint: [valid-typeof](http://eslint.org/docs/rules/valid-typeof)
```javascript
typeof name === 'undefimed'     // ✗ avoid 
typeof name === 'undefined'     // ✓ ok 
```
### 111、自调用匿名函数 (IIFEs) 使用括号包裹。
eslint: [wrap-iife](http://eslint.org/docs/rules/wrap-iife)
```javascript
const getName = function () { }()     // ✗ avoid 
 
const getName = (function () { }())   // ✓ ok 
const getName = (function () { })()   // ✓ ok 
```
### 112、yield * 中的 * 前后都要有空格。
eslint: [yield-star-spacing](http://eslint.org/docs/rules/yield-star-spacing)
```javascript
yield* increment()    // ✗ avoid 
yield * increment()   // ✓ ok 
```
### 113、请书写优雅的条件语句（avoid Yoda conditions）。
eslint: [yoda](http://eslint.org/docs/rules/yoda)
```javascript
if (42 === age) { }    // ✗ avoid 
if (age === 42) { }    // ✓ ok 
```
## 关于分号
### 1、使用分号或不使用分号【非强制】(保证同一个项目风格统一即可)。
eslint: [semi](http://eslint.org/docs/rules/semi)
```javascript
window.alert('hi');
window.alert('hi')
```
### 2、不要使用 (, [, ` 等作为一行的开始。在没有分号的情况下代码压缩后可能会导致报错，而坚持这一规范则可避免出错。
eslint: [no-unexpected-multiline](http://eslint.org/docs/rules/no-unexpected-multiline)
```javascript
// ✓ ok 
;(function () {
    window.alert('ok')
}())
 
// ✗ avoid 
(function () {
    window.alert('ok')
}())
// ✓ ok 
;[1, 2, 3].forEach(bar)
 
// ✗ avoid 
[1, 2, 3].forEach(bar)
// ✓ ok 
;`hello`.indexOf('o')
 
// ✗ avoid 
`hello`.indexOf('o')
// 备注：上面的写法只能说聪明过头了。

// 相比更加可读易懂的代码，那些看似投巧的写法是不可取的。

// 譬如：

;[1, 2, 3].forEach(bar)
// 建议的写法是：

var nums = [1, 2, 3]
nums.forEach(bar)
```









