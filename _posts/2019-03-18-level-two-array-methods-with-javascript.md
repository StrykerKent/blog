---
layout: post
title:  "Level 2 Array Methods with JavaScript"
description: "Learn Javascript Level 2 Array Methods in this informational post from Stryker Stinnette (a Web Application Developer of over 10 years)."
author: "Stryker Stinnette"
date:   2019-03-18 7:15:00 -0600
readTime: "4 minute read"
categories: [js]
tags: [javascript, array, beginner, method, level 2]
permalink: /level-two-array-methods-with-javascript/
---

<img src="/assets/images/javascript_array_methods_level_2.png" alt="JavaScript Array Methods Level 2 shift unshift join sort reverse includes">

The array methods in this article are next level (a.k.a. level 2), in my opinion. Learn these array methods after [Level 1 Array Methods]({% post_url 2019-03-08-level-one-array-methods-with-javascript %}). Remember, I am trying to 
make this easy to understand without the extra fluff. For more in-depth array method explanations, go to the [Mozilla Developer Network](https://developer.mozilla.org/) website.

This is part 2 of my "Array Series." If you missed part 1 then go here: [Level 1 Array Methods]({% post_url 2019-03-08-level-one-array-methods-with-javascript %}).

<br>

### Add Item at Beginning of Array
{% highlight javascript %}
arrayName.unshift('New York'); // adds 'New York' to beginning of array
{% endhighlight %}

`Unshift` adds the item in parenthesis to the beginning of the array and returns the number of items in the array. The array becomes one item larger and moves existing items up one index.

**Use case:** When you are taking a coding challenge and they ask you to add an item to the beginning of the array.

{% highlight javascript %}
// Example:
// Index                                0              1          2
const mostPopulatedUSCitiesInOrder = ['Los Angeles', 'Chicago', 'Houston'];

// add New York to beginning of array and log count of array
console.log(mostPopulatedUSCitiesInOrder.unshift('New York'));
//output: 4

// log array to console
console.log(mostPopulatedUSCitiesInOrder);
// Index         0              1          2         3
// output: ['New York', 'Los Angeles', 'Chicago', 'Houston'];
{% endhighlight %}

Los Angeles went from an index of 0 to an index of 1 when you add an item to the array using `unshift`.

<br>

### Remove Item at Beginning of Array
{% highlight javascript %}
arrayName.shift(); 
{% endhighlight %}

`Shift` removes the first item in the array and returns it.

**Use case:** When you are taking a coding challenge and they ask you to remove an item from the beginning of the array.

{% highlight javascript %}
// Example:
const mostPopulatedUSCitiesInOrder = ['New York', 'Los Angeles', 'Chicago', 'Houston'];

// remove first item in array and console log removed item
console.log(mostPopulatedUSCitiesInOrder.shift());
// output: 'New York'

// log array to console
console.log(mostPopulatedUSCitiesInOrder);
// output: ['Los Angeles', 'Chicago', 'Houston'];
{% endhighlight %}

<br>

### Join Items in Array into One String

{% highlight javascript %}
arrayName.join(); 
{% endhighlight %}

`Join` concatenates all the items in the array into a string. (Concatenate is another way to say `put together`.) 
Each item from the array will be separated by what you put in the parenthesis. Commas will be used if you leave join parenthesis blank.

{% highlight javascript %}
// Example:
const arrayName = ['Harry', 'Steve', 'Jack', 'Tom'];

// join array items and console log result
console.log(arrayName.join());
// output: Harry,Steve,Jack,Tom
{% endhighlight %}


**Use case:** When you receive data that is separated in an array, but you need it in one string.

{% highlight javascript %}
// Example:
const arrayName = ['H','e','l','l','o',' ','W','o','r','l','d','!'];

// join array items and console log the output
console.log(arrayName.join(''));
// output: Hello Word!
{% endhighlight %}

<br>

### Sort an Array
{% highlight javascript %}
arrayName.sort(); 
{% endhighlight %}

`Sort` reorders items in the array into alphabetical order, then returns the array in its new order. The array items are sorted as strings (UTF-16).

**Use case:** When you need to sort an array in alphabetical order.

{% highlight javascript %}
// Example:
const mostPopulatedUSCitiesSortByName = ['New York', 'Los Angeles', 'Chicago', 'Houston'];

// sort array
mostPopulatedUSCitiesSortByName.sort();

// log sorted array to console
console.log(mostPopulatedUSCitiesSortByName);
// output: ['Chicago', 'Houston', 'Los Angeles', 'New York'];
{% endhighlight %}
 
<br>


### Reverse an Array
{% highlight javascript %}
arrayName.reverse(); 
{% endhighlight %}

`Reverse` reverses items in the array, then returns the array in its new order. The last item in the array becomes the first, first to last item becomes the second, and so on.

**Use case:** When you are in a coding challenge interview and they ask you to reverse an array.

{% highlight javascript %}
// Example:
const theArray = ['a', 'b', 'c', 'd'];

// reverse array
theArray.reverse();

// log array to console
console.log(theArray);
// output: ['d', 'c', 'b', 'a'];
{% endhighlight %}
 
<br>

### Check if Item is in Array Using Includes
{% highlight javascript %}
arrayName.includes('Tom'); 
{% endhighlight %}

The `Includes` array method checks the array for the value in parenthesis and returns `true` or `false`. True if `includes` found a match and false if it did not.

**Use case:** When you need to check if Oranges are already in your grocery list array.

{% highlight javascript %}
// Example:
const groceryList = ['Apples', 'Bananas', 'Oranges', 'Mangos'];

// check if Oranges are on grocery list array
console.log(groceryList.includes('Oranges'));
// output: true
{% endhighlight %}

<br>

### **Bonus:** Iterate through an Array Using forEach
{% highlight javascript %}
array1.forEach(function(item) {
  console.log(item);
}); 
{% endhighlight %}

`ForEach` loops through each item in the array and executes the declared function. If there are 4 items in the array, `forEach` will run 4 times.

**Use case:** When you need to check the length of each item in the array.

{% highlight javascript %}
// Example:
const theArray = ['Apples', 'Bananas', 'Oranges', 'Mangos'];

// check length of each item in the array using forEach
theArray.forEach(function(item) {
  console.log(item + ' - ' + item.length);
});
// output: 
// Apples - 6
// Bananas - 7
// Oranges - 7
// Mangos - 6
{% endhighlight %}

<br>

Those are what I classify as `level 2` array methods. 

I hope this article was quick, easy to follow, and helped you learn. Let me know if I need to expand on something or explain it better (in the comments section below).

Next up… [Level 3 Array Methods]({% post_url 2019-03-26-level-three-array-methods-with-javascript %}).
