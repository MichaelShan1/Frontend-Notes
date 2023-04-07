```html
<!DOCTYPE html>
<html></html>
```

HTML & CSS(W3C) validator

## HTML element

- Meta element
  Information about the webpage. For example, "keywords" for search engine optimization. "description" a short description about the webpage under search key.
```html
	<meta charset="UTF-8" />

    <meta http-equiv="X-UA-Compatible" content="IE=edge" />

    <meta name="viewport" content="width=device-width, initial-scale=1.0" />

    <meta name="keywords" content="HTML, CSS" />

    <meta name="description" content="" />
```
- **link and hyper link**
a link just an address of the target page. Hyper link is the target to that page.

- **Image** 
当图片太大可以用如果用width定义图片失真，可以使用object-fit：cover
- **Video** 
boolean attributes: autoplay, controls, loop
```html
<video controls src="images/ocean.mp4">Your browser doesn't support videos. </video>
```
- **List**
	1. unordered list, ordered list 
	2. Description list 
		dl: description list
		dt: description term
		dd: description detail
	```   html
		<dl>
			
		      <dt>HTML</dt>
		
		      <dd>Hyper Text Markup Language</dd>
		
		      <dt>CSS</dt>
		
		      <dd>Cascading style sheet</dd>
		
		</dl>
		
	```



- **Tables**
	`<tr></tr>` a row of a table 
	`<td></td>` table data of a row
	`<th></th>` table header 
	```html
	<table>
	      <tr>
	        <td>Marketing</td>
	        <td>$100</td>
	        <td>ABC</td>
	      </tr>
	      <tr>
	        <td>accounting</td>
	        <td>$200</td>
	      </tr>
	    </table>
	```
	1. <span style="color: red;">Table Styling</span>
		 
		```css
		table {
		      border: 3px solid black;
		    }
		```
	![[Pasted image 20230221173314.png]]
	<br></br>
	
	```css
	table, td {
	      border: 3px solid black;
	      
	    }
	```
	 ![[Pasted image 20230221173903.png]]
	 <br></br>
	```css
	    table,
	    td {
	      border: 3px solid black;
	      border-collapse: collapse;
	      padding: 5px;
	    }
	```
	
	 ![[Pasted image 20230221174303.png]]
	
	<spa>
2. **table Header **
	``` html
		<table>
		<tr>
	        <th>Category</th>
	        <th>Amount</th>
	      </tr>
	      <tr>
	        <td>Marketing</td>
	        <td>$100</td>
	      </tr>
	      <tr>
	        <td>accounting</td>
	        <td>$200</td>
	      </tr>
		</table>
	```
	**Using thead and tbody**
	
	``` html
	<table>
	      <thead>
	        <tr>
	          <th>Category</th>
	          <th>Amount</th>
	        </tr>
	      </thead>
	      <tbody>
	        <tr>
	          <td>Marketing</td>
	          <td>$100</td>
	        </tr>
	        <tr>
	          <td>accounting</td>
	          <td>$200</td>
	        </tr>
	      </tbody>
	    </table>
	```
	Produce same feature as the code above but more structured. 
	<br></br>

	 一行一个th
	``` html
	 <tr>
	    <th colspan="2">Michael's corp</th>
	 </tr>
	```

	![[Pasted image 20230221183000.png]]

- **HTML 5 Semantic element**
   Help search enginee understands your webpage. 