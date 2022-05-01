# Ch 7. CSS 개요

## 01. 기본 문법, 주석

div {color: blue;}  
선택자 {속성: 값;}  

선택자 : 스타일을 적용할 대상(Selector)
속성 : 스타일의 종류(property)  
값 : 스타일의 값(value)  
{ : 스타일 범위의 시작  
} : 스타일 범위의 끝

/* 설명 작성 */
: 브라우저는 이 범위를 해석하지 않음 (컨트롤 슬래시)

## 02. 선언 방식
- 내장방식
 : 
 ```HTML
 <style>
  div<!-- 선택자 -->
    color...
  }
 </style>
 ```
  의 내용으로 스타일을 작성하는 방식

- 인라인 방식 : 요소의 `style 속성`에 직접 스타일을 작성하는 방식(선택자 없음)

 ```HTML
<div style="color:..."></div>
 ```

- 링크 방식 : 
```HTML
<link rel="stylesheet" href="./css/main.css/>
```
로 외부 CSS문서를 가져와서 연결하는 방식, `병렬`로 연결이 되어있는 방식, @import 방식에 비해 로딩되어 구현되는 속도가 빠름

- @import 방식 : CSS의 `@import 규칙`으로 `CSS문서 안에서` 또 다른 CSS문서를 가져와 연결하는 방식, `직렬`로 연결이 되어있는 방식

```CSS
@import url("./box.css");
div {
  ...
}
```
## 03. CSS 선택자
기본, 복합, 가상클래스, 가상요소, 속성

### 1. 기본
- `* : 전체 선택자(Universal Selector)

- 태그이름 : 태그 선택자(type selector)

- .클래스이름 : class selector

- #아이디이름 : ID selector

### 2. 복합
- 일치 선택자(Basic Combinator)
: 두개의 선택자를 동시에 만족하는 요소 선택
```html
<span class="orange">오렌지</span>
```
```css
span.orange {
  color: red;
}
```
태그.클래스

- 자식 선택자(Child Combinator)
: 선택자의 자식요소 선택
```html
<div>
  <ul>
    <li class="orange">오렌지</li><!-선택->
  </ul>
  <span class="orange">오렌지</span>
</div>
```
```css
ul>.orange{
  color: red;
}
```

- 하위(후손)선택자 (Descendant Combinator)
: 선택자의 하위요소를 선택, 띄어쓰기가 선택자의 기호

```html
<div>
  <ul>
    <li>사과</li>
    <li class="orange">오렌지</li><!-선택->
  </ul>
  <span class="orange">오렌지</span> <!-선택->
</div>
<span class="orange">오렌지</span>
```
```css
div .orange{
  color: red;
}
```

- **인접형제** 선택자(Adjacent Sibling Combinator) : 선택자의 `다음 형제요소 하나`를 선택
```html
<ul>
  <li class="orange">오렌지</li>
  <li>망고</li> <!-선택->
  <li>사과</li>
</ul>
```
```css
.orange + li {
  color: red;
}
```
- 일반형제 선택자(General Sibling Combinator) : 선택자의 `다음형제요소 모두`를 선택
```html
<ul>
  <li class="orange">오렌지</li>
  <li>망고</li> <!-선택->
  <li>사과</li> <!-선택->
</ul>
```
```css
.orange + li {
  color: red;
}
```
## 05. 가상클래스
:가상클래스  
행동을 했을때 나타나는 동작을 제어

hover : 마우스를 올렸을때 선택이 되는 요소를 제어

- HOVER 가상 클래스 선택자(Pseudo-Classes)  
선택자 요소에 `마우스 커서가 올라가 있는 동안` 선택

```css
a:hover {
  color:red;
}
```

- ACTIVE 가상 클래스 선택자  
선택자 요소에 `마우스를 클릭하고 있는 동안` 선택

- FOCUS  
선택자 요소가 `포커스`되면 선택  
input 등
```css
input:focus {
  background-color: orange;
}
```
div 같이 focus가 되지 않는 요소에 tabindex="-1"속성을 추가하면 focus시킬 수 있음

-FIRST CHILD  
선택자가 형제 요소 중 첫째라면 선택
```html
<div class="fruits">
  <span>딸기</span> <!-선택->
  <span>수박</span>
  <div>오렌지</div>
  <p>망고</p>
  <h3>사과</h3>
```
```css
.fruits span:first-child{
  color: red;
}
```

```css
.fruits div:first-child{
  ...
}
```
이 경우는 선택되는 div 형제요소가 없음

- LAST CHILD  
선택자가 형제 요소 중 막내라면 선택.
```css
.fruits h3:last-child{
  color:red;
}
```
사과 선택

- NTH CHILD  
선택자가 형제 요소 중 n째라면 선택

```css
.fruits *:nth-child(2){
  color: red;
}
```
수박 선택  

n은 0부터 시작(zero-based numbering)
```css
.fruits *:nth-child(2n){
  color:red;
}
```
짝수번째의 요소를 선택- 수박, 망고 선택  
2n+1 홀수번째의 요소 선택 -딸기, 오렌지, 사과  
n+2 두번째 선택자부터 선택

- NOT : 부정 선택자(Negation) 
선택자 XYZ가 아닌 ABC요소 선택  
ABC:not(XYZ)

```css
.fruits *:not(span){
  color:red;
}
```
오렌지, 망고, 사과 선택

- BEFORE: 가상 요소 선택자  
선택자 요소의 `내부 앞`에 내용을 삽입.  
ABC::before  
인라인(글자) 요소

```css
.box::before{
  content: "앞!";
}
```

- AFTER : 가상 요소 선택자  
선택자 요소의 내부 뒤에 내용을 삽입.

!! 가상요소 선택자 선택시 content 라는 속성과 같이 사용해야 함.

display: block 으로 하면 인라인 요소를 블록요소로 바꿔줄 수 있음.

- ATTR 속성 선택자(Attribute)  
속성을 포함한 요소 선택
```html
<input type="text" value="ABCD" disabled>
```
```css
[disabled]{
  color: red;
}
```


- ATTR=VALUE  [ABC="XYZ"]  
속성 ABC을 포함하고 값이 XYZ인 요소 선택
```css
[type="password"]{
  ...
}
```

## 09. 스타일 상속
상속되는 CSS 속성들 : 모두 글자/문자 관련 속성들(모든 글자/문자 속성이 상속되지는 않음)  
font-style(기울기),weight(두께),size,line-height(줄높이),font-family, color,text-align...

강제 상속  
상속되지 않는 속성을 상속시킴  
속성:inherit;

## 10. 선택자 우선순위
우선순위란 같은 요소가 여러 선언의 대상이 된 경우, 어떤 선언의 CSS 속성을 우선 적용할지 결정하는 방법

1. 점수가 높은 선언이 우선함!
2. 점수가 같으면, 가장 마지막에 해석된 선언이 우선함!

!important 중요도 : 1위  
inline 선언(태그 내 style속성) : 1000점  
#ID 선택자 : 100점  
.CLASS 선택자 : 10점
태그 선택자 : 1점
전체 선택자(*) : 0점  
상속 : 점수계산안됨

명시도

.not 부정선택자는 점수계산안됨
