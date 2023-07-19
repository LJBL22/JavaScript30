# 04 Array Cardio Day 1: [DEMO](https://ljbl22.github.io/JavaScript30/04_array_cardio_1/)

### Codes

```JavaScript
const sortedArr = inventors.toSorted((a, b) => a.year - b.year);
  console.table(sortedArr);
```

## :writing_hand: Highlights

- `console.table` for showing neat result

- Array.prototype.sort() [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort#sorting_array_of_objects)

  ```JavaScript
  // sort by value
  items.sort((a, b) => a.value - b.value);
  ```

- **ECMA 2023** Array.prototype.toSorted() [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort#sorting_array_of_objects)

  - new method after 2023 May.
  - copy array first then mutate

- Array.prototype.reduce() [MDN](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Global_Objects/Array/reduce)
  - :question: why The "reduce" method is named as such because it is designed to reduce or consolidate a list of values into a single value. It is commonly used in programming languages and frameworks to perform cumulative operations on a collection of elements.

## :page_facing_up: reference and discussion

- [.toSorted() works only in a browser](https://stackoverflow.com/questions/76006398/tosorted-works-only-in-a-browser)
