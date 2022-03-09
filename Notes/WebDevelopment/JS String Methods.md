Topic: JavaScript String Methods
Date: Mar 6, 2022 
Course: Web Development
Class: JavaScript Basics

---
# Introduction
JavaScript, methods and properties are available to primitive values, because JavaScript treats primitive values as objects when executing methods and properties.

## JavaScript String Length
The `length` property returns the length of a string

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

`Note:`
- JavaScript counts from position 0. First position is **0** Second position is **1** in that order.
- The position is counted from the end of the string if a parameter is negative.

2. **substring():** `substring()` method is similar to `slice()`. The difference is that `substring()` cannot accept negative indexes.

```
let str = "Kate, Joy, Samuel";
let part = str.substring(5, 14); 

console.log(part);
```

`Note:` If you omit the second parameter, `substring()` will slice out the rest of the string.

3. **JavaScript String substr():** `substr()` is similar to `slice()`. The difference is that the second parameter specifies the **length** of the extracted part.

```
let str = "Apple, Banana, Kiwi";  
let part = str.substr(7, 6);
```

- `Note:` If you omit the second parameter, `subst()` will slice out the rest of the string.
- If the first parameter is negative, the position counts from the end of the string.
```
let str = "Apple, Banana, Kiwi";  
let part = str.substr(-4);

console.log(part)
```

---
## Replacing string content
The `replace()` method replaces a specified value with another value in a string.

```
let greetings = "Hello Samuel, how are you doing?";

let newGreetings = greetings.replace("Samuel", "Grace");

console.log(newGreetings);
```

`Note:`
- The `replace()` method does not change the original string.
- The `replace()` method returns a new string.
- The `replace()` method replaces only the *`first`* match. If you want to replace all matches, use a regular expression with the `/g flag set.` 

`Example:`

```
let greetings = "Hello Samuel? Samuel, I hope you are doing great?";
let newGreetings = greetings.replace(/Samuel/g, "Grace");

console.log(newGreetings);
```

- By default, the `replace()` method is case sensitive. Writing SAMUEL (with upper-case) will not work.

```
let greetings = "Hello Samuel? Samuel, I hope you are doing great?";
let newGreetings = greetings.replace(/SAMUEL/g, "Grace"); // SAMUEL(upper-case throws an error)

console.log(newGreetings);
```

- To replace case insensitive, use a **regular expression** with an `/i` flag (insensitive).

```
let greetings = "Hello Samuel? Samuel, I hope you are doing great?";
let newGreetings = greetings.replace(/SAMUEL/i, "Grace"); // This works due to i(insensitive to upper-case)

console.log(newGreetings);
```

----
## Converting to Upper and Lower Case 

1. **toUpperCase():** Converts a string to uppercase.

```
let greetings = "Hello Samuel? Samuel, I hope you are doing great?";
let newGreetings = greetings.toUpperCase();

console.log(newGreetings);
```

2. **toLowercase():** Converts a string to lowercase.

```
let greetings = "Hello Samuel? Samuel, I hope you are doing great?";
let newGreetings = greetings.toLowerCase();

console.log(newGreetings);

```

---
## JavaScript String concat()

The `concat()` method joins two or more strings.

```
let greetings = "Hello Samuel";
let newGreetings = "I hope you are doing?";
let finalGreetings = greetings.concat("," , " ", newGreetings);

// One can use + operator instead of concat()
let lastGreetings = greetings + ", " + newGreetings;

console.log(finalGreetings);
console.log(lastGreetings);
```

`Note:`

- All string methods return a new string. They don't modify the original string. Strings are *`immutable`*  Strings cannot be changed, only replaced.

## JavaScript String trim()

The `trim()` method removes whitespaces from both sides of a string.

```
let greetings = " Hello Samuel? Samuel, I hope you are doing? ";
let newGreetings = greetings.trim();

console.log(newGreetings);
```

## JavaScript String Padding
ECMAScript 2017 added two String methods:
1. `padStart:` Supports padding at the beginning of a string.

	`Note:` `padStart()` is not supported in Internet Explorer.

	```
	let age = "35";
    let paddedAge = age.padStart(4,0);
    
    console.log(paddedAge);
	```
	
2.  `padEnd:` Supports padding at the end of a string.

	`Note:` `padEnd()` is not supported in Internet Explorer.

	```
	let age = "35";
    let paddedAge = age.padEnd(4,0;
    
    console.log(paddedAge);
    
    ```

---

## Extracting String Characters

There are 3 methods for extracting string characters:

1.  **String charAt() method:** The `charAt()` method returns the character at a specified index (position) in a string.

	```
	let char = "Hello Samuel?";
	let newChar = char.charAt(3);

	console.log(newChar);
	
	```

2.  **String charCodeAt() method:** The `charCodeAt()` method returns the unicode of the character at a specified index in a string. The method returns a `UTF-16 code` (an integer between 0 and 65535). 

	```
	let char = "Hello Samuel?";
	let newChar = char.charCodeAt(3);
		
	console.log(newChar);
		
	```

---
## Property Access

ECMAScript 5 (2009) allows property access [ ] on strings:

```
let text = "HELLO WORLD";  
let char = text[0];

console.log(char);

```

## Note
Property access might be a little **unpredictable:**

-  It makes strings look like arrays (but they are not)
- If no character is found, [ ] returns undefined, while  charAt() returns an  string.
-   It is read only. str[0] = "A" gives no error (but does not work!)

```
let text = "HELLO WORLD";  
text[0] = "A"; // Gives no error, but does not work

``` 

---

## Converting a String to an Array
If you want to work with a string as an array, you can convert it to an array.

**String split() :** A string can be converted to an array with the `split()` method:

```
let text = "a,b,c,d,e,f";

console.log(text.split(",")); // Split on commas
console.log(text.split(" ")); // Split on spaces
console.log(text.split("|")); // Split on pipe
```

- If the separator is omitted, the returned array will contain the whole string in index [0].

- If the separator is "", the returned array will be an array of single character.

```
let text = "Hello";

const myArr = text.split("");
text = "";

for (let i = 0; i < myArr.length; i++) {
	text += myArr[i] + "<br>"
}

console.log(text);

```

---

### Summary
- See more ==here==.
