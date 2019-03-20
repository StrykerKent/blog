---
layout: post
title:  "Level 1 Array Methods with JavaScript"
description: "Learn Javascript Level 1 Array Methods in this quickstart from Stryker Stinnette (a Web Application Developer of over 10 years)."
author: "Stryker Stinnette"
date:   2019-03-08 17:23:18 -0600
categories: [js]
tags: [javascript, array, beginner, method, level 1]
permalink: /level-one-array-methods-with-javascript/
---

Arrays are useful. Array methods make arrays even more useful. The better I get at programming, the more uses I find for them. In this article, I am going over what I call: Level 1 Array Methods using JavaScript. 

Have you read through [Mozilla Developer Network's](https://developer.mozilla.org/) documentation on arrays? It's great, but it can be a little overwhelming (especially if you are new to programming and/or arrays). Below, I have written an easy to follow quick start on the array methods I believe are `level 1` that I use most in my programming. 

If you are **not** new to arrays, then [click here to skip the Quick Notes for Beginners with Arrays section](#arraySuperstar).

<br>

### Three Quick Notes for Beginners with Arrays

**1) Arrays have an index that starts at 0.** 

An index is a number assigned to an item as it enters the array. The number can be used to locate an item in the array. (See below.)

{% highlight javascript %}
		0    1    2    3
const myArray = ['a', 'b', 'c', 'd'];
{% endhighlight %}

Item `c` is located at index 2. It is the third item in the list but since an array's index starts at 0, it is located at position 2.

**2) How to declare an array.**

{% highlight javascript %}
const arrayName = [];
// or
const arrayName = ['Item0', 'Item1', 'Item2', 'Item3'];
{% endhighlight %}

Use brackets to declare an array. Use empty brackets when you do not have values for your array yet. The name of my array is `arrayName` but you can call your array just about anything (as long as it does not start with a number).

**3) Array Values - Strings and Numbers**
{% highlight javascript %}
// Strings
const arrayWithStrings = ['Apples', 'Bananas', 'Oranges', 'Mangos'];
// Numbers
const arrayWithNumbers = [10, 11, 12, 13];
// Both Strings and Numbers
const arrayWithBothStringsAndNumbers = ['Apple', 11, 'Oranges', 'Bananas', 23, 47, 85];
{% endhighlight %}

Items in the array can be strings or numbers. Strings have to be surrounded by single `'` or double quotes `"` and numbers do not. Yes, you can have both strings and numbers in the same array.

<br>

## <a name="arraySuperstar"></a>Intro Over... On To Array Methods...

<br>

### Add Item to end of Array

{% highlight javascript %}
arrayName.push('Tom'); // adds 'Tom' to end of array
{% endhighlight %}

`Push` adds the item in parenthesis to the end of the array.

**Use case:** When you need to add a username to the array of logged in users.

{% highlight javascript %}
// Example:
const arrayName = ['Harry', 'Steve', 'Jack'];
// add Tom to array
arrayName.push('Tom');
// arrayName = ['Harry', 'Steve', 'Jack', 'Tom'];
{% endhighlight %}

<br>

### Find Index of Item in Array

{% highlight javascript %}
arrayName.indexOf('Tom'); // returns index number of where Tom is in our array
{% endhighlight %}

If the item you put in parenthesis is in the array, `indexOf` will return the index number of the item. If the item you are searching for is not in the variable you specified, then `indexOf` will return `-1`.

**Use case:** Check if the user is already in your array. 

{% highlight javascript %}
// Example:
const arrayName = ['Harry', 'Steve', 'Jack', 'Tom'];
// log to console the index of Tom in array
console.log(arrayName.indexOf('Tom'));
// 3
{% endhighlight %}

In the example above, `indexOf` returns the number `3`. To see what `indexOf` returned, we logged it to the console using `console.log()`.

<br>

### Remove Item in Array by Index Number

{% highlight javascript %}
arrayName.splice(0, 1);
{% endhighlight %}

Splice takes two parameters, `Start` and `deleteCount`. The `Start` is the index number of the item to start from, and `deleteCount` is how many to delete. For this example, I used `0` as the `Start` and `1` as the `deleteCount`.

**Use case:** Remove username from the array when the user logs off.

{% highlight javascript %}
// Example
const usersOnline = ['Harry', 'Steve', 'Jack', 'Tom'];
// Delete Jack
usersOnline.splice(2, 1);
// usersOnline = ['Harry', 'Steve', 'Tom']
{% endhighlight %}

Now `usersOnline` array is just `['Harry', 'Steve', 'Tom']`.

<br>

### Remove From End of Array
{% highlight javascript %}
arrayName.pop();
{% endhighlight %}

`Pop` removes the last item in the array.

**Use Case:** When you are doing Last In First Out (LIFO), pop will get the last item you added to the array out for you.

{% highlight javascript %}
// Example
const usersOnline = ['Harry', 'Steve', 'Jack', 'Tom'];
// Remove last item in array
arrayName.pop();
// usersOnline = ['Harry', 'Steve', 'Jack']
{% endhighlight %}

<br>

### Bonus: Check Array's Length

{% highlight javascript %}
arrayName.length;
{% endhighlight %}

Returns the count of items in the array. The count starts with 1.

**Use Case:** When you need to capitalize the first letter of each word in the array.

{% highlight javascript %}
// Example
const arrayName = ['Harry', 'Steve', 'Jack', 'Tom'];

//loop through each item in arrayName array
for (let i = 0; i < arrayName.length; i++) {
  // capitalize first letter of each word
  arrayName[i] = arrayName[i].toUpperCase();
}

//log to console the length of array to prove to the people I am not lying
console.log(arrayName.length);
//  4
{% endhighlight %}

<br>

Those are my most used `level 1` array methods. 

I hope this article was quick, easy to follow, and helped you learn. Let me know if I need to expand on something or explain it better (in the comments section below).

Next up… [Level 2 Array Methods]({% post_url 2019-03-18-level-two-array-methods-with-javascript %}).
