# Classes in Javascript

Classes are a ES6 feature providing a more cleaner and structures way to make objects dynamically in Javascript in contrast to using [Constructors in Javascript](https://github.com/sarimhasan/Today-I-Learned/blob/main/Javascript/Constructors-in-js.md).

First define a class and then its name

then make a constructor function inside with the options you want as parameters

then define the key value pairs using the this keyword equals to the parameter

```js
class Product {
  constructor(name, price) {
    this.name = name;
    this.price = price;
  }
}
```

You can also make a method by making a function without any key

```js
class Product {
  constructor(name, price) {
    this.name = name;
    this.price = price;
  }

  showProduct() {
    //method
    console.log(`Product Name: ${this.name}`);
    console.log(`Product Price: PKR${this.price}`);
  }
}
```

Now you can simply make a new object by calling the class and storing the value in a const variable

```js
const product1 = new Product("shirt", 800);
```

Now you can also see the value like this

```js
console.log(product1.name);
```

or with a more structured way like this

```js
product1.showProduct();
```

The output will look like this

```
Product Name: shirt
Product price: PKR800
```
