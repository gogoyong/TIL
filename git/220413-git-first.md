0413 git강의1

Kernel : 하드웨어와 응용프로그램을 이어주는
운영체제의 핵심 시스템소프트웨어
Shell : Kernel과 사용자를 이어주는 소프트웨어

ls : list segments
ls -a : 숨김파일 보여주기(all files)
ls -l : line by line 한줄한줄 상세정보
ls -al : 숨김파일까지 line by line

- : flag이며 combination이 가능함

cd : change directory
tab키 누르면 자동완성
cd : 최상단
cd . : 현재
cd .. : 상위
mkdir : make directory

touch 파일명 : 파일생성
&& : 명령을 동시에 사용할 때 사용
mv 파일 폴더: 파일을 폴더로 이동(move)

딜리미터(구분자) - 여기서는 띄어쓰기
mv ../server.js ./
상위 폴더에 있는 파일을 현재폴더로 이동
mv ../server.* ./
상위 폴더에 있는 server이름을 가진 모든파일을
현재폴더로 이동

cp 파일 폴더 : 파일을 폴더에 사본으로 생성
cp hello.md ./hello-copy.md : 파일을 파일로 사본으로 생성

remove 제거
delete 삭제

rm -r 폴더명 : 폴더삭제

sudo : superuser do(관리자 권한 실행)
mv 파일1 파일2 : 이름변경

vim 파일 : 파일 에디터로 열기

## Vim mode

- normal mode : press escape on any mode
- insert mode : press i on normal mode
- visual mode : priss v on normal mode
- command mode : press : on normal mode
  - commands : :w, :wq, :q, :q!

## Markdown syntax

- hashtag(#) : heading text <h1></h1>
- hyphen(-) : Unordered list <ul><li></li></ul>
- numbers(1.) : Ordered list <ul><li></li></ul>
- plain text : paragraph <p></p>

:wq -write and quit (저장, 종료)
:q! -저장안하고 종료

cat 파일명 : 파일읽기(catenate)

git 
vcs (version control system) 
 == scm (source code management)
 < scm (software configuration management : 형상관리)

git의 장점
-소스코드 주고받기 없이 동시작업이 가능해져 생산성이 증가한다
-수정내용은 commit단위로 관리, 배포, 원하는시점으로 checkout 가능
-새로운 기능 추가는 branch로 개발하여 편안한 실험이 가능하며,
성공적 개발 완료후 merge하여 반영
-인터넷이 연결되지 않아도 개발 가능

git objects
blob : 파일 하나 내용에 대한 정보/피사체
tree : blob이나 subtree의 메타데이터(디렉토리 위치, 속성, 이름)/정보
commit : 커밋 순간의 스냅샷/사진

local
working directory -git add-> staging area
staging area -git commit -> localrepo

remote
localrepo -git push -> remote repo
remote repo -git pull -> localrepo

localrepo -git checkout -> working directory

git 초기설정
git config --list
git config --global user.name "내용"
git config --global core.editer "vim"
git config --global core.page "cat"

git clone URL : github 원격저장소(레포스토리)를 
로컬로 복제해옴(로컬에 폴더가 생성됨)

shift + insert : 붙여넣기

pwd : present working directory 현재위치표시
파일이름 대소문자 구분함

git status : 상태명령어
origin 은 remote repo의 관습적 표현

git remote add 이름 URL
origin 대신 특정 이름으로 원격저장소 지정할 수 있음

git commit : 설명입력

commit에서
제목 엔터두번 내용으로 구분 필수

commit할때 작업단위별로 구분해서 작업해야 함
git add 파일명 : 파일을 작업단위로 담아줌

git push origin main : github에 업로드(push)

react : library 
angular : framework

Conventional Commits(규칙)
commit 제목은 하나의 구나 절
Importance of Capitalize
prefix 꼭 달기
 - feat : 기능개발 관련
 - fix : 오류 개선, 버그패치
 - docs : 문서화 작업
 - test 
 - conf : 환경설정
 - build : 빌드
 - ci : continuous integration
 - reactior : 개선

## 제목


파일읽기 : cat 파일명
stage : 앞접시 개념

ctrl + C : 입력취소


정적 사이트 생성
hugo, hexo(쉬움)- node.js

hexo init 폴더명 : 폴더생성
hexo generate : 정적파일(html,css,js) 생성
hexo server : 서버오픈
 - package.json 파일 있는 폴더인지
ls로 확인

hexo new post "My first hexo blog"
에디터 내에서 삽입(i) 입력시
o 눌러주면 i눌러서 한줄띄운것과 같은 효과
hexo Clean && hexo generate : 일괄적용

vi _config.yml
deployment에서
type: git
repo: 주소
branch: main

npm install hexo-deployer-git --save
npm install hexo-theme-next --save

hexo deploy
새로고침 : ctrl + shift + r



## 오늘 한 일

### Start project wit git

```shell
$ git clone {repo url}
$ cd {repo}
$ git add README.md
$ git commit
$ git push origin main
```


## 내일 할 일
