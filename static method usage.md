To use static methods we nee to declare it next way
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

	static unlike(){
		return like;
	}
}

const ex = new Comment("First")

console.dir(Comment.unlike)
```

#js #OOP