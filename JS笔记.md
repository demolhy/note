## 基本类型

分为两大类，九种数据类型：  

1.原始类型  
2.对象类型  

原始类型又分为七种：  
* string
* number
* undefind
* null
* boolean
* symbol(es6)
* bigint(es6)  

对象类型分为两种：  
* object
* function

symbol是一种独一无二的值，不是对象，无法使用new写法，基本方法：  
````
let name = Symbol("demolhy")
console.log(name)  // Symbol("demolhy")
typeof(name)  // Symbol

let names = Symbol("demolhy")
name === names // false
````
使用场景：可作为对象的属性名，保证每个对象不重名
````
let data = Symbol("name")
let obj = {}
obj[data] = "demolhy"
console.log(obj) // Symbol(name): "demolhy"
````

由于number有最大数限制，bigint可以表示任意大的整数，填补了Number在整数范围的表示空缺。  
JS 中的<font color='red'>Number</font>类型只能安全地表示-9007199254740991 (-(2^53-1)) 和9007199254740991(2^53-1)之间的整数，任何超出此范围的整数值都可能失去精度。  
JS 提供==Number.MAX_SAFE_INTEGER==常量来表示 最大安全整数，==Number.MIN_SAFE_INTEGER==常量表示最小安全整数：
````
const minInt = Number.MIN_SAFE_INTEGER;

console.log(minInt);  // -9007199254740991
````

使用Bigint就不用变通方法或库来安全地表示==Number.MAX_SAFE_INTEGER==和==Number.Min_SAFE_INTEGER==之外的整数，使用方法：
````
//方法1
console.log(9007199254740995n) //9007199254740995n
console.log(9007199254740995); //9007199254740996

//方法2
BigInt('9007199254740995') // 9007199254740995n
````
