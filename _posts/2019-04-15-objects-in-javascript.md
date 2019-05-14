---
layout: post
title:  "Objects in JavaScript"
description: "Learn the basics of the object data structure in JavaScript in this informational post from Stryker Stinnette (a Web Application Developer of over 10 years)."
author: "Stryker Stinnette"
date:   2019-04-15 19:15:00 -0600
readTime: "3 minute read"
categories: [js]
tags: [javascript, objects, beginner, [data structure]]
permalink: /objects-in-javascript/
---

<img src="/assets/images/javascript_objects.png" alt="JavaScript Objects">

Objects are everywhere in JavaScript. Learning them can help you understand parts of JavaScript better and help your programming. Objects are more dynamic than arrays because they can hold more than indexes and values.

[Geeks for Geeks](https://www.geeksforgeeks.org) says, 
> "Objects, in JavaScript is it’s most important data-type and forms the building blocks for modern JavaScript." 

This article is a basic introduction to objects.  I will not be going over objects in-depth, but I will be informing you of the parts I use most frequently to get you up and running quickly. For a more in-depth description of objects, I recommend [MDN Working with Objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects).


<br>

## What is an Object?

[MDN](https://developer.mozilla.org/) defines an object as:

> "An object is a collection of properties, and a property is an association between a name (or key) and a value. A property's value can be a function, in which case the property is known as a method."

<br>

Let's break this definition down. `"An object is a collection of properties"`, like:


{% highlight javascript %}
const footballPlayer =  {
  name: 'Tom', 
  position: 'QB',
  jerseyNumber: 12, 
  team: 'New England'
}
{% endhighlight %}

In the example above, the object `footballPlayer` has properties of name, position, jerseyNumber, and team. These properties are known as keys and the corresponding strings or numbers beside them are known as values. Together, each key and value make up a key-value pair. 

{% highlight javascript %}
// key    // value
name:     Tom 

// key    // value
position: QB
{% endhighlight %}

<br>

The second part of the MDN object definition says `"A property's value can be a function, in which case the property is known as a method."` 
To simplify, this means a function inside an object is called a method. See the throw method/function in the example below:
{% highlight javascript %}
const footballPlayer = {
  name: 'Tom', 
  position: 'QB',
  throw() {
    let numberOfYards = Math.floor(Math.random() * 61);
    console.log(`football was thrown ${numberOfYards} yards`);
  }
}

footballPlayer.throw();
// outputs: 'football was thrown 53 yards'
// number of yards will generated randomly by JavaScript. 0 to 60.
{% endhighlight %}

`Throw` is a function that takes no parameters and console logs out the action of the player, which is "football was thrown [random integer under 61] yards". Since this function is inside of an object, it is referred to as a method. 

To call the throw method, you would type `footballPlayer.throw()`. 

<br>

## What can you do with Objects?

Objects are great for data. With objects, you can mock a database for examples/prototyping, retrieve Web API data, or store/retrieve NoSQL Database data (MongoDB). 

Don't forget the obvious: You can use a programming paradigm called `Object Oriented Programming` which uses objects.

<br>

## Display data from Objects

One way is to call the object name and use dot notation:

{% highlight javascript %}
console.log(footballPlayer.name);
//output: Tom
{% endhighlight %}

Another way is to use bracket notation:

{% highlight javascript %}
console.log(footballPlayer['name']);
//output: Tom
{% endhighlight %}

For iterating through objects with arrays:  

{% highlight javascript %}
const players = [
  {name: 'Tom', sport: 'football'},
  {name: 'Mike', sport: 'baseball'},
  {name: 'Bryce', sport: 'baseball'},
  {name: 'LeBron', sport: 'basketball'},
  {name: 'Lionel', sport: 'soccer'},
];

for(let i = 0; i < players.length; i++) {
  console.log(players[i].name, players[i].sport);
}

// output: 
// Tom football
// Mike baseball
// Bryce baseball
// LeBron basketball
// Lionel soccer
{% endhighlight %}

<br>

## Assign Values
You can assign values by using dot notation. You can overwrite a previous property's value or create a new property and value.

{% highlight javascript %}
const footballPlayer = {
  name: 'Tom'
}
// overwrite previous property value
footballPlayer.name = 'Brian';
console.log(footballPlayer.name);
// output: 'Brian'

//new property and value
footballPlayer.helmetSize = 'medium';
console.log(footballPlayer.helmetSize);
// output: 'medium'
{% endhighlight %}

You can also use `bracket notation`:

{% highlight javascript %}
const footballPlayer = {
  name: 'Tom'
}
// overwrite previous property value
footballPlayer['name'] = 'Brian';
console.log(footballPlayer['name']);
// output: 'Brian'

//new property and value
footballPlayer['helmetSize'] = 'small';
console.log(footballPlayer['helmetSize']);
// output: 'small'

{% endhighlight %}

<br>

## Objects are Everywhere in JavaScript
JavaScript uses objects itself. One example is the `Array` object. Yes, the arrays you have been using are objects in JavaScript. The array object has methods like split, join, push, pop, etc.

{% highlight javascript %}
// Example of an array method.
myArray.push('Ben');
{% endhighlight %}

I went over array methods in my previous 3 posts ([Level 1 Array Methods]({% post_url 2019-03-08-level-one-array-methods-with-javascript %}), [Level 2 Array Methods]({% post_url 2019-03-18-level-two-array-methods-with-javascript %}), [Level 3 Array Methods]({% post_url 2019-03-26-level-three-array-methods-with-javascript %})). 

Arrays are not the only objects in JavaScript. Check out [this expansive list of JavaScript built-in objects](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects) and tell me you are not surprised at some of those. (A string is an object too? Whoa.)

Thank you for your time. I hope this simple article helped you better understand objects in JavaScript. Now go out there and practice what you have learned.
