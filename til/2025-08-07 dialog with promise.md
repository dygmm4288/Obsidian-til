---
title: "2025-08-07 dialog with promise"
date: "2025-08-07"
status: in-progress
---

## 배운 것
- **Quasar `$q.dialog`는 Promise를 반환하지 않는다**
	- `onOk`, `onCancel` 등 콜백 패턴이므로 자연스러운 Promise를 위해서는 직접 래핑 
- **Promise를 감싸서 async/await 또는 then 체인을 구현한다**
```javascript
const __ = new Promise((res) => {
	this.$q.dialog({
		component: Component,
	}).onOk(yes => {
		if (!yes) return;
		res(yes);
	});
}).then((res) => {
	this.$q.dialog({
		component: Component2,
	}).onOk(yes => {
		if(!yes) return;
		res(yes);
	})
}).then(res => {
	// do...
});
```
- Promise를 자연스럽게 타려면 직접 promise wrapping 한다.
```javascript
const callComponent = () => {
	const vm = this; 
	return new Promise((res, rej) => {
		vm.$q.dialog({
			component: Component
		}).onOk(res).onCancel(() => rej('취소'));
	});
};

const callComponent2 = () => {
	const vm = this;
	return new Promise((res, rej) => {
		vm.$q.dialog({
			component: Component2,
		}).onOk(res).onCancel(() => rej('취소'));
	});
};


const call = async () => {
	try {
		const yes = await callComponent();
		const yes2 = await callComponent2();
	} catch(err) {
		console.error(err);
	}
};
call();
```
## 다음 할 일
-  [[2025-08-07 dialog promise wrapping]]