 - Virtual Dom
 - compare the virtual dom to the actual and update changed nodes.
 - React vs Angular vs vue
   - React is a JavaScript library. Other two are framework.
- React only return a single HTML element. Use `Fragment` from React allows to return several HTML elements. `<></>`
- Using `map` to render the array item. We need to give each item a key.
- `onClick{ }` listen to click event.
- State Hook
  - built-in feature in React
  - `useState()`   component can have data or state that changes over time.
  - State hook is asynchronous. To minimize rerender. 
  - Update Hook.
   - Do not change the orginal value.
   - copy the value into the new object. 
	``` TypeScript
	  const [arr] = useState(-1); // returns an array. set initial to -1
	  arr[0]; //variable (selected index)
	  arr[1]; //update function
	  //usually used like
	  const [slectedElment, changeIndex] = useState(-1);
	   // list to click event and change the index  
	   //onClick={() => changeIndex(index)}

   ```
- Props
  - Passing Children.  Name Props property `children` `<Alert>Hello World</Alert>` . 
  - Passing data as object and their properties to a component parameter.
   ![[Pasted image 20230316174559.png]]
   `App.tsx`
   ![[Pasted image 20230316174652.png]]
- Props vs State
  - Props: inpue passed to a componennt.
  - shoule be read-only
  - State: data managed. State changes each time. Dom is rerender.
- Import css file as an object 
 - name css file as `name.module.css`
 - import css file `import styles from './Button.module.css';`
 - Apply css classes to the HTML element 
 - `className={[styles.bttn, styles['bttn-primary']].join(' ')}`
- Add react icons 
  - `npm i react-icons@4.7.1`
  - Go to google find the one you like.
  - `import { BiAbacus } from 'react-icons/bi';`
  - `<BiAbacus size="40" color="blue" />` custom
- Conditional rendering
``` JSX
// reduce duplicate code
return (  
	<li className="item">  
	   {isPacked ? name + ' ✔' : name}  
	</li>  
);

//reduce duplicate code
//if (isPacked) {  
//return <li className="item">{name} ✔</li>;  
//}  
//return <li className="item">{name}</li>;

  ```
  - render some JSX when the condition is true, **or render nothing otherwise.**
```JSX
//logical &&
return (  
<li className="item">  

{name} {isPacked && '✔'}  

</li>  
);
```
 - rafce shortcut to create component
- **Form**
  - 方法1 
  -  `useRef` reference a DOM element.
  - `const nameRef = useRef<HTMLInputElement>(null)`
  - `<input ref={nameRef}`
  - read the input value `nameRef.current.value`
  - 方法2 Best
  - React Hook Form
  - use `register` to get value from input field
  - call `handleSubmit` to handle the submit. `console log` data as an object when hit submit.
	``` JSX
	  const { register, handleSubmit } = useForm();
	  <form onSubmit={handleSubmit((data) => console.log(data))}>
		  <input
		          {...register('name')}
		          id="name"
		          type="text"
		          className="form-control"
		        />
	
	```
	- Form validation
	- 方法1
	-  `const {formState: { errors } } = useForm();`
	- `{...register('name', { required: true, minLength: 3 })}`
	- `{errors.name?.type === 'required' && <p>The name field is requried</p>}`
       - 方法2 with zod
         -  
 
- Effect hook 
  -  after component renders
  - `axios.get('url') returns a promise
  - axios sends a http request to the server.
``` JavaScript
interface User {
  id: number;
  name: string;
}
const [users, changeUser] = useState<User[]>([]);
  //useState for http request
  const [error, setError] = useState('');
  useEffect(() => {
    const fetchUser = async () => {
      try {
        const res = await axios.get<User[]>(
         'https://jsonplaceholder.typicode.com/users'
        );
        changeUser(res.data);
      } catch (err) {
        setError((err as AxiosError).message);
      }
    };
    fetchUser();
    // get -> promise -> response/ error
    // get -> await promise -> response/ error
    // .then((res) => changeUser(res.data))
    // .catch((err) => setError(err.message))
  }, []);
```
- Promise 
  - an object that holds the eventual result or failure of an asynchronous operation.
  - delete data
    - `axios.delete`
  - Generic HTTP service
    -   