## Box model 
  ![[Pasted image 20230227160639.png]]

  - Padding is between content and border. 

  - Margin is between different element.   ex. `<p></p> <p></p>` 
  - Margin collapse: If all p has margin: 20px. The distance between two p tags is 20px, not 40 px.  
  - width: 50% 
	eg. 50% of its parent width. 
  - width: 50vw 
	eg. view width50% of the broswer window width.
  - width: 10em 
	eg. 10x font size of the current element. Trace back to parent element if current element does not have a font size. 
  - **width: 10rem**
	  eg. 10x font size of the root element. root font size = 16px
 -  rem helps with sizing for different user font settings. For example, user sets font size to small.  The box width changes accordingly. 
 - **z-index**: default 0. if set z-index to -1. 
 
 ![[Pasted image 20230227175619.png]]

## Positioning
- Relative: realative to the elment's nomal position
- Absolute: relative to the parent.
- Fixed: relative to the viewport.

## Flex box
- flex-direction: Style an element in one direction. Horizontally or vertically. 
### Flex box axis
 - direction: row 
 ![[Pasted image 20230227183636.png]]
 - direction: column 
![[Pasted image 20230227184335.png]]
### Aligning items
- justify-content ( along the main axis )
- align-items ( along the cross axis)
- align-content: apply rules to the entire flex box content

#### Row direction, center in main axis, flex-end in cross axis
```html
 <div class="container">
      <div class="flexbox">A</div>
      <div class="flexbox">B</div>
      <div class="flexbox">C</div>
    </div>
```


```css
.flexbox {
  width: 5rem;
  height: 5rem;
  background: gold;
  margin: 1rem;
}
.container {
  display: flex;
  flex-direction: row;
  border: 3px solid lightgrey;
  justify-content: center;
  align-items: flex-end;
  height: 90vh;
}
```

 ![[Pasted image 20230227184830.png]]
 
### Sizing items
- Flex basis: the initial size of a flex item
- Fex-grow: the growth factor.Increment the size of flex item. Based on free space of width and height 
- flex- shrink: the shrink factor


## Grid
<span style="color: red; font-size: 16; font-weight: bold; ">Define a grid</span>
- display: grid
- grid-template-rows
- gri-template-columns
### Aligning items
- justify-items ( along the horizontal axis )
- align-items ( along the vertical axis )
### Gap
- row gap
- column-gap
- gap
### Placing items
 - grid-row: change grid item to different row
 - grid-column: 占用几个column
```html
<div class="gridcon">
      <div class="gridbox gbox1">A</div>
      <div class="gridbox">B</div>
      <div class="gridbox">C</div>
      <div class="gridbox">D</div>
    </div>
```

```css
.gridcon {
  display: grid;
  grid-template-rows: repeat(3, 100px);
  grid-template-columns: repeat(2, 100px);
  border: 3px solid lightgreen;
  row-gap: 5px;
  column-gap: 5px;
}

.gridbox {
  background: gold;
}

.gbox1 {
  grid-column: 1/3;
}
```

![[Pasted image 20230227194515.png]]
### Define specific cells using name
- grid-template-areas: "first row first column first row second column"
- grid-area: put element into specific cell. 
<br>

## Font 

 - font-size: 1rem; 1 times the root of the user settings
 - Vertical spacing: line- height: 1.5; does not use rem in line-height because if the font size changes. the line-height also changes
 - Ideal line length: should be between 50-70 characters
 
 ### Formatting text
 - text-align: left
 - text-indent: 开头空格
 - text-decoration: underline;
 - text-transform: Capitalize;
 ## Form
 - Styling input form
 ```html
 <form>
      <div>
        <label for="name">Name</label>
        <input id="name" type="text" />
      </div>
      <div>
        <label for="email">Email</label>
        <input id="email" type="email" />
      </div>
      <button type="submit">Register</button>
      <button type="reset">Clear</button>
</form>
```

```css
label {
  display: block;
}

input[type='text'],
input[type='email'] {
  margin-bottom: 2rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  padding: 0.5rem 0.7rem;
  transition: border-color 0.15s, box-shadow 0.15s;
}

input[type='text']:focus,
input[type='email']:focus {
  border-color: #7db0fb;
  outline: 0;
  box-shadow: 0 0 0 1px dodgerblue;
}


button {
  background: dodgerblue;
  color: white;
  border-radius: 5px;
  border: 0;
  padding: 0.5rem;
}
```

 ## Suggestion list
 - Give suggestions of a input text.
 - User can choose or type in the field.
 ```html
 <form>
      <input type="text" list="countries" />
      <datalist id="countries">
        <option>Aus</option>
        <option>Canada</option>
      </datalist>

  </form>
```

## Drop-down list
- Drop-down by group
- ![[Pasted image 20230301194422.png]]
 ```html
 <form>
      <select>
        <optgroup label="Front-end Courses">
          <option value="">HTML</option>
          <option value="">CSS</option>
          <option value="">JS</option>
        </optgroup>
        <optgroup label="back-end Courses">
          <option value="">Select a course</option>
          <option value="">HTML</option>
          <option value="">CSS</option>
          <option value="">JS</option>
        </optgroup>
      </select>
 </form>
```

## Select files
 - Parameter: multiple, accept = ".jpg"
## Group related fields
```html
<form>
      <fieldset>
        <legend>Billing Address</legend>
        <input type="text" name="" id="" />
        <input type="text" name="" id="" />
        <input type="text" name="" id="" />
      </fieldset>
      <fieldset>
        <legend>Payment</legend>
        <input type="text" name="" id="" />
        <input type="text" name="" id="" />
        <input type="text" name="" id="" />
      </fieldset>
</form>
```
![[Pasted image 20230302152453.png]]
