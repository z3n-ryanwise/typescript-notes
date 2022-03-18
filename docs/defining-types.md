# Defining Types
- [[README]]

## Notes
- Types are implicetly implied unless instructed otherwise.

## Types
### Primatives
- `boolean`
- `bigint`
- `null`
- `number`
- `string`
- `symbol`
- `undefined`

### TS
- `any` : Allow any type
- `unknown`: Must be declared on use
- `never`: Should not be used/happen
- `void`: A function that returns either nothing, or `undefined`

## Inferred Types v explicit types

Inferred:
```ts
const user {
  name: "Hayes",
  id: 0,
};
```
Explicit:
```ts
interface User {
  name: string;
  id: number;
}

const user: User {
  name: "Hayes",
  id: 0,
}
```

This is more boilerplate, but it means that a user object cannot be constructed unless it conforms to the template.
```ts
// Here username is not defined in the interface, and thus an error will be thrown
const user: User {
  username: "Hayes",
  id: 0,
}
```

This same principle can be used for constructors
```ts
interface User {
name: string;
id: number;
}

class UserAccount {
	name: string;
	id: number;

	constructor(name: string, id: number) {
		this.name = name;
		this.id = id;
	}
}

const user: User = new UserAccount("Murphy", 1);
```

## Define paramaters and return types

```ts
function getAdminUser(): User {
	//...
}

function deleteUser(user: User) {
	// ...
}
```