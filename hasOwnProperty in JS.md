To check have instance key  we need to use `hasOwnProperty` method
```js
class Comment{
	constructor(text){
		this.text = text // created new attr with value of parametr
		this.likes = 0 // created new attr and gave him a value 0
	}

	like(){
		this.likes += 1; // plus to like 1
		this.asnwers = 0 // created new attr
	}
}

const ex = new Comment("First")
ex.like()

console.dir(ex.hasOwnProperty('likes'))//true
```