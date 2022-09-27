## ALTERNATE SOLUTIONS
### Solution 1
```js
const filteredList = watchList.filter(movie => {
    // return true it will keep the item
    // return false it will reject the item
    return parseFloat(movie.imdbRating) => 8.0;
}).map(movie => {
    return {
        title: movie.Title,
        rating: movie.imdbRating
    };
});
```

### Code Explanation:
First we `filter` through and only return the objects that meet the criteria.  In this case, the criteria is having an `imdbRating` of `8.0` or higher.

Then we `map` the objects to the desired format.

### Solution 2
```js
const filteredList = watchList.filter(movie => movie.imdbRating >= 8.0)
                              .map(movie => ({ title: movie["Title"], rating: movie["imdbRating"] }));
// Only change code above this line
console.log(filteredList);
```

### Solution 3
```js
// Only change code below this line
const filteredList = watchList.filter(({ imdbRating }) => imdbRating >= 8.0)
                              .map(({ Title: title, imdbRating: rating }) => ({ title, rating }));
// Only change code above this line
console.log(filteredList);
```

## REFERENCE LINKS:
- MDN: [`Array.prototype.filter()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/filter)
- MDN: [`Array.prototype.map()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)
- MDN: [Destructuring assignment](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)

