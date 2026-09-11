---
layout: post
title: "Spread Operator"
date: 2024-04-02
category: blog
labels:
  - Tutorial
image: /images/spread.jpg
excerpt: "Some days ago, I was interviewing three different developers for a position in our company and stumbled upon something really interesting. No one knew the spread operator..."
---
Some days ago, I was interviewing three different developers for a position in our company and stumbled upon something really interesting. No one knew the spread operator.

So I decided to write a little article showing the **Spread Operators** superpowers, that can save you some lines of code and logic on your project.

The definition of the S**pread Operator** on W3C is:

# Spread Operator

The JavaScript spread operator (`...`) allows us to quickly copy all or part of an existing array or object into another array or object.

So let`s use a simple example to show its first superpower:

Q**uickly copy all or part of an existing array**.

Let`s say that we have an Array of animals and another one listing new Animals and we want to join them together into a Zoo. We can use the **Spread Operator** to achieve it

```
const animals = ["lion","eagle","fox"];
const newAnimals = ["snake","whale","frog"];

const zoo = [...animals, ...newAnimals];

//zoo=["lion","eagle","fox","snake","whale","frog"]
```

Another example that was added by our Fronted Team Leader

Lidia Secchi

, is that we can also use the spread operator to update a single property inside an Object, as the following example:

```
const animal = {leg:4, tail:1, fur:'short'};

const newAnimal = {...animal, fur:'long' };

console.log(newAnimal);
// {leg:4, tail:1, fur:'long'}
```

The second Superpower that we use a lot is the **destructuring**

Second Mdn Docs:

The **destructuring** assignment syntax is a JavaScript expression that makes it possible to unpack values from arrays, or properties from objects, into distinct variables.

So let`s say that we have this Object called person and we will use only 2 values from it Name and Age, we have different ways to do it, but look how it is simple and clean using destructuring.

```
const person = {
  name: "Jon Doe",
  age: 30,
  height: 180,
  weight: 80
};

const {name, age} = person;

console.log(name,age);

// "Jon Doe", 30
```

The same thing works with arrays as well, but instead of using the key we can use the index:

```
const animals = ["lion","eagle","fox"];
const newAnimals = ["snake","whale","frog"];

const [animal1, animal2] = newAnimals

console.log(animal1,animal2);

// "snake", "whale"
```

This is the **basis** of the **Spread Operator**, let`s move on to something a little more **advanced**, using the same example as before, but let`s say that for some reason we want to rename the keys **Name** and **Age** to **personName** and **personAge**, we can achieve it using destructuring, and assigning its new name:

```
const person = {
  name: "Jon Doe",
  age: 30,
  height: 180,
  weight: 80
};

const {name:personName, age:personAge} = person;

console.log(personName,personAge);

// "Jon Doe", 30
```

Another more advanced use of it is to select the specific index from an Array, using the animal's array let`s console only the 3rd animal, using empty commas we can skip the indexes and catch only the third one.

```
const animals = ["lion","eagle","fox"];

const [,,thirdAnimal] = animals;

console.log(thirdAnimal)
// "fox"
```

Looks strange but is a common use on RXJS combineLatest when you need to use only one Observable as a response.

The last but not least superpower that we will talk about is the **…rest**, we can use it to retrieve the rest of an Array, follow the example.

Here we are going to get the first book, and then create an array with the rest of them.

```
const books = [
  "To Kill a Mockingbird",
  "1984",
  "Pride and Prejudice",
  "The Great Gatsby" ];

const [book1,...rest] = books

console.log(book1,rest);

//"To Kill a Mockingbird", ["1984", "Pride and Prejudice", "The Great Gatsby"]
```

Uff, ok… There are lots of ways to use the **Spread Operator**, it will save time, and lines to have a cleaner code.

And how do you use it?