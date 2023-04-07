
## Relational selectors
- all `<p>` in id "products" is orange
```css
#products p {
  color: orange;
}
```

- use of >p 
 ``` html   
	  <style>
	  #products > p {
		  color: orange;
      }
	  </style>
	  
      <section id="products">
      <p>Lorem ipsum dolor sit amet.</p>
      <article>
      <p>Lorem ipsum dolor sit amet.</p>
      </article>
    </section>
```
 ![[Pasted image 20230222175054.png]]

- +p select the next `<p>` tag right after the `<section>`
- ~p select all `<p>` after the `<section>`
- pseudo-elements vs pseudo-classes
   pseudo-elements to style part of an element. 
   pseudo-classes to style element in a particular state. Eg. Hovered anchor


## Selector weight
  - id>class
  - Selector specificity(# of id selectors, # of class selectors , # of element selectors)

## 渐变色
- gradient generator
