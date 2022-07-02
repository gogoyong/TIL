협업을 하다보면 PR에 대한 리뷰를 위해 
본인 로컬로 당겨오기를 할 필요가 생기는데 
방법을 정리하고자 간단하게 포스팅합니다.

## 1. PR 당겨오기  
1. github 레포에 들어가 pull request 탭에 들어간다.
2. 당겨오고자 하는 PR의 번호 (예를 들면 #23이라고 표시되어 있으면 23번)를 기억한다.
3. 터미널을 열어 당겨오고자 하는 로컬 폴더인지 확인하고 맞으면 가져고오자 하는 원본원격 저장소 별명을 확인한다.
```git
$ git remote -v
```
(가져오고자 하는 원본원격 레포의 별명이 origin이라고 가정) 

4. 터미널을 열어 아래와 같이 명령을 입력한다.
```git
$ git pull origin pull/23/head:pr23
```
origin이라는 원격저장소의 Pull and request #23번 파일을  
본인 로컬저장소의 pr23이라는 이름의 branch로 가져온다는 의미입니다.

---
## 2. PR 되돌리기
당겨와진 PR을 확인 완료하였으면,
당겨오기 직전 상태로 되돌리고 싶은 경우가 있을 수 있는데 그러면
이와 같이 하면 됩니다.

```git
$ git reset --hard ORIG_HEAD
```
---
## 추가) 특정한 상태로 되돌리기

1. 터미널에서 작업할 폴더인지를 확인한 후 아래와 같이 입력
```git
$ git reflog
```
위와 같이 입력하면 HEAD@{13} 이런 형식으로 작업한 커밋들을 확인할 수 있는데
여기서 되돌리고자 하는 상태의 번호를 확인합니다.

2. HEAD@{13} 이 상태로 되돌리고자 한다면 아래와 같이 명령을 입력
```git
$ git reset --hard HEAD@{13}
```

끝입니다.

감사합니다.

---
참고 
[GitHub의 Pull Request를 로컬로 가져오기](https://blog.outsider.ne.kr/1204)
[git. commit, add, pull, merge 취소](https://mrgamza.tistory.com/593)
[Git pull 받은 내역 rollback(복구) 하기](https://zzang9ha.tistory.com/330)
