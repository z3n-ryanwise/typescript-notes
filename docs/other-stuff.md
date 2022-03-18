# Things of yet undefined
- [[README]]

## Non-Exception Faliures
Typescript can help to identify cases where exception would usually cause faliures, but not nexcessarily throw an exception. Consider:
```js
const user = {
	name: "Daniel",
	age: 26,
};

user.location; // returns undefined
```

Typescrip allows this kind of error to be picked up before it causes issues at runtime:
```ts
const user = {
	name: "Daniel",
	age: 26,
};

user.location;
//Error: Property 'location' does not exist on type '{ name: string; age: number; }'.
```