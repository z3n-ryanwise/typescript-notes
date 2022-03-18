# Composing Types
- [[README]]

## Notes
- Create complex types by composing primitive ones

## Unions
Used to declare when a type is one of many types. 
```ts
function getLength(obj: string | string[]) {
	return obj.length;
}
```

This is commonly used to construct a series of accepted string or number literals,

```ts
type WindowStates = "open" | "closed" | "minimized";
type LockStates = "locked" | "unlocked";
type PositiveOddNumbersUnderTen = 1 | 3 | 5 | 7 | 9;
```

## Duck Typing
`````ts

interface Point {
 x: number;
 y: number;
}

function logPoint(p: Point) {
 console.log(`${p.x}, ${p.y}`);
} // logs "12, 26"

// const point is not of type Point defined above, but as it follows a similar shape, it is allowed
const point = { x: 12, y: 26 };
logPoint(point);


// again const point3 is not of type Point defined above, but as it follows a similar shape with the same subset of data, it is allowed.
const point3 = { x: 12, y: 26, z: 89 };
logPoint(point3); // logs "12, 26"

// again const rect is not of type Point defined above, but as it follows a similar shape with the same subset of data, it is allowed.
const rect = { x: 33, y: 3, width: 30, height: 80 };
logPoint(rect); // logs "33, 3"

// const color does not contain the correct subset of information
const color = { hex: "#187ABF" };
logPoint(color);
//Fails
//Argument of type '{ hex: string; }' is not assignable to parameter of type 'Point'. Type '{ hex: string; }' is missing the following properties from type 'Point': x, y
```
