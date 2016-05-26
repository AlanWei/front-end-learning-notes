# ES6

1. Default parameters
~~~
  function [name]([param1[ = defaultValue1 ][, ..., paramN[ = defaultValueN ]]]) {
    // statements
  }
~~~
e.g.
~~~
  function setBackgroundColor(element, color = 'rosybrown') {
    element.style.backgroundColor = color;
  }
~~~

2. Object.assign()
  1. Cloning an object
    ~~~
      var obj = { a: 1 };
      var copy = Object.assign({}, obj);
    ~~~
  2. Merging objects
    ~~~
      var o1 = { a: 1 };
      var o2 = { a: 1 };
      var o3 = { a: 1 };
      var merge = Object.assign({}, o1, o2 , o3);      
    ~~~
  3. Note: Properties on the prototype chain and non-enumerable properties cannot be copied
    ~~~
      var obj = Object.create({ foo: 1 }, { // foo is on obj's prototype chain.
        bar: {
          value: 2  // bar is a non-enumerable property.
        },
        baz: {
          value: 3,
          enumerable: true  // baz is an own enumerable property.
        }
      });

      var copy = Object.assign({}, obj);
      console.log(copy); // { baz: 3 }
    ~~~