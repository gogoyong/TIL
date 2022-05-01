# 0415 pt1 스타벅스 ch3무작정 시작하기
## 01. Doctype(DTD)  
< !DOCTYPE html >  
문서의 HTML버전을 지정
document type definition

웹브라우저가 HTML버전을 해석할 수 있도록 알려주는 용도

## 02. HTML HEAD BODY
HTML : 문서의 전체 범위  
HEAD : 문서의 정보를 나타내는 범위
 - 웹 브라우저가 해석해야 할 제목, 설명, 파일위치, 스타일(CSS)같은,
 웹 페이지의 `보이지 않는 정보`를 작성하는 범위  

BODY : 문서의 구조를 나타내는 범위
사용자 화면을 통해 보여지는 로고, 헤더, 푸터, 내비게이션, 메뉴, 버튼, 이미지 같은 웹페이지의 `보여지는 구조`를 작성하는 범위

## 03. CSS, JS 연결하기
head 하부 link 태그 href="css"삽입

script src="js" 삽입

## 04. 정보를 의미하는 태그
head 하부 style태그 삽입하는 방법도 있음.
HTML 문서 안에서 작성하는 경우 사용

link 태그 : 외부 문서를 가져와 연결할 때 사용
(대부분 css파일)

rel : 가져올 문서와 `관계` relationship  
href : `경로`
hypertext reference

- link rel="stylesheet" href="./main.css"  
- link rel="icon" href="./favicon.png"

meta name 정보의 종류 content 정보의 값  
name="author" content="HEROPY"

name="viewport" content="width-device width, initial-scale=1.0"

charset character set 문자인코딩방식

## 05. 이미지 출력하기
img 태그
alt 대체텍스트

## 06. 상대경로 vs 절대 경로
상대 경로 ./(생략가능) 주변  
../ 상위 폴더

절대 경로 http 원격  
/ 최상위 경로

localhost : 우리  
프로젝트  
루트폴더

## 07. 페이지를 나누고 연결하기

CSS 선택자 :
CSS 스타일을 어떤 요소에 적용할지를
선택하는 일종의 규칙

