# Few ways to reverse a string

### First (easiest):

```js
let myString = 'hello world!'
let reversedString = myString.split('').reverse().join('')
console.log(reversedString) // '!dlrow olleh'
```

### Second

```js
const str = 'hello world!'
let arr = str.split('')

for (let i = 0; i < Math.trunc(arr.length / 2); i++) {
  let deletedSymbol = arr[i]
  arr[i] = arr[arr.length - (i + 1)]
  arr[arr.length - (i + 1)] = deletedSymbol
}

const reversedString = arr.join('')

console.log(reversedString) // '!dlrow olleh'
```

### Third

```js
const myString = 'hello world!'
const myArray = myString.split('')

for (let i = 0; i < myArray.length; i++) {
  myArray.splice(i, 0, myArray.pop())
}

const reversedString = myArray.join('')

console.log(reversedString) // '!dlrow olleh'
```

### Fourth (recursion)

```js
let reversedArray = []
let i = 0

function reverseString(str) {
  reversedArray.unshift(str[i++])

  if (i < str.length) {
    return reverseString(str)
  } else {
    return reversedArray.join('')
  }
}

reverseString('hello world!') // '!dlrow olleh'
```
