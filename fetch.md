```js
const url = 'https://jsonplaceholder.typicode.com/todos/1'

const api = fetch(url) // return json obj

api
	.then(value => value.json()) // value == fetch return (json obj)
	.then(json => console.log(json))
	.catch(error => console.log(error))

```

#js #api