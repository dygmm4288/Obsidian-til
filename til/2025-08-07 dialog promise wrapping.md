---
title: 2025-08-07 dialog promise wrapping
date: 2025-08-07
status: in-progress
---

## 배운 것
- **dialog를 promise로 wrapping 해주는 공통함수를 사용하면 더 효과적으로 사용 가능하다**
```javascript
// wrapping 해주는 함수
const dialog_promise = (vm, dialog_args) => {
	return new Promise((res, rej) => {
		vm.$q.dialog(dialog_args).onOk(res)
		.onCancel(() => rej('cancel'))
		.onDismiss(() => rej('dismiss'));
	});
}

// 사용예제
try {
	const yes = await dialog_promise(this, { component: Component });
	const yes2 = await dialog_promise(this, { component: Component2 });
} catch(err) {
	if (err === 'cancel') return;
	if (err === 'dismiss') return;
	console.error(err);
}
```

## 다음 할 일
- promise 내부에서 promise를 반환할 경우 기다리는지 확인 