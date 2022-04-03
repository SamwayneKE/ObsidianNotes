Topic: JavaScript Logical Operators
Date: April 03, 2022 
Course: Web Development
Class: JavaScript Basics

---

# Logical operators

There are four logical operators in JavaScript: `||` (OR), `&&` (AND), `!` (NOT), `??` (Nullish Coalescing). Here we cover the first three, the `??` operator is in the next article.

Although they are called “logical”, they can be applied to values of any type, not only boolean. Their result can also be of any type.

Let’s see the details.

 ## || (OR)

The “OR” operator is represented with two vertical line symbols:

`result = a || b;`

In classical programming, the logical OR is meant to manipulate boolean values only. If any of its arguments are `true`, it returns `true`, otherwise it returns `false`.

In JavaScript, the operator is a little bit trickier and more powerful. But first, let’s see what happens with boolean values.

There are four possible logical combinations:

```
<script>

	"use strict";
	
	alert( true || true ); // true
	alert( false || true ); // true
	alert( true || false ); // true
	alert( false || false ); // false

</script>

```




---
### Summary
- See more here [[JS String Methods]]
- Check more here [[JS String Reference]].