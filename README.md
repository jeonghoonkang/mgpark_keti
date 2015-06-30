# mgpark_keti
KETI_Workspace
저도 잘하는 편이 아니라서 정말 간단한 예제 정도만...적겠습니다.

처음 설치는 리눅스 터미널 명령어로
sudo apt-get install git
을 사용하여 git을 설치하면 됩니다.


1. 
일단 리눅스에서 git을 관리할 디렉터리를 하나 만듭니다.
저의 경우 ~/workspace 로 두었습니다.
-- mkdir ~/workspace


2.
만든 디렉터리로 이동하여서 git init 명령으로 git을 초기화 합니다.
이 명령을 실행하면 현재 접속중인 디렉터리에 .git 이라는 파일이 생기게 됩니다.
-- cd ~/workspace
   git init


3.
이제 이 공간에서 파일을 만들거나 작업을하면 git 저장소에 추가가 됩니다.
git status 명령어를 실행하면 현재 git 저장소의 상태를 보여줍니다.

-- git status


4.
git status 명령어를 실행하였을 때, 영어로 설명이 쭉 나오는데,
간단하게 설명드리겠습니다.

앞서 git이 어떻게 동작하는지를 설명드리겠습니다.
맨처음 git이 수정되거나, 핸들을 하지 않으면 unstage 상태라고 불립니다.
git은 stage 상태를 통해 commit하여 로컬 git서버 저장소에 올리게 되고,
push를 통해 다른 서버로 전송할 수 있게 됩니다.


push는 마지막 한번만하여서 서버로 전송하면 되며,
update하고, stage상태로 두고, commit을 사용하면 로컬 저장소에는 저장되기 때문에,
문제가 되지않습니다.



로컬영역에서 git디렉터리 안에 파일들의 상태 :
Untranked : git디렉터리에는 존재하지만, git이 핸들하고 있지 않는 상태




1) Untracked files : 
현재 git 저장소에 추가된 파일이지만, git이 이 파일을 핸들하고 있지 않습니다.
이때에는 git add [파일명] 을 통하여 stage 상태로 변경하여주면 됩니다.

2) Changes not staged for commit :
git이 핸들하고 있는 파일이며, 수정이 되었으나,
stage 상태가 아니라는 뜻입니다.
역시 git add [파일명] 을 통하여 stage 상태로 변경하여주면 됩니다.

3) Changes to be committed :
stage된 상태의 파일이니, commit을 통하여 로컬저장소에 올리면 된다는 뜻입니다.



4) git commit -m "메세지"
를 통하여 로컬저장소로 올리게 됩니다.
-m 옵션을 통하여 메세지를 써서 올리면 되는데,
그냥 간단한 코멘트정도로 어떤 것을 수정했는지 작성하는
비고란 정도로 생각해주시면 될 것 같습니다.

***********************************
git commit 명령어를 실행할 때
git config --global user.name
git config --global user.email
에 대하여 설정하라고 에러가 나온다면

git config --global user.name [유저이름]
git config --global user.email [이메일주소]
를 사용하면 됩니다.

git이 버전관리 시스템이다 보니,
공동작업을 했을 때, 수정하였으면 수정한 사람의 이름과 이메일을 남겨야 하기 때문에,
global name 과 global email 을
초기 설정을 해주어야만 commit이 가능하게 됩니다.
global name말고 각각의 계정마다 name 과 email을 설정할 수 있지만,
꼭 필요한 작업은 아니기 때문에,
넘어가겠습니다

사실 제가 기억이 안납니다..ㅠ
**********************************


5) git remote add origin [본인 github의 디렉터리 웹페이지 주소]
   저의 경우 git remote add origin https://github.com/hello920922/mgpark_keti.git
   으로 되어있습니다.
-- git remote add origin [https://github.com/[username]/[directoryname].git



6) git push -u origin master
   origin과 master는 각각 remote저장소와 브랜치의 default값인데,
   브랜치는 어떤 특정한 상태를 저장하고 싶을 때 사용하는 것이 브랜치이고,
   origin은 내가 어느 서버로 올릴것인지.
   위에서 [https://github.com/[username]/[directoryname].git
   이 서버의 닉네임같은 것이라고 보면 되겠습니다.

이렇게 하면 본인이 설정한 주소로 해당 디렉터리의 파일들이 넘어가게 되며,
접속할 때 username 과 password를 묻는 화면이 나오고,
정상적으로 입력하면 github페이지에 올라가져있는 것을 볼 수 있습니다.
