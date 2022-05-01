# Ch 8. CSS 속성
## 01. 개요
박스 모델, 글꼴, 문자, 배경, 배치, 플렉스(정렬), 전환-전후상태를 애니메이션처리하는 것, 변환, 띄움(float), 애니메이션, 그리드, 다단, 필터(blur, grayscale 흑백, reverse 반전)

## 02. 너비(width, height)
요소의 가로,세로 `너비`

auto 기본값(요소에 이미 들어있는 속성의 값) : 브라우저가 너비를 계산  
단위 : px, em, vw 등 단위로 지정

- span : 대표적인 인라인요소, 본질적으로 아무것도 나타내지 않는, 콘텐츠 영역을 설정하는 용도

- width, height : auto  
포함한 콘텐츠 크기만큼 자동으로 줄어듬

- div : 대표적인 블록 요소
- width : auto : 부모 요소의 크기만큼 자동으로 늘어남
height : 포함한 콘텐츠 크기만큼 자동으로 줄어듬

- max-width, max-height
 : none 기본값, 최대 너비 제한 없음, 단위로 지정

 - min-width, min-height
 : 0 이상값, 최소너비 제한없음

 ## 03. CSS 단위
px 픽셀  
% 상대적 백분율  
em 요소의 글꼴 크기 (1em = 1 font-size)  
rem 루트(즉,최상위) 요소(html)의 글꼴크기  
vw 뷰포트 가로 너비의 백분율  
vh 뷰포트 세로 너비의 백분율

## 04. 요소의 외부 여백(margin)
`단축 속성`
margin top,bottom,left,right  
margin top,bottom / left,right  
margin top / left,right / bottom  
margin top / right / bottom / left 시계방향  

음수를 사용할 수 있음.(겹쳐짐)  
가로(세로) 너비가 있는 요소의 가운데 정렬에 활용함.  
기본값 : 0(외부여백 없음)  
auto : 브라우저가 여백을 계산  
단위로 지정

- 개별속성 : margin-방향

## 05. 내부 여백(padding)
요소의 `크기가 커짐`  
% : 부모 요소의 `가로 너비`에 대한 비율로 지정

## 06. 테두리선(border)과 색상 표현
border: 선-두께 선-종류 선-색상;  
border-width, border-style, border-color  
요소의 `크기가 커짐`.  
요소의 `테두리 선`을 지정하는 `단축 속성`  

border-width : 단축속성  
border-style : 단축속성
  - 기본값 : none 선없음  
  solid 실선(일반선)  
  dashed 파선 ---

border-color : 단축속성
 - 기본값 : black, 색상, transparent 투명

색상표현
 - 색상이름 _red_
 - `Hex 색상코드` - 16진수 색상 _#000_
 - RGB : 빛의 삼원색 _rgb(255,255,255)_
 - RGBA : 빛의 삼원색 + 투명도 _rgba(0,0,0,0.5)_

 요소의 테두리 선을 지정하는 기타 속성들  
 border-방향  
 border-방향-속성  
 border-top-width /style / color

 ## 07. 모서리 둥글게(border-radius)
 요소 모서리를 `둥글게 깎음`
- 기본값 : 0 둥글게 없음

border-radius: 0 10px 0 0;  
최상단 왼쪽지점부터 시계방향 순서

## 08. 크기 계산(box-sizing)
요소의 `크기 계산 기준`을 지정

 - 기본값 : content-box 요소의 내용으로 크기 계산  
 - border-box : 요소의 내용 + padding + border로 크기 계산  
** 주의 : margin 은 포함하지않음  

box-sizing:border-box  
box-sizing:content-box(기본값)

## 09. 넘침 제어(overflow)
요소의 크기 이상으로 `내용이 넘쳤을 때`, `보이는 것을 제어하는 단축 속성`  

- 기본값 : visible -넘친 내용을 그대로 보여줌  
hidden : 넘친내용을 잘라냄  
auto : 넘친 내용이 있는 경우에만 잘라내고 스크롤바 생성

요소의 크기 이상으로 내용이 넘쳤을 때, 보여지는 것을 제어하는 `개별 속성들`
overflow-x / y

## 10. 출력특성(display)
: 요소의 화면 `출력 특성`
- 기본값 :
 각 요소에 이미 지정되어 있는 값  
 block : 상자(레이아웃)요소, div, 가로, 세로값을 가짐.  
 inline : 글자요소, span  
 inline-block : 글자+상자 요소  

 따로 지정해서 사용하는 값  

 flex : 플렉스 박스(1차원 레이아웃)  
 grid : 그리드 (2차원 레이아웃)  
 none : 보여지는 특성 없음, 화면에서 사라짐

 table, table-row, table-cell 등..  


## 11. 투명도
opacity - 기본값 1 불투명, 0~1 사이 소수점 숫자
- 0 생략하여 표현 가능

## 12. 글꼴
- font-style : 글자의 `기울기`  
기본값 : normal  
italic : 이탤릭체

- font-weight : 글자 `두께 가중치`  
기본값 : normal, 400  
bold, 700 : 두껍게  
100 ~ 900

- font-size : 글자 `크기`  
기본값 : 16px

- line-height : `한 줄의 높이`, 행간과 유사  
숫자 : 요소의 `글꼴 크기의 배수`로 지정  

- font-family : `글꼴(서체)` 지정

font-family : 글꼴1, "글꼴2", ... **글꼴계열**;  
글꼴계열은 필수로 작성  

sans-serif : 고딕체 계열  

## 13. 문자
color : 글자의 `색상`  
기본값 : rgb(0,0,0) 검정색  

text-align : 문자의 `정렬 방식`  
기본값 : left  
right, center

text-decoration  : 문자의 장식(`선`)  
기본값 : none(장식 없음)  
underline(밑줄), line-through(중앙선)

text-indent : 문자 `첫 줄의 들여쓰기`(내어쓰기도 음수입력으로 가능) 
기본값 : 0  

## 14. 배경  
background-color : 요소의 `배경 색상`  
기본값 : transparent 투명  

background-image : 요소의 `배경 이미지 삽입`  
기본값 : none  
url("경로")  

background-repeat : 요소의 `배경이미지 반복` 
기본값 : repeat  이미지를 수직, 수평 반복  
repeat-x 수평축 반복  
repeat-y 수직축 반복  
no-repeat 이미지 반복없음  

background-position : `배경이미지 위치`  
방향 : top, bottom, left, right, center 방향  
단위 x축으로부터 y축으로부터  

background-size : `배경이미지 크기`  
기본값 : auto(실제 크기)  
단위,  
cover  : 가로 및 세로 중 더 긴 너비에 맞춰짐  
contain  : 가로 및 세로 중 더 짧은 너비에 맞춰짐  

background-attachment : `배경 이미지 스크롤 특성`  
기본값 : scroll -이미지가 요소를 따라서 같이 스크롤  
fixed : 이미지가 뷰포트에 고정, 스크롤안됨  

## 15. 배치
position : 요소의 `위치 지정 기준`  
top, bottom, left, right, z-index 음수 사용 가능  
기본값 : static 기준없음  
relative : 요소 `자신`을 기준  
absolute : 위치 상 `부모` 요소 기준
fixed : `뷰포트` 기준  

요소의 각 방향별 거리 지정  
top, bottom, left, right  
기본값 : auto  

부모요소에 position : relative 를 선언해준 상태에서 자식 요소를 position : absolute를 해주어야 부모요소와 상호작용함

position : static 되어 있는 요소는 상호작용하지 않음을 의미함

요소쌓임 순서(stack order)  
어떤 요소가 사용자와 더 가깝게 있는지(위에 쌓이는지) 결정  

1. 요소에 position 속성의 값이 있는 경우 위에 쌓임(기본값 static 제외)
2. 1번 조건과 같은 경우, z-index 속성의 숫자 값이 높을 수록 위에 쌓임.
3. 1번, 2번조건까기 같은 경우, HTML의 다음 구조일 수록 위에 쌓임.

z-index : 요소의 쌓임 정도를 지정  
- 기본값 : auto(0) 부모 요소와 동일한 쌓임 정도  
숫자 : 숫자가 높을 수록 위에 쌓임  

요소의 display가 변경됨  
`position 속성의 값으로 absolute, fixed가 지정된 요소는, display 속성이 block으로 변경됨.`

## 18. 플렉스(정렬)
1차원 레이아웃을 만드는 개념  
flex container : 부모요소  
 - display:flex 선언된 요소  
display, flex-flow, flex-direction, flex-wrap, justify content, align-content, 
align-items 속성  

flex items : 자식요소
 order, flex, flex-grow, flex-shrink, flex-basis, align-self 속성

display 속성 : flex container 화면 출력 특성  
flex : `블록 요소`와 같이 flex container 정의  
inline-flex : 인라인 요소처럼 동작하는 flex container 정의  

* 블록요소는 width : auto 가로로 최대로 표현하려고 함.  

flex-direction : 주 축(main axis)을 설정  
  기본값 : row(행축 좌->우)  
  row-reverse : 행축 (우->좌)

row 행 (수평)  
column 열 (수직)

* 교차 축 (cross-axis)  
시작점 : flex-start  
끝점 : flex-end

flex-wrap  
: flex items 묶음(`줄 바꿈)` 여부  
기본값 : nowrap 묶음(줄바꿈) 없음  
wrap : 여러줄로 묶음

justify-content  : 주축의 정렬방법  
기본값 : flex-start : flex items를 시작점으로 정렬  
flex-end : 아이템을 끝점으로 정렬  
center : 아이템을 가운데 정렬  

align-content : `교차축의 여러줄` 정렬방법  
기본값 : stretch : 아이템을 교차축으로 늘림  
flex-start / flex-end / center  

align-items : `교차 축의 한 줄` 정렬 방법  
기본값 : stretch : 아이템을 교차 축으로 늘림  
flex-start, flex-end, center  
***
flex item에 쓰는 속성들
***
order : flex item 순서  
기본값 : 0 (순서없음)  
숫자 : 숫자가 작을수록 먼저

** HTML 요소를 수정하지 않고도 요소의 순서를 변경할 수 있는 장점이 있음.** 

flex-grow : flex item의 `증가` 너비 비율  
기본값 : 0 증가 비율 없음  
숫자

flex-shrink : flex item의 `감소` 너비 비율  
기본값 : `1`- flex container 너비에 따라 감소 비율 적용  
숫자

flex-basis : flex item의 공간 배분 전 `기본` 너비  
기본값 - auto : 요소의 content 너비  
단위

아이템들의 flex-basis값을 0으로 하면 요소 컨텐트 길이와 관계없이 flex-grow 값을 요소에 적용할 수 있음.  

## 21. 전환
transition : 속성명 `지속시간` 타이밍함수 대기시간;  

요소의 전환(시작과 끝) 효과를 지정하는 `단축 속성`

transition-property  
transition-duration  
transition-timing-function  
transition-delay  

transition-property : 전환 효과를 사용할 `속성이름`을 지정  
기본값 : all (모든 속성에 적용)  
속성이름 : 전환 효과를 사용할 속성 이름 명시  

transition-duration : 전환효과 지속시간  

transition-timing-function : 전환 효과의 `타이밍(easing)함수`를 지정 

기본값 : ease : 느리게-빠르게-느리게  
linear 일정하게  
ease-in 느리게- 빠르게  
ease-out 빠르게- 느리게  
ease-in-out 느리게 빠르게 느리게  

transition-delay : 전환 효과가 몇 초 뒤에 시작할지 대기 
기본값 : 0

## 변환
요소의 `변환 효과`  
transform: 변환함수1 함수2 함수3 ...  
transform: 원근법 이동 크기 회전 기울임;

### 2D 변환함수
px  
translate(x,y) : 이동   
translateX(x)  x는 인수(argument)  
translateY(y)
scale(x,y) : 크기  

deg  
rotate(degree) : 회전(각도)  
skewX(x) : 기울임(x축)  
skewY(y) : 기울임(y축)  

### 3D 변환함수
px  
perspective(n) : 원근법(거리)  

deg  
rotateX(x) : 회전(x축)  
rotateY(y) : 회전(y축)

`원근법 함수`는 `제일 앞에 작성`해야 함!  
transform: perspective(500px) rotateX(45deg);  

perspective : 하위 요소를 관찰하는 `원근 거리`를 지정  
단위 : px 등 단위로 지정  
css 속성  

**차이점**
`속성`  perspective: 600px  
`관찰 대상의 부모`에 적용  
기준점 perspective-origin  

`함수`  transform:perspective(600px)  
`관찰 대상`에 적용  
기준점 transform-origin

backface-visibility : 3D 변환으로 회전된 요소의 `뒷면 숨김 여부` 

기본값 : visible 뒷면 보임  
hidden 뒷면 숨김

::q