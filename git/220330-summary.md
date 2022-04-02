# 220330 - 정리

## hexo bolg 생성
1. github에서 `username`.github.io로 리파지토리를 생성
![hexoblog-1](/git/hexoblog-1.png)
2. git bash에서 npm을 이용하여 `hexo-dli`설치
```shell
$ npm install -g hexo cli
```
3. ghblog폴더를 생성하여 기본 파일 설치(폴더명은 자유)
```shell
$ hexo init ghblog
```
3-1. ghblog에 설치된 기본 파일들   
![hexo-basic-files](/git/hexoblog-2.png)   
3-2. hexo관련 명령어는 `_config.yml` 파일이 있는 ghblog 폴더 안에서 한다.   
![config-file](/git/hexoblog-3.png)   
4. 위에서 `$ hexo init [폴더명]` 으로 만들어진 폴더로 들어가 위 명령어를 실행해 hexo에 필요한 파일들을 설치
```shell
$ npm install
```
5. `/documents/dev/ghblog/source/_posts/My-first-post.md` 파일 생성 명렁어
```shell
$ hexo new post "My first post"
```
6. vim 편집기로 My-first-post.md 파일을 작성   
![my-first-post-edit](/git/hexoblog-4.png)   
6-1. 내용은 위처럼 `---` 아래에 작성하고 `markdown` 문법으로 작성한다.   
7. `$ hexo server` 로 로컬 서버 구동하여 작성한 블로그 페이지를 볼 수 있다.(ctrl+C를 누르면 서버 닫기)   
![server-open](/git/hexoblog-5.png)
8. `_config.yml`파일을 vim 편집기로 열어 `#Deployment` 영역에 github에서 만든 블로그 리포와 hexo를 동기화 시켜준다.   
![deployment-to-repo](/git/hexoblog-6.png)
9. hexo-deployer-git 플러그인 설치
```shell
$ npm install hexo-deployer-git --save
```
10. 블로그 배포
```shell
$ hexo clean && hexo deploy
```
    - hexo clean - public 폴더의 내용을 찌꺼기 까지 삭제하고 업데이트 및 새파일 설치
    - &&는 앞에 명령어 성공하면 다음 명령어 실행
