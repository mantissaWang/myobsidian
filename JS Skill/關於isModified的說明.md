---
date: 2022-07-01
time: 16:41
mood:
---
# Metadata
Tags: [#JS #mongoose]
Data source: 
Source URL: [Mongoose](https://mongoosejs.com/docs/api.html#document_Document-isModified)



# 1、關於來源：
isModified是繼承Document而來。
```JS
Document.prototype.isModified()
```


# 2、內部使用的參數？
內部使用參數的型別必須要是String。

# 3、關於return的值？
這會回傳一個boolean。
官方說他回傳的東西是一個path。
原文如下：

	Returns true if any of the given paths is modified, else false. If no arguments, returns `true` if any path in this document is modified.

	If `path` is given, checks if a path or any full path containing `path` as part of its path chain has been modified.

# 4、以doc.set('documents.0.title', 'changed');為例？

```JS
doc.set('documents.0.title', 'changed');
doc.isModified()                      // true
doc.isModified('documents')           // true
doc.isModified('documents.0.title')   // true
doc.isModified('documents otherProp') // true
doc.isDirectModified('documents')     // false
```