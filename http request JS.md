In case to make http requests we can use `fetch()` and `XMLHttpRequest()` functions.

Example using `fetch()`:
```js
const api = async () => {  
let url = 'https://date.nager.at/api/v2/publicholidays/2020/US';  
let response = await fetch(url);  
let commits = await response.json(); // читаем ответ в формате JSON  
  
console.log(commits[0].date);  
}  
  
api()
```