---
layout: post
title: Double vs. Triple Equals
---

What is the difference between two == and three ===?

In Javascript, there’s a slight difference between using two equal signs and three equal signs. 
The short version of the difference between == and === is that two equal signs uses something called implicit type casting, and === compares both value AND the type, and both must match for that expression to return true. 

A very common example is 42 == ’42’ because the type coercion will force the number type 42 to equal a string, and then compare the two values. 
Going on a bit of a side tangent, type coercion also happens with cases like 42  + “”  returning “42” because the  compiler forces the 42 to be converted to a string. 
Since there is a + sign and also a string “” the + sign becomes a string concatenation and converts everything to the right of the expression into a string. 
Javascript is evaluated left to right, so 42 + 5 + “string” would be “47string” but 42 + “string” + 5 would be 42string5.
<!--break-->
Another example of when == and === is especially relevant is with object equality.
```
var huskyPuppy = {
    type: "puppy",
    adorableness: "true"
};

var terrierPuppy = {
    type: "puppy",
    adorableness: "true"
};

var callingHusky = huskyPuppy

// Outputs: both false
console.log(huskyPuppy === terrierPuppy);
console.log(huskyPuppy == terrierPuppy);

//Outputs: true
console.log(callingHusky === huskyPuppy);
```

Although huskyPuppy and terrierPuppy seem identical, they’re each a new instance of an object, and therefore not ‘strictly’ equal. 

If you want to find out how to compare if two objects are ‘value wise’ the same, then you will have to go through their keys and compare their key value pairs.

Generally when comparing values you  want to stay away from only using two equals signs, since sometimes it will change the type of one of your comparison values, but only at time of comparison.
