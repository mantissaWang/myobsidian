---
date: 2022-06-28
time: 15:42
mood:
---
# Metadata
Tags: [#JS #Bind]
Data source: Yves' Notion
Source URL: [JS進階篇2：Bind、Call、Apply](https://www.notion.so/yves01480/JS-2-Bind-Call-Apply-958d1db91a6442798c16b803e7fe4932#9a87e18583224420978123f25a387dce)



# 1、一個物件程式碼範例
```JS

let Wilson = { 
name = 'Wilson Ren', 
age = 25 
} 

function getAge(){ 
console.log(this); 
console.log(this.age);
} 

getAge(); 

//undefined
```
輸出結果為undifined。


# 2、使用bind？
```JS
let Wilson = { 
name = 'Wilson Ren', 
age = 25 
} 
function getAge(){ 
console.log(this.age); 
//這個this.age，透過bind來指向Wilson 
} 

let getWilsonAge = getAge.bind(Wilson); 
getWilsonAge();
```
