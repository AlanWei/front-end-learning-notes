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

