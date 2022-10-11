# About git

***버전 컨트롤***
**일반적인 문서 작업을 할 때 한꺼번에 끝낼 수 없고 중간중간 수정하는 단계가 있다. 잘못된 수정을**  
*할 수도 있으므로 복사본을 만들어가며 수정하는데 이러면 점점 이름이 길어지고 누가 수정했는지* 
알기 힘들므로 버전 컨트롤 시스템이 필요하고 git은 이것을 대략 3단계로 나눈다.  
(프로젝트.txt, 프로젝트_최종.txt, 프로젝트_최종_수정1.txt)  
Working Directory: 평소에 사용하는 작업 디렉터리.  

Staging area: 중간 단게로 커밋을 하려고 하는 파일에 대한 정보를 저장하는 공간. 

git directory: Staging Area에 있는 파일들을 커밋할경우 git 디렉토리에 영구적으로 저장한다.  

---
git에 대한 configuration은 3단계로 나누어져 있다. 모든 configuration은 git configure라는 파일에 저장이 된다.  

System level: --system option. 시스템 옵션으로 모든 사용자와 repertory에 영향을 끼친다.

Global level(user level): --global option. 글로벌옵션으로 설정된 옵션은 사용자의 모든 repositories에 적용된다.

Local level: --local option. 로컬옵션으로 한 repositories 안에서만 적용된다. 

각각의 설정은 하위 설정이 덮에 씌운다 system -> global -> local.

---
```sh
$ git config --list
$ git init
$ git Status
$ git add
$ git rm --cached
$ git commit
```
git config --list 명령으로 현재 세팅되어있는 confit을 알수있다.  
뒤에 --show-origin을 붙여 어디에 저장되어 있는지를 알수있다.  
user.name "이름"  
User.email "이메일"  

git init: 해당 디렉토리에 .git 이라는 폴더를 만들고 해당 폴더를 git으로 관리할 수 있게 하는 명령어.

git Status: working directory와 staging area의 상태를 확인하기 위해 사용하는 명령어.
untracked files: 디랙토리 안에 존재하지만 git이 해당 파일들을 수정하거나 지워도 상관하지 않는다.

git add: 특정 파일을 stageging area로 움기는데 쓰는 명령어.
stageing area에 있는 파일이 수정되거나 하면 git이 감지한뒤 modified 라고 표시하여 구분해서 저장한다(다시 add하여 수정된 파일로 덮어쉬울수 있다). 
git add .: 모든 파일과 디렉토리를 stageging area로 올린다.  

git rm --cached: stageging area로 올린 파일을 지운다(실제파일을 지우지는 않는다).  

.gitignore이란 파일을 만들어 특정파일의 이름을 적으면 git에서 그 파일을 무시한다.  

git commit: stageging area로 움긴 파일을 commit하여 영구적으로 저장한다.
