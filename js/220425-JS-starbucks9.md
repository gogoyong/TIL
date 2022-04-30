# Ch. 9 JS 선행
## 01. 개요
### 표기법
dash-case(kebab-case): HTML, CSS    
snake_case : HTML, CSS  
`camelCase` : JS  
ParcelCase :JS  

Zero-based Numbering : `0부터` 번호매기기

주석 comments
// 한 줄 메모
/**  
 * 여러 줄  
 * 메모1  
 * 메모2  
 */  

 ## 02. 데이터 종류(자료형)
 string, number, boolean, undefined, null, object, array

 // String(문자데이터)
 // 따옴표를 사용합니다.
```js
let myName = 'HEROPY"
let hello =`Hello ${myName}?!`
```
백틱 기호는 다른 데이터를 보간해서 중간에 삽입할 수 있게 해줌  

// number(숫자 데이터), 정수, 부동소수점 숫자를 나타냄
// Boolean, true, false 두 값밖에 없는 논리데이터
// Undefined, 값이 할당되지 않은 상태
```js
let obj = {abc:123};
console.log(obj.abc); // 123
console.log(obj.xyz); // undefined
```

// Null 어떤 값이 `의도적으로` 비어있음을 의미
```js
let empty = null;
console.log(empty); // null
```
// Object(객체데이터), 여러 데이터를 Key:Value형태로 저장함, { }
```js
let user ={
  name: 'HEROPY',
  age: 85
};
console.log(user.name); // HEROPY
```
//Array(배열데이터), 여러 데이터를 순차적으로 저장함.
[]

## 03. 변수, 예약어
### 변수  
 : 데이터를 저장하고 참조(사용)하는 데이터의 이름  
var, `let, const`  
// 재사용이 가능!
// 변수 선언!
```js
let a = 2;
let b = 5;
console.log(a+b); // 7
```

// 값(데이터)의 재할당 가능!
```js
let a=12;
console.log(a); // 12
a=999;
console.log(a); //999
```
`const는 값(데이터)의 재할당 불가!`

예약어 :  
특별한 의미를 가지고 있어, 변수나 함수 이름으로 사용할 수 없는 단어  
ex) this, if, break 등  
(변수 선언시 SyntaxError 발생함)

## 04. 함수
특정 동작(기능)을 수행하는 일부 코드의 집합(부분)  
 
```js
// 함수 선언 
function helloFunc(){
  // 실행코드
  console.log(1234);
}

// 함수 호출
helloFunc(); //1234

function returnFunc(){
  return 123;
}
let a = returnFunc();
console.log(a); //123
```
```js
function sum(a,b) { // a와 b는 매개변수(parameters)
  return a+b;
}
let a = sum(1,2); // 1과 2는 인수(Arguments)
```
```js
// 기명(이름이 있는) 함수, 함수 선언
function hello(){
  console.log("hello~");
}
// 익명(이름이 없는) 함수, 함수 `표현`
let world = function(){
  colsole.log('World~');
}
```
```js
// 객체 데이터
// method : 속성 부분에 함수가 할당된 것
```
## 05. 조건문
조건의 결과에 따라 다른 코드를 실행하는 구문  

## 06. DOM API  
document object model, application programming interface  
HTML 명령, JS로 HTML을 제어할때 사용  

HTML 요소에 적용할 수 있는 메소드 : `addEventListener()`
- 인수를 추가 가능
- 이벤트(상황), `핸들러`(실행할 함수)
```js
boxEl.addEventlistener('click', function (){
  console.log('Click~!')
})
```

요소의 클래스 정보 객체 활용 : `classList`
```js
const boxEl = document.querySelector('.box');
boxEl.classList.add('active');
let isContains = boxEl.classList.contains('active');
console.log(isContains); //true

borEl.classList.remove('active');
isContains = boxEl.classList.contains('active');
console.log(isContains); //false
```

HTML 요소 모두 검색/찾기 : `querySelectorAll`  

```js
// 찾은 요소들 반복해서 함수 실행!
// 익명 함수를 인수로 추가!
boxEls.forEach(function () {});
// 반복중인 요소, 반복중인 번호
boxEls.forEach(function (boxEl, index) {});
boxEls.forEach(function (boxEl, index){
  boxEl.classList.add(`order~${index +1}`);
  console.log(index.boxEl);
})
```
getter : 값을 `얻는` 용도  
setter : 값을 `지정하는` 용도

## 08. method chaining
메소드를 점(.)으로 붙여서 한번에 써 주는 것  
split : 문자를 인수 기준으로 쪼개서 배열로 변환  
reverse: 배열을 뒤집기  
join : 배열을 인수 기준으로 문자로 병합해 반환.  

```js
const a = 'Hello~';
const b = a.split('').reverse().join(''); // method chining
console.log(a); //Hello~
console.log(b); //~olleH
```

## 09. QnA
camelCase : theQucikBrownFox
```js
let fruits =['a','Banana','Cherry']  
console.log(fruits[1]);
```
