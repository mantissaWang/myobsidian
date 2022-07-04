---
date: 2022-07-01
time: 16:35
mood:
---
# Metadata
Tags: [#JS #pre() #mongoose]
Data source: 
Source URL: [程式前沿](https://codertw.com/資料庫/9681/#outline__9_1)



# 1、pre(第一個參數,pre參數)
在執行第一個參數之前，會先進行pre參數。
```JS
var schema = new mongoose.Schema({ age:Number, name: String,x:Number,y:Number}); 
schema.pre('find',function(next){
console.log('我是pre方法1');
next(); 
});

schema.pre('find',function(next){ 
console.log('我是pre方法2'); 
next();
});
var temp = mongoose.model('temp', schema); temp.find(function(err,docs){ console.log(docs[0]); }) 

執行結果如下：
	我是pre方法1 
	我是pre方法2 
	{ _id: 5972ed35e6f98ec60e3dc886,name: 'huochai',age: 27,x: 1,y: 2 } 