# Objects in JavaScript
- [Key terms](#Key-terms)
- [What is an object](#What-is-an-object?)
- [Why do we need objects](#Why-do-we-need-objects?)
- [How to access data in an object](#How-to-access-data-in-an-object)
- [Adding properties to objects](#Adding-properties-to-objects)
- [Reassigning properties](#Reassigning-properties)
- [More complex data](#More-complex-data-in-objects)
- [Object methods](#Methods-on-objects)

### Key terms
- Key: The name used to reference a value on an object
- Value: The data referenced by a key
- Property: How we refer to one of the key-value pairs of an object
- Method: A function on an object
- Dot Notation: Notation to access a value on an object, explicitly specifies the key

---

### What is an object? 

Objects are a complex data type. They are meant to bundle together two things:

  - State (data)
  - Behavior (functionality)

### Why do we need objects?

- When we need an associative relationship (e.g. a title for some info)
- We want to model a more complex thing.

Imagine you wanted to model all the information related to a dog in code (breed, size, name, age, etc). We could capture all of that information in an array:
 ```
 var myDog = ['Ruby', 'golden lab', 60, 7]
 ```
However, with an array we have no way to access elements other than by index. For example, if I wanted to access my dog's age, I would have to know that age is the fourth element in the array (`myDog[3]`). Arrays are great for ordered data sets, but less useful with unstructured data.

Althernatively, we could create a whole series of variables to hold that information:
  ```
  var dogName = 'Ruby';
  var breed = 'golden lab';
  var weight = 60;
  var age = 7;
  ```
However, these variables aren’t tied together in any sensible way. There is no way for our program to know that the variables `dogName` and `breed` refer to the same thing. 

---

This is where objects come in handy. Objects allow us to collect key-value pairs, or _properties_, into a single object. 
```
var myDog = {
    name: 'Ruby',
    breed: 'golden lab',
    weight: 60,
    age: 7
}
```

### How to access data in an object

You can use dot notation to access properties of an object.

```
console.log(myDog.name)

// 'Ruby'
```

### Adding properties to objects

You can add a property to an already created object using dot notation.

```
myDog.color = 'gold'
console.log(myDog);

// {
//   name: 'Ruby',
//   breed: 'golden lab',
//   weight: 60,
//   age: 7,
//   color: 'gold'
// }
```

### Reassigning properties

Sometimes, we need to update an existing property in an object. For example on my dog's birthday, I might update the value assigned to the `age` key. This idea is also commonly referred to as “updating the state” of an object.

```
myDog.age = 8;
console.log(myDog);

// {
//   name: 'Ruby',
//   breed: 'golden lab',
//   weight: 60,
//   age: 8,
//   color: 'gold'
// }
```

---

### More complex data in objects

The value assigned to a key in an object can be any data type, including boolean, array, or another object.

```
var myDog = {
    name: 'Ruby',
    breed: 'golden lab',
    weight: 60,
    age: 8,
    isFriendly: true,
    likes: ['chasing squirrels', 'chewing things', 'swimming'],
    cohabitants: {
        owner: 'Matt',
        roommates: ['Marisa', 'Sam'],
        cat: 'The cat'
    }
}
```

And here's how you can access those values:

```
console.log(myDog.isFriendly);
console.log(myDog.likes[2]);
console.log(myDog.cohabitants.owner);

// true
// 'swimming'
// 'Matt'
```

---

### Methods on objects

So far we have seen how objects can hold data about an object. However, we can also capture behavior, or functionality, in an object. We do this by assigning a function to the value of a key in an object. This is called a method. Let's add `bark` method to our dog object.

```
var myDog = {
    name: 'Ruby',
    breed: 'golden lab',
    weight: 60,
    age: 8,
    isFriendly: true,
    likes: ['chasing squirrels', 'chewing things', 'swimming'],
    cohabitants: {
        owner: 'Matt',
        roommates: ['Marisa', 'Sam'],
        cat: 'The cat'
    },
    bark: function() {
        return 'woof woof'
    } 
}
```

Just like a property, we can access this method using dot notation:

```
console.log(myDog.bark())

// 'woof woof'
```

You can reference properties of an object inside a method using the keyword _this_.

```
var myDog = {
    name: 'Ruby',
    breed: 'golden lab',
    weight: 60,
    age: 8,
    isFriendly: true,
    likes: ['chasing squirrels', 'chewing things', 'swimming'],
    cohabitants: {
        owner: 'Matt',
        roommates: ['Marisa', 'Sam'],
        cat: 'The cat'
    },
    bark: function() {
        return 'woof woof'
    },
    speak: function() {
        return 'hello, my name is ' + this.name + '. I like ' + this.likes[0]
    } 
}
```

```
console.log(myDog.speak())

// 'hello, my name is Ruby. I like chasing squirrels'
```