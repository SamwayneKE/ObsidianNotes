Topic: JavaScript String Reference by MDN Web Docs
Date: Mar 10, 2022 
Course: Web Development
Class: JavaScript Basics

---
# Strings
The `string` object is used to represent and manipulate a sequence of characters.

## Introduction
Strings are useful for holding data that can be represented in text form. Strings are useful for holding data that can be represented in text form. Some of the most-used operations on strings are to check their [`length`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/length), to build and concatenate them using the [+ and += string operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators#string_operators), checking for the existence or location of substrings with the [`indexOf()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/indexOf) method, or extracting substrings with the [`substring()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring) method.

## Creating strings
Strings can be created as:
- **Primitives:** From string literals.
- **Objects:** Using the `string()` constructor.

```
const string1 = "A string primitive";
const string2 = 'Also a string primitive';
const string3 = `Yet another string primitive`;


const string4 = new String("A String object");
```

String literals can be specified using single or double quotes, which are treated identically, or using the backtick character. This last form specifies a `template literal` with this form you can interpolate expressions.

## Character Access
1. **charAt()** method.

*E.g*
```
return 'cat'.charAt(1) // returns "a"
```

2. The other way (introduced in ECMAScript 5) is to treat the string as an array-like object, where individual characters correspond to a numerical index:

*E.g*

```
return 'cat'[1] // returns "a"

```

**Note:**
When using bracket notation for character access, attempting to delete or assign a value to these properties will not succeed. The properties involved are neither writable nor configurable.
## Comparing strings
We use less-than(<) or the greater-than(>) operators.

```
let a = 3;
let b = 2;

if (a < b) { // true
	console.log(a + ' is less than ' + b);
} else if (a > b) { // false
	console.log(a + ' is greater than ' + b);
} else { // false
	console.log(a + ' and ' + b + ' are equal');
}
```




---

### Summary
- See more here [[JS String Methods]]
- Check more here [[JS String Reference]].