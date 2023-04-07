## Part 2
  - Getter for an object. 
``` JavaScript
	Object.defineProperty(this, 'duration', {
	    get: function () {
      return duration;
    },
  });
```
 
 - Prototype: a parent of another object. 
 - Prototypical Inheritance: when calling a method on an object. JavaScript engine will first look at the object itself. Then check its prototype.
 - Property description
   - `Object.defineProperty(object,propertyName,{})` we can set proerty to `writable` `enumerable` ...
 - Constructor 
  - The object and constructor their prototype are the same. For example, `let a = [];` `a.__proto__` and `Array.protoptype` are the same. `a` is created by JS `Array` constructor. 
  - When a method of a constructor may not used by every object it creates. We can define this method in `Object.protoptype.draw = function(){...}` 
  - `ShapeBase = ( Shape.prototype)`
  - Change the prototype of a Class.
    - Make `Circle` class a child class of `Shape`   
    - Need to reset the constructor Circle constructor. Otherwise (assign Shape constructor as defualt)
    - `Circle.prototype = Object.create(Shape.prototype)`
    - `Circle.prototype.constructor = Circle;`
 -  Use call to call a super constructor
 - Create a f## Function Inheritance
``` JavaScript
	function extend(Child, Parent) {
	  Child.prototype = Object.create(Parent.prototype);
	  Child.prototype.constructor = Parent;
	}
```

 - ES6
  -  Static method: can be used without creating an `new` object. Invoke by `Math.abs` 
  -  Classes 
  - Define a function outside of its constructor makes it prototype function. 
```javaScript
class Circle {
  constructor(radius) {
    this.radius = radius;
    this.find = function (){
    
    }
  }
  draw() {
    console.log('draw');
  }
}
```
- Private members using WeakMap
  - ![[img1.png]]
- getter and setter in es6
   - `get radius(){return _radius.get(this);}`
   - `set radius(radius){_radius.set(this,radius);}`
- Inheritance in es6 
- Inherite color from shape and set own radius.
``` javaScript
  class Shape {
  constructor(color) {
    this.color = color;
  }
  move() {
    console.log('move');
  }
}
class Tri extends Shape {
  constructor(color, radius) {
    super(color);
    this.radius = radius;
  }
}
const cab = new Tri('red', 1);
```
- ES6 modules
### 滑动到页面指定位置
   ``` JavaScript
     const btnScroll = document.querySelector('.scroll-to');

	 const QRcode = document.querySelector('#scorll-here');
	
	 btnScroll.addEventListener('click', function (event) {

		 QRcode.scrollIntoView({ behavior: 'smooth' });

     });
   ```
 ### Bubbling and capturing
  -  click event 
     - Capturing phase: When a click event happens,  event traels from root DOM element to the target element. 
     - Target phase: when the event hit the target element. 
     - Bubbling phase: The target element travels back to the root element. 
     - If a child and parent element has a `eventListner` of the same `event`.  When the child element is clicked, its parent also clicked. This is called bubbing. 
### Observer API
- `new IntersectionObserver(callback function, {root: , threshold:)`
- `threshold` : percentage of the DOM element is visible to the view port. The callback function get executed.  ie: 0 is just about to be visible to the view port. 
-  `threshold: 1`   :`isIntersecting()` is true only when the element is 100% on the screen. If the element is less than 100%,  ` isIntersecting() = false` the callback function also get called, unless we unobserve the element
- 