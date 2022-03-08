Topic: JS String Methods
Date: Mar 6, 2022 
Course: Insurance 
Class: Part One

---
# Introduction
JavaScript, methods and properties are available to primitive values, because JavaScript treats primitive values as objects when executing methods and properties.

## JavaScript String Length
The **length** property returns the length of a string

```
let text = "Samuel Wainaina Ndungu";
let length = text.length;

console.log(length);
```
---
##  Extracting  Parts of a String
There are 3 methods:
- slice(start, end)
- substring(start, end)
-  substr(start, length)

1. **slice()** Method: Returns an extracted part in a new string. It takes two parameters, *start* and the *end* positions(end excluded).

```
let str = "Kate, Joy, Samuel";  
let part = str.slice(5, 14); // position 5 to position 13(14-1)

console.log(part);
```

**Note:**
- JavaScript counts from position 0. First position is **0** Second position is **1** in that order.
- The position is counted from the end of the string if a parameter is negative.



 