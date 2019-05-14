---
layout: post
title:  "Level 3 Array Methods with JavaScript"
description: "Learn Javascript Level 3 Array Methods / Higher-Order Functions (filter, map, reduce) in this informational post from Stryker Stinnette (a Web Application Developer of over 10 years)."
author: "Stryker Stinnette"
date:   2019-03-25 19:15:00 -0600
readTime: "4 minute read"
categories: [js]
tags: [javascript, array, intermediate, methods, level 3, higher-order functions]
permalink: /level-three-array-methods-with-javascript/
---

<img src="/assets/images/javascript_array_methods_level_3.png" alt="JavaScript Array Methods Higher Order Functions">

What I classify as Level 3 array methods are what some people call higher-order functions. In this article, we will be going over [filter](#filter), [map](#map), and [reduce](#reduce) array methods.

I learned higher-order functions from Mattias Petter Johansson a.k.a. MPJ. [In his blog post and videos on higher-order functions](https://medium.com/humans-create-software/a-dirt-simple-introduction-to-higher-order-functions-in-javascript-b33bf9e19056), he tied higher-order functions to functional programming and stated, 
> "Making your programming style more functional will improve you a lot as a programmer."  

That sold me. This is my attempt at explaining and breaking down higher-order functions for anyone to understand.

<br>

Looking for level 1 or level 2 array methods? Check out my previous posts [Level 1 Array Methods]({% post_url 2019-03-08-level-one-array-methods-with-javascript %}) and [Level 2 Array Methods]({% post_url 2019-03-18-level-two-array-methods-with-javascript %}).

<br>

## What is a Higher-Order Function?

A higher order function is a function that takes a function as an argument, or returns a function. 

The array methods below (filter, map, reduce) accept a function as a parameter. This is what makes these array methods `Level 3`.

Still confused? I was too when I first read about this topic. Seeing and walking through an example will help clarify:
 
<br>

### **Filter()**

Let's say we want to filter an array of objects (players) to only give us baseball players. Below is the code in full to do this using the `filter` method:

{% highlight javascript %}
//1
const players = [
  {name: 'Tom', sport: 'football'},
  {name: 'Mike', sport: 'baseball'},
  {name: 'Bryce', sport: 'baseball'},
  {name: 'LeBron', sport: 'basketball'},
  {name: 'Lionel', sport: 'soccer'},
];

//2                             //3       //4
const baseballPlayers = players.filter(function(player) {
    return player.sport === 'baseball'; 
});

// (5) log output to console
console.log(baseballPlayers);
// output: [ { name: 'Mike', sport: 'baseball' },
// { name: 'Bryce', sport: 'baseball' } ]
{% endhighlight %}

What does the above code do?

**(1)** We declared an array of objects for players.  
**(2)** Next, we created a new array named baseballPlayers to save our output to.  
**(3)** Then we called the .filter() method on the original array (players).  
**(4)** Inside the filter function, we pass another function as an argument.  
**(5)** Lastly, we log the new array (baseballPlayers) to check our work.

<br>

Let's take a deeper look at the function (4) that is being passed as a parameter.

{% highlight javascript %}
// 4. excerpt from code block above. this is the function being passed as a parameter. 
function(player) {
    return player.sport === 'baseball';
}
{% endhighlight %}

The function **(4)** runs on each object in the array. If the sport equals baseball, then that object makes it to our new array. The final output for baseballPlayers is 

{% highlight javascript %}
[ { name: 'Mike', sport: 'baseball' }, 
{ name: 'Bryce', sport: 'baseball' } ]
{% endhighlight %}

Understand? Good. Now let's get to the meat and potatoes (map).

<br>

### **Map()**


> "Once you learn to use map, your life as a programmer changes." - MPJ


I agree. Map also accepts a function as a parameter and iterates over each item in the array (just like filter), but it does not have to return the whole object in the array. Again, an example will help clear this up.

If we wanted an array of only the name of the baseball players (instead of showing all keys and values for each baseball players' object), we could use `map` to do this. 

{% highlight javascript %}
const players = [
  {name: 'Tom', sport: 'football'},
  {name: 'Mike', sport: 'baseball'},
  {name: 'Bryce', sport: 'baseball'},
  {name: 'LeBron', sport: 'basketball'},
  {name: 'Lionel', sport: 'soccer'},
];

const baseballPlayers = players
	.filter(function(player) {
    		return player.sport === 'baseball';
	})
	.map(function(player) {
		return player.name
	});

// log output to console
console.log(baseballPlayers);
// output:  [ 'Mike', 'Bryce' ]
{% endhighlight %}

The `map` method above takes a function that returns only the name of the players. Since map follows the filter method, map only runs on the array items returned by filter. The new baseballPlayers array becomes:

{% highlight javascript %}
[ 'Mike', 'Bryce' ]
{% endhighlight %}


<br>

### **Reduce()**

Reduce takes two parameters the accumulator and the current value. The accumulator is the previous value returned from the previous run of the function inside reduce and the current value is the value we are currently iterating over in the array. 

I know it sounds confusing, but again the example will help us understand better.

(Notice: I have added `gamesPlayed` to each object in the players array and one more baseball player.)

{% highlight javascript %}
const players = [
  {name: 'Tom', sport: 'football', gamesPlayed: 269},
  {name: 'Mike', sport: 'baseball', gamesPlayed: 1065},
  {name: 'Bryce', sport: 'baseball', gamesPlayed: 927},
  {name: 'Cal', sport: 'baseball', gamesPlayed: 2632},
  {name: 'LeBron', sport: 'basketball', gamesPlayed: 1196},
  {name: 'Lionel', sport: 'soccer', gamesPlayed: 700},
];

const baseballGamesPlayed = players
    .filter(function(player) {
            return player.sport === 'baseball';
    })
    .map(function(player) { 
	return player.gamesPlayed;
	})
    .reduce(function(accumulator, currentGamesPlayedValue) {
      	return accumulator + currentGamesPlayedValue
    });
    // 1065 + 927 + 2632

    console.log(baseballGamesPlayed)
    //output:  4624
{% endhighlight %}

`Filter` returns the three objects in the array that have a sport of baseball.
`Map` returns only the gamesPlayed value for each object. [1065, 927, 2632]

`Reduce` iterates over the three values provided by map 1065 + 927 + 2632. 



***Iteration 1 (Mike)***  
accumulator = 0 ... currentGamesPlayedValue = 1065  
return 0 + 1065

***Iteration 2 (Bryce)***  
accumulator = 1065 ... currentGamesPlayedValue = 927  
return 1065 + 927

***Iteration 3 (Cal)***  
accumulator = 2037 ... currentGamesPlayedValue = 2632  
return 2037 + 2632


`Reduce` returns the final number which is 4624.

<br>

### **BONUS - Arrow Function Version**

Below is the `arrow function` version of the same code we just went over for reduce.

{% highlight javascript %}
const players = [
  {name: 'Tom', sport: 'football', gamesPlayed: 269},
  {name: 'Mike', sport: 'baseball', gamesPlayed: 1065},
  {name: 'Bryce', sport: 'baseball', gamesPlayed: 927},
  {name: 'LeBron', sport: 'basketball', gamesPlayed: 1196},
  {name: 'Lionel', sport: 'soccer', gamesPlayed: 700},
];

const baseballPlayers = players
    .filter(player => player.sport === 'baseball')
    .map(player => player.gamesPlayed)
    .reduce((accumulator, gamesPlayedValue) => accumulator + gamesPlayedValue);

    console.log(baseballPlayers)
    //output: 1992
{% endhighlight %}

Whoa, the arrow functions made this code block more compact and easier to read.

I hope this article helped you gain a better understanding of Higher-Order Functions / Level 3 Array Methods in JavaScript. Let me know if I need to expand on something or explain it better (in the comments section below).

Next up… [Objects in JavaScript]({% post_url 2019-04-15-objects-in-javascript %}).
