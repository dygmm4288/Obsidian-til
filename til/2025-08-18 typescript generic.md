---
title: "2025-08-18 typescript generic"
date: "2025-08-18"
status: in-progress
---

## 배운 것
T extends object를 선언하고 이 T의 key와 typeof 를 꺼내면 아래와 같은 방식으로 사용할 수 있지 않을까 했다.
```typescript
type Prop<T extends object> = {
	defaultValue?: T;
}

const useInput = <T extends object)({defaultValue}:Props<T>) => {
	const handleChange = (key: keyof T[keyof T], value: typeof T[keyof T]) => {};
};
```
제대로 지식이 없는 것 같다.
- `keyof T`:  keyof 연산자는 주어진 타입의 모든 public 키들의 유니온 타입을 반환한다.
```typescript
const myObject = {
	x: 1,
	y: 2,
	z: 3,
};

type keyofObject = keyof myObject; // "x" | "y" | "z"

```
- `typeof` T: Typescript의 typeof 연산자는 변수의 타입을 가져오는 데 사용한다. 
```typescript
const myObject = {
	x: 1,
	y: '2',
	z: false,
};

type typeofObject = typeof myObject // {x: number, y: string, z: boolean}
```
## 다음 할 일
- 