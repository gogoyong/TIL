# PT1스벅 CH4. 웹에서 시작하기

## 02. 브라우저 스타일 초기화

## 03. Emnet
Emmet 은 CSS 선택자를 활용해 사용하는 기능
* 곱하기, {} 내용삽입, $ 순서대로 숫자입력
- Emmet에서만 지원하는 기능

# Ch 5. HTML 개요

## 01. 기본문법
요소(element)
<태그>내용</태그>
시작태그, 내용, 종료태그

## 02. 부모와 자식 관계 이해
부모요소가 자식요소를 
시작태그, 종료태그로 감싼다

부모요소 시작태그  
  (들여쓰기, indent, tab) 자식요소  
종료태그

내어쓰기 outdent, shift tab

상위(조상)요소 : 부모요소를 포함하는, 나를 감싸고있는 모든 요소

하위(후손)요소 : 내가 감싸는
모든 요소

## 03. 빈 태그(empty tag)
- meta, img, input, br 태그 등  
- <태그/>
: 빈 태그임을 명확히 표현함

<태그 속성="값'>
기능의 확장
- 빈 태그는 대부분 필수속성이 필요

``` html
<input type="text"/>
<input type="checkbox"/>
```

## 04. 글자와 상자
요소가 화면에 출력되는 특성
- inline 요소 : 글자를 만들기 위한 요소
- block 요소 : 상자(레이아웃)를 만들기 위한 요소

```
<span>Hello</span>
<span>World</span>
```
span 대표적인 인라인 요소.
본질적으로 아무것도 나타내지 않는
콘텐츠 영역을 설정하는 용도
- 요소가 수평으로 쌓임

포함한 콘텐츠 크기만큼 자동으로 줄어듬. (글자 요소)

``` html
<span style="width:100px">Hello</span>

글자 요소는 가로, 세로 크기를 지정할 수 없으므로 반응 없음
```
width, height 요소의 가로,세로 너비를 지정하는 CSS 속성

```html
<span style="margin:20px 20px;">Hello</span>
```
글자요소의 좌, 우 여백은 가능, 상, 하 여백은 불가능

margin, padding : 요소의 외부, 내부여백을 지정하는 CSS 속성

```
<span><div></div></span>
불가, 글자(인라인) 내부에 상자(블록) 넣을 수 없음

<span><span></span></span>
가능
```

div : 대표적인 `블록 요소`
본질적으로 아무것도 나타내지 않는 콘텐츠 영역을 설정하는 용도
- 요소가 수직으로 쌓임

- `가로너비`는 부모요소의 크기만큼 `자동으로 늘어남`
- 세로너비는 포함한 콘텐츠 크기만큼 자동으로 줄어듬

width, height, marin, padding
모두 가능

블록 요소는 자식으로 블록 포함 가능
블록 요소는 자식으로 인라인요소도 포함 가능함

---

# Ch 6. HTML 핵심정리
## 01. 핵심 요소 정리
- div (division) 특별한 의미가 없는 구분을 위한 요소. `블록(상자) 요소`
- h (heading) 제목을 의미하는 요소. `블록(상자) 요소` 숫자가 작을수록 더 중요한 제목
- p (paragraph) 문장, **`블록(상자)요소`**
---
- img (image) - `인라인(글자)요소`
src source 경로  
alt alternate 대체텍스트

- ul (unordered list), 순서 불필요 목록 집합, `블록(상자)요소`
- li (list item) - 목록 내 각 항목, `블록(상자)요소`

- a (anchor) - 다르거나 같은 페이지로 이동하는 하이퍼링크를 지정하는 요소, `인라인(글자)요소`
href(hypertext reference) : URL  
target : 링크URL의 표시(브라우저 탭) 위치 (_blank)

- span : 특별한 의미가 없는 구분을 위한 요소, `인라인(글자) 요소`, 사용예) 글자 색입히기 위해 범위 지정할때 사용

- br(break) : 줄바꿈 요소, `인라인(글자)요소`

- input : 사용자가 데이터를 입력하는 요소. `인라인(글자)요소`, `블록(상자)요소`
inline-block  
type : 입력받을 데이터의 유형  
type="text"
value : 미리 입력된 값(데이터)  
placeholder : 사용자가 입력할 값(데이터)의 힌트  
disabled : 입력요소 비활성화

  type="checkbox" : 사용자에게 체크 여부를 입력 받음
```
<label>
  <input type "checkbox" checked /> Banana
</label>

checked 미리 체크가 되어있음 선택
```

  type="radio" 체크 여부를 그룹에서 1개만 입력받음  
  name="그룹이름"

table : `테이블요소`, 표 요소, 행(row)과 열(column)의 집합

```
<table>
  <tr><!-- table row -->
    <td><!--  table data -->A</td><td>B</td>
  </tr>
  <tr>
    <td>C</td><td>D</td>
  </tr>
</table>
    
```

## 03. 주석
수정사항이나 설명 등을 작성
컨트롤 /

## 04. 전역 속성
속성 : 태그 기능을 확장하여 주는 것
- title="설명"
- style="스타일" : 요소에 적용할 스타일(CSS)을 지정

CSS 선언방법
- link
- style태그
- <태그 style="스타일"></태그>

- class="이름" : 요소를 지칭하는 **중복 가능**한 이름

- id="이름" : 요소를 지칭하는 **고유**한 이름

- data-이름="데이터" : 요소에 **데이터**를 지정

- defer 속성 : HTML 구조가 준비된 후에 JS를 해석하겠다는 의미
script 요소 속성


