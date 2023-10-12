
# 对比

## 数据类型

```typescript
typescript
string
number toExponential toFixed toString
boolean
```

```typescript
let myMap = new Map();
let myMap = new Map([
        ["key1", "value1"],
        ["key2", "value2"]
    ]); 

数组
var numlist:number[] = [2,4,6,8];

元组
var mytuple = [10,"Runoob"];

枚举
enum Color {Red, Green, Blue};
let c: Color = Color.Blue;
console.log(c);    // 输出 2

类
class Site { 
   name():void { 
      console.log("Runoob") 
   } 
} 
var obj = new Site(); 
obj.name();

函数
function buildName(firstName: string, ...restOfName: string[]) {
    return firstName + " " + restOfName.join(" ");
}

匿名函数
var msg = function () {
    return "hello world";
};
console.log(msg());

lambda
var foo = (x:number)=>10 + x 
console.log(foo(100))      //输出结果为 110
```

