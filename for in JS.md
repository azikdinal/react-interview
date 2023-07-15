to jump through object keys
```js
for(const k in objA){
	console.log(k)
}
```

to make array of object keys 
```js
const objA = {
	city:"Moscow",
	country:"Russia"
}
Object.keys(objA)
```
we can also use `for in` with arrays

```js
const arrayA = [1,2,3]

for(const key in arrayA){
	console.log(arrayA[key])
}

```

#js