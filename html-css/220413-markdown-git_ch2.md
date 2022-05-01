0413 markdown
# 표(table)

hiddhi<br>
position 속성  
값 | 의미 | 기본값
--|:--:|--:
static | 기준 없음 | O
relative | 요소 자신 | X
absolute| 위치 상 부모 요소 | X

# 원시 HTML(Raw HTML)
동해물과 백두산이 

# 수평선(Horizontal Rule)
---
***
___


02 제목, 문장, 줄바꿈

제목
# = h1

줄바꿈
문장 제일 뒤에 띄어쓰기 두번 입력하거나
<br/> 추가하면 줄바꿈

_이탤릭_
**두껍게**
~~취소선~~ (~ : 틸드)
<u>밑줄</u>

목록
1.
띄어쓰기 네번(들여쓰기 두번)하면 하위 목록으로 추가됨

링크
[NAVER](https://naver.com "NAVER로 이동!")
"title"은 링크 위에 마우스를 갖다대면 나오는 설명

이미지
![HEROPY](https://heropy.blog/css/images/logo.png)

[![HEROPY](https://heropy.blog/css/images/logo.png)](https://naver.com)
이미지를 클릭하면 특정사이트로 이동할 수 있는 형태 출력

인용문
>
>>

강조
` `(그레이브 기호로 감싸줌)
VScode에서는 감싸줄 단어를 블록설정한 후 그레이브 기호 입력하면
바로 지정이 됨

블록코드 강조
코드 강조되어(검은 상자 내에) 표시
```html(언어)
<a href="">
```

```bash
$ git commit ...
```

표 
position 속성  
값 | 의미 | 기본값  << 머리열
--|:--:|--                 << 구분
static | 기준 없음 | O
relative | 요소 자신 | X

기본값은 왼쪽 정렬임
가운데 열은 가운데정렬이 됨
오른쪽 열은 오른쪽정렬이 됨

원시 HTML
밑줄 <span style="text-decoration: underline;"> </span>

수평선 
--- 또는 *** ___
