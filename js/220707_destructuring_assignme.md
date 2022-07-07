### 배열 비구조화 할당
```js
let arr = ['one', 'two', 'three']
let one = arr[0]
let two = arr[1]
let three = arr[2]

console.log(one,two,three)
```
위 코드는 아래와 결과가 같다.
```js
let arr = ['one','two','three']
let [one, two, three] = arr
```

배열의 값을 순서대로 할당받아서 사용할 수 있는 것을  
`비구조화 할당` 이라고 함  

```js
let [one, two, three, four='four'] = ['one','two','three']
//할당받지 못하는 four에 기본값을 줄 수 있음
```

스왑
```js
let a = 10

let b = 20

let tmp = 0

tmp = a
a = b
b = tmp
console.log(a,b) // 20 10
```
```js
let a = 10

let b = 20

let tmp = 0

[a, b] = [b, a]
console.log(a,b) // 20 10
```
배열의 index를 이용해 할당

---

### 객체의 비구조화 할당
```js
let object = {one:'one', two:'two', three:'three'}

let one = object.one;
let two = object.two;
let three = object.three

console.log(one, two, three)
```
```js
let object = {one:'one', two:'two', three:'three'}

let {name:myName, one, two, three, abc='four'} = object
console.log(one, two, three, myName)
// name이라는 키값을 기준으로 value를 myName이라는 변수이름에 
//할당하여  사용하는 것도 가능하다.
// 할당되지 않은 abc 값을 할당받기 위한 기본값 설정이 가능함
```

객체(object)의 `key`값을 이용해 할당함

