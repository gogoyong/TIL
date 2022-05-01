0414 git강의2
1. 원격저장소 만들기
2. 주소 복사
3. bash 실행 후 클론 생성할 폴더 이동
4. git clone URL

README.md 
- 프로젝트와 원격저장소를 설명하는 
책 표지같은 문서

license
MIT License(행동에 제약사항 없음)
Apache License(특허권 내용 포함)
GNU General Public License(의무사항 존재)

.gitignore
git이 파일 추적시 
어떤 파일, 폴더를 추적하지 않도록 
명시하기 위해 작성

숨겨져 있으므로 
작업 후 ls -a해야 보임

branch
분기점을 생성하여 독립적으로 코드를 
변경할 수 있도록 도와주는 모델

conf: config

git branch : 가지상태 확인
git branch 가지이름 : 가지이름 만들기
git switch 가지이름 : 가지로 갈아타기
git merge 가지이름 : 해당 가지를 당기기
git branch -D 가지이름 : 가지 제거

merge하여 conflict 발생하면
수정한 후
commit을 해주어야 merged path 생김

git push -u origin 가지이름
-u upsream set
원격에 없던 새로운 가지를 올려줌

branch models
git flow : 가장 많이 적용
(hotfix)-main-(release)-develop-feature
hotfix:긴급패치
github flow
gitlab flow

main : 사용자가 보게될 소스코드

git flow init
git flow feature start 가지이름
git flow feature finish 가지이름
git flow release start v0.1
git flow release finish v0.1
commit 총 세번
merge, tag, develop

git push -u origin develop
git tag
git push

minor change 소수점 뒤 숫자를 올림
major change 

mv 파일1 파일2 :
git에서는 파일1이 삭제되고 2가 생성된걸로
인식
따라서
git mv 파일1 파일2 로 해야 rename됨

git restore 파일이름 : 되돌리기(commit단위)
git add하는 단계에서만 가능함

git reset HEAD 파일명
: working 디렉토리에 다시 남도록 함
add로 올린 스테이지를 취소하는 것

git commit --amend
: 커밋 수정

HEAD : 최신의 commit을 의미

git revert --no-commit HEAD~3..
세개를 순차적(..)으로 커밋 삭제

협업 
조장 - 새 repository 생성
name, readme 생성,
주소 복사

이슈를 등록해서 fork를 하면
팀장의 게임이 아니라
팀원 권한의 게임이 됨

