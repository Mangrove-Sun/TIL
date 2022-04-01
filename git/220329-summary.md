# 2022/03/29 정리


## README의 역할
이 저장소가 어떤 역할을 하는지 설명하는 파일   
**최대한 구체적이고 친절한 설명을 해주자**


## Git Process Flow
![git process flow](/gitprocessflow.png)   
`$ git add` 변경사항을 commit하고 싶은 걸 stage라는 앞접시에 덜고   
`$ git commit` 앞접시에 덜어놓은 것에 변경사항의 스냅샷을 찍는다


## Git 명령어
```shell
$ git init
```
현재 위치한 폴더를 git에서 관리하겠다는 선언(초기화), 로컬 리파지토리 생성(.git 폴더)

```shell
$ git clone [repoAddress]
```
remote Github의 리파지토리의 파일을 로컬의 현재 폴더에 복사

```shell
$ git remote add [alias] [repoAddress]
```
리파지토리와 작업폴더를 연결[별명(alias]은 임의로 적어도 되지만 일반적으로 origin을 많이 씀

```shell
$ git remote remove [alias] [repoAddress]
```
리파지토리 연결을 제거

```shell
$ git remote remove [alias]
```
별명(alias) 지우기

```shell
$ git remote
```
별명 확인

```shell어
$ git remote -v
```
원격의 Github의 리파지토리 주소 정보를 확인

```shell
$ git add [파일명]
```
파일을 stage영역에 올려두는 작업
  - `$ git add .` 현재 폴더의 모든 파일을 올림(변경된 파일만 올라감)

```shell
$ git commit
```
commit 메세지 작성
  - `$ git commit -m "커밋설명"` - 커밋 메세지를 작성하는 다른 방법, 오타 발생시 새로 
  작성해야하는 불편함이 있으니 사용을 자제바람

```shell
$ git push origin main
```
커밋된 파일을 원격의 origin 경로의 주소에 main 브랜치에 로컬파일을 전송

```shell
$ git branch -M main
```
(-M 대소문자 구분) master -> main으로 브랜치 변경하기

```shell
$ git push -u mask main
```
(-u, upstream set) `$ git init`한 경우 remote branch main과 init한 local branch main과 
연결해주는 명령어 // 너희는 같은 녀석이야~


## Commit 메세지 작성 Tip

1. commit은 동작 가능한 최소단위로 자주 할 것!
2. 해당 작업단위에 수행된 모든 파일 변화가 해당 commit에 포함되어야 함.
3. 모두가 이해할 수 있는 log를 작성할 것.
4. Open source Contribution시 영어가 강제되지만, 그렇지 않을 경우 팀 내 사용 언
따라 쓸 것.
5. 제목은 50자 이내로 축약하여 쓰자, 내용은 문장형으로 작성하여 추가설명 할 것.
6. 제목과 내용은 한 줄 띄워 분리할 것
7. 내용은 이 commit의 구성과 의도를 충실히 작성할 것.
8. prefix 꼭 달기
  - feat (features): 기능 개발 관련
  - fix: 오류 개선 혹은 버그 패치
  - docs (documentations): 문서화 작업
  - test: test 관련
  - conf (configurations): 환경설정 관련
  - build: 빌드 관련
  - perf (performance): 부산물 생성 관련
  - ci: Continuous Intergration 관련
