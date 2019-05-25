---
layout: post
title:  "Classes in JavaScript"
description: "Learn the basics of JavaScript Classes in this informational post from Stryker Stinnette (a Web Application Developer of over 10 years)."
author: "Stryker Stinnette"
date:   2019-05-20 20:00:00 -0600
readTime: "4 minute read"
categories: [js]
tags: [javascript, class, beginner, [object-oriented programming]]
permalink: /classes-in-javascript/
---

<img src="/assets/images/javascript_classes.png" alt="Basics of JavaScript Classes by Stryker Stinnette presented in a simple and concise way for quick and easy understanding">

Classes were added to JavaScript in ES6 (aka ECMAScript 2015). Although classes did not provide new functionality, they introduced an easier syntax for object-oriented programming in JavaScript. The class syntax in JavaScript is similar to the class syntax in other languages.

Before ES6 and classes, object-oriented programming was achieved using prototypes. We will not be going over prototypes in this article, but if you would like more information on them, check out [prototypes at MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype).

In my college computer science courses, classes did not come easy to me. Partly because I did not have a basic understanding of classes to build on, and because we covered a lot of information in a short timeframe. 

Below is my attempt at addressing the basics of a JavaScript Class in a simple and concise way for quick and easy understanding. Then we can build on this knowledge and become JavaScript Class experts.

<br>

## What is a Class?
> Classes are in fact "special functions". - [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)

In other programming languages, classes are referred to as blueprints (or templates) that can be re-used. Take a character in your favorite game. He/She has traits they always start with. These traits can be part of the blueprint. Health 100, speed 90, special ability 'airstrike', passive 'fast heal'. We could write these into a character class to be reused.

Below is a barebones example of a class:

{% highlight javascript %}
// declare class
class MyClassName {

}

// instantiate an instanace of class
const myVariableNameForClass = new MyClassName();
{% endhighlight %}

First we declare the class, then we instantiate an instanace of the class. More on this below.

<br>

## How to Create a Class

There are two ways to create a class, class declaration and class expression. We will be using class declaration in this article (trying to keep things simple).

{% highlight javascript %}
class MyClassName {

}
{% endhighlight %}

We create a class by using the `class` keyword (lowercase) then the name we are giving our class. Above, we used `MyClassName`. Class names should be in Pascal case (capitalize the first letter and first letter of each new word with no spaces between). After the class name, use opening and closing brackets to create the class body. The code for our class goes between the brackets.

Remember to create the class first before we access it. Classes are not [hoisted](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting) like functions are.  
​
<br>

## How to Instantiate a Class

Instantiate means to create an instance of. We will be creating an instance of the class we made previously.

{% highlight javascript %}
const myVariableNameForClass = new MyClassName();
{% endhighlight %}

To instantiate our class, we set a variable (`myVariableNameForClass`) equal to a new instance of the class (`MyClassName`) followed by an empty pair of parentheses as depicted in the code snippit above. To see this class, we would console log out the variable name `myVariableNameForClass` (see below).

{% highlight javascript %}
console.log(myVariableNameForClass);
// output MyClassName {}
{% endhighlight %}

<br>

## Constructor<a name="constructor"></a>

A constructor is a method that gets executed when a new instance of an object is created. The constructor provides the class with initial values. Check out the example of a class constructor below:

{% highlight javascript %}
class MasterChief {
  constructor() {
    this.health = 100;
    this.color = "green";
    this.grenadeCount = 2;
  }
}​
{% endhighlight %}

We can even pass a value to the constructor and assign it to a constructor property.

{% highlight javascript %}
class MasterChief {
  constructor(color) {
    this.health = 100;
    this.color = color;
    this.grenadeCount = 2;
  }
}​

const player1 = new MasterChief("green");
{% endhighlight %}

Let's walk through passing a value to the constructor:

We instantiate the class (`const player1 = new MasterChief("green");`) and give the class a value of `green` in the parenthesis.
Then the color `green` goes into the constructor as a parameter named `color` and then is passed to `this.color` by assignment. Now we can create multiple MasterChiefs of multiple colors.

<br>

**More facts about constructor methods:**

**1.** Can only have one constructor method per class.  
**2.** All classes have a constructor method.  
**3.** If we do not define a constructor method, one will be defined for us (behind the scenes).

<br>

**Why do constructor properties have `this` in front of them?**  

Because `this` refers to the class they are in. Without `this`, the values in the constructor will not be bound to the class they are being constructed in, therefore throwing a reference error of [property] not defined. 

<br>

## Methods

A method is a function that is declared inside a class. We have already learned about one method, the constructor method [(above)](#constructor).

We can create methods that complete an action or a task for the class object. We could create a method in our MasterChief class that throws a grenade or shoots a gun.

<br>
<a name="masterChief"></a>
{% highlight javascript %}
class MasterChief {
  constructor(color) {
    this.health = 100;
    this.color = color;
    this.grenadeCount = 2;
  }
  throwGrenade() {
    if (this.grenadeCount > 0) {
      console.log("Grenade thrown.");
      this.grenadeCount--;
    } else {
      console.log("Out of grenades.");
    }
  }
}

const player1 = new MasterChief("green");
​{% endhighlight %}

<br>

If we call `player1.throwGrenade();` three times, we would get

```
Grenade thrown.
Grenade thrown.
Out of grenades.
```

<br>

## What are Classes Used For?

Classes are used in object-oriented programming, which is a type of programming design. In a game using object-oriented design, we can use a class to build our characters and reuse the class every time that character is needed (as shown above with the [MasterChief class](#masterChief)).

In React, we can build components using Javascript Classes.

{% highlight javascript %}
class Welcome extends Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  render() {
    return (
       <h1>Hello, {this.props.name}!</h1>
       <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
    );
  }
}
​​{% endhighlight %}

<br><br>

After writing all of that, I feel better about JavaScript Classes and classes in general. Don't you?

Thank you for your time. I hope this simple article helped you better understand classes in JavaScript. If you need more help, feel free to comment below.
