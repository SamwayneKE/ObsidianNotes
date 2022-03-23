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

A similar result can be achieved using the [`localeCompare()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/localeCompare) method inherited by `String` instances.
```
// JavaScript Demo: String.localeCompare()

const a = 'réservé'; // with accents, lowercase
const b = 'RESERVE'; // no accents, uppercase

console.log(a.localeCompare(b));
// expected output: 1
console.log(a.localeCompare(b, 'en', { sensitivity: 'base' }));
// expected output: 0
```

Note that `a == b` compares the strings in `a` and `b` for being equal in the usual case-sensitive way. If you wish to compare without regard to upper or lower case characters, use a function similar to this:

```
// Upper case is used instead of lower case in this function, due to problems with certain UTF-8 character conversions.

function isEqual(str1, str2)
{
    return str1.toUpperCase() === str2.toUpperCase()
} // isEqual

```

## String primitives and String objects
- **Primitive strings:** String literals (denoted by double or single quotes) and strings returned from `String` calls in a non-constructor context (that is, called without using the `new` keyword.
-  JavaScript automatically converts primitives to `String` objects, so that it's possible to use `String` object methods for primitive strings. 
- In contexts where a method is to be invoked on a primitive string or a property lookup occurs, JavaScript will automatically wrap the string primitive and call the method or perform the property lookup.

**The new keyword:**

```
let s_prim = 'foo'
let s_obj = new String(s_prim)

console.log(typeof s_prim) // Logs "string"
console.log(typeof s_obj)  // Logs "object"

```

- String primitives and `String` objects also give different results when using `eval()`. Primitives passed to `eval` are treated as source code; `String` objects are treated as all other objects are, by returning the object. For example:

**The eval() method:**

```
let s1 = '2 + 2'           // creates a string primitive
let s2 = new String('2 + 2')  // creates a String object
console.log(eval(s1))      // returns the number 4
console.log(eval(s2))      // returns the string "2 + 2"
```
---
- For these reasons, the code may break when it encounters `String` objects when it expects a primitive string instead, although generally, authors need not worry about the distinction.

**The valueof() method:**

- A `String` object can always be converted to its primitive counterpart with the `valueOf()` method.

```
let s1 = '2 + 2'           // creates a string primitive
let s2 = new String('2 + 2')  // creates a String object
console.log(eval(s1))      // returns the number 4
console.log(eval(s2))      // returns the string "2 + 2"

console.log(eval(s2.valueOf()))  // returns the number 4
```

### [Long literal strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String#long_literal_strings "Permalink to Long literal strings")

Sometimes, your code will include strings which are very long. Rather than having lines that go on endlessly, or wrap at the whim of your editor, you may wish to specifically break the string into multiple lines in the source code without affecting the actual string contents. There are two ways you can do this.

**Method 1:**

You can use the [+](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Addition) operator to append multiple strings together, like this:

```
let longString = "This is a very long string which needs " +
                 "to wrap across multiple lines because " +
                 "otherwise my code is unreadable."
                 
```
```
```

**Method 2:**

You can use the backslash character (`\`) at the end of each line to indicate that the string will continue on the next line. Make sure there is no space or any other character after the backslash (except for a line break), or as an indent; otherwise it will not work.

That form looks like this:

```
let longString = "This is a very long string which needs \
to wrap across multiple lines because \
otherwise my code is unreadable."
```

Both of the above methods result in identical strings.

---
### Summary
- See more here [[JS String Methods]]
- Check more here [[JS String Reference]].