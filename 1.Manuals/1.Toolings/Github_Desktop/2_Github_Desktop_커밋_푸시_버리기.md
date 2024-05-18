
# git 왜 씀?
git 을 구글에 검색하면 머 복잡한 설명이 나오는데, 쉽게 설명하면,
여러명이 코딩할 때 생기는 각종 문제들을 해결하고 관리해주는 툴이다.

사실 코드뿐만 아니라, 문서를 여러명이서 작성하보면 아래와 같이 진짜 마지막 수정인줄 알았는데 또 수정해야되고, 여러명이 수정해서 사람 이름을 붙이고 이런 일이 빈번하다. (열받는다)
![alt text](<images/1_commit_push_discard/image copy 1-1.png>) 

이렇게 동일한 문서의 다른 버전을 관리하기 위해서 git 을 쓴다. git 같은걸 "버전관리 툴" 이라고 부르는 이유임

혼자 코딩할때도 git 을 쓰면 좋은데, git 을 쓰면 일종의 "아주 체계적인 Ctrl+Z" 를 할 수 있다.

먼말이냐면,

Ctrl + Z 로 수정한 내용 되돌리기 기능을 써본적이 있을 것이다.
보통 Ctrl + Z 를 연타해서 원하는 지점까지 되돌리는데, 

git 을 쓰면 특정 수정한 지점에 표시를 해두고 그 지점까지 돌아가는 것도 가능하고, 돌아갔다가 다시 되돌아오고 과거와 현재를 합치고 뭐 이런 짓이 됨 ㅇㅇ

# git 기능 / 용어 대충 설명
git 은 기능이 짱 많은데, 몇개만 알고 나머지는 구글로 그때 그때 찾아보면 된다

### 1) Repository(레포지토리)
레포지토리는 git 으로 관리되는 폴더를 묶어서 레포지토리라고 함. 줄여서 레포라고들 많이 부른다.

### 2) remote (리모트, 원격지)
레포를 github 같은 서버에 올리면 그 서버를 remote 라고 부른다.

### 3) Commit(커밋)
커밋은 "내가 수정한 내용을 표시" 하는 기능이다.
커밋은 체계적으로 Ctrl+Z 할 때, 남이 내 코드를 읽을 때 중요한 역할을 함 ㅇㅇ

코드를 수정하고나서 이걸 왜 수정했는지 의도를 기록해둔다.

커밋할 때 적는 메모를 커밋 메세지(Commit Message)라고 함

### 4) Push(푸시)
커밋을 한개 또는 여러개를 하면 내 컴퓨터에 수정사항이 저장된다. (정확히 말하면, git repo 를 클론해온 폴더에 있는 .git 이라는 숨김폴더 안에 기록됨. 이 폴더 지우면 커밋 다 날라감 ㅇㅇ)

### 5) Fetch, Pull(패치, 풀)
Fetch 랑 Pull 은 remote 에서 코드를 다운받는 기능임
Fetch 는 remote 의 코드랑 내 코드를 비교해서 다운받을게 있는지 체크하는 기능이다. 업데이트 확인? 기능이랄까
Fetch 를 해서 업데이트할게 있을 때, Pull 을 하면 코드가 다운받아진다.

remote (보통 github) 에 이 커밋과 수정된 코드를 올리는 것을 Push 라고 함. 인터넷이 연결되어있어야 할 수 있다.

### 6) Pull Request (풀리퀘스트, 풀리퀘)
자세한건 실습해보면 쉽게 알 수 있는데,
쉽게 얘기하면 내가 코딩한거 함 보시고 니 코드에 합쳐주세요 하고 부탁하는 기능이다


# 실습
실습을 위해 테스트 레포지토리를 만듭니다. 다하고 지우셈 ㅇㅇ

![alt text](<images/1_commit_push_discard/image copy 0.png>) 

README file 을 체크하면, 기본 파일인 README.md 를 추가해줍니다.
체크해줘야 안 귀찮음

(빈 repository 를 생성하면 귀찮음. 왜냐면 github 는 아무 파일도 없는 repository 를 허용하지 않으므로, pc 에서 처음 코드를 업로드할 때 이것저것 해줘야하기 때문입니다. 먼 upstream 을 설정하고 그런걸 해야됨)

![alt text](<images/1_commit_push_discard/image copy 2.png>) 

이제 github desktop 을 열고 File>Clone repository 를 눌러서 레포를 클론해옵니다.
클론해온다는건 온라인 github 서버에 있는 파일들을 pc에 다운로드한다는 뜻 입니다.

![alt text](<images/1_commit_push_discard/image copy 3.png>) 

clone 할 주소를 입력하라고 뜨는데, 
![alt text](<images/1_commit_push_discard/image copy 5.png>) 

github 에 들어가서 Code, HTTPS 에 들어가보면 있다. 저걸 복붙하면 됨
![alt text](<images/1_commit_push_discard/image copy 4.png>) 

이제 Current repository 가 test_repo 로 뜨고,
![alt text](<images/1_commit_push_discard/image copy 6.png>)

우클릭하고 Show in Explorer 를 클릭하면 내 컴퓨터의 탐색기로 볼 수 있다.
![alt text](<images/1_commit_push_discard/image copy 6-1.png>)

Open in Visual Studio Code 를 누르면 vscode 로 열 수 있다.
![alt text](<images/1_commit_push_discard/image copy 7.png>) 

클릭하면 vscode 로 열린다. 이제 이 코드들은 git 에 추적된다.
![alt text](<images/1_commit_push_discard/image copy 8.png>)

이제 대충 코딩을 해본다. 그냥 바보라고 출력하고 0~10을 출력하는 코드임
![alt text](<images/1_commit_push_discard/image copy 9.png>) 

코드를 수정한다음 github desktop 앱을 켜보면 수정사항이 뜬다
![alt text](<images/1_commit_push_discard/image copy 10.png>) 

커밋메세지를 작성해보자.
![alt text](<images/1_commit_push_discard/image copy 11.png>) 

아래 커밋메세지를 적는 란에 커밋메세지와 설명을 적으면 된다. 설명(Description) 은 선택사항이라 적어도 되고 안적어도 된다
![alt text](<images/1_commit_push_discard/image copy 12.png>) 

이제 계속 코딩을 해보자. 코딩을 하다보니까 숫자: 이렇게 숫자 앞에 표시하면 좋을 것 같다.
![alt text](<images/1_commit_push_discard/image copy 13.png>) 

이제 다시 github desktop 을 보면 해당 사항이 수정된 것이 보인다.
![alt text](<images/1_commit_push_discard/image copy 14.png>)

만일 이 수정을 되돌리고 싶으면 해당 수정을 discard 하면 된다.
(Ctrl+Z 와 같다)

우클릭한 후 Discard changes 를 누르면 취소된다.
![alt text](<images/1_commit_push_discard/image copy 16.png>) 

그러면 실제 코드도 다시 수정하기 전으로 돌아온다.
![alt text](<images/1_commit_push_discard/image copy 17.png>)

History 를 누르면 커밋 메세지 목록을 볼 수 있다.
Push 버튼을 누르면 remote 인 github 로 코드를 업로드한다.
![alt text](<images/1_commit_push_discard/image copy 16-1.png>) 

Push Origin 을 누르고, github 에 들어가서 확인해보면 코드가 올라가있다.![alt text](image.png)
![alt text](<images/1_commit_push_discard/image copy 20.png>) 
![alt text](<images/1_commit_push_discard/image copy 21.png>) 

github 웹브라우저에서도 코드를 커밋할 수 있다. 연필 모양 버튼을 눌러서 수정해보자
![alt text](<images/1_commit_push_discard/image copy 22.png>) 

수정다음 커밋을 누른다.
![alt text](<images/1_commit_push_discard/image copy 23.png>)

![alt text](<images/1_commit_push_discard/image copy 24.png>) 

그러면 커밋 메세지를 작성할 수 있는 창이 뜸
![alt text](<images/1_commit_push_discard/image copy 25.png>) 

이제 다시 github desktop 앱을 열고,
![alt text](<images/1_commit_push_discard/image copy 26.png>) 

Fetch 버튼을 누르면 Pull 로 바뀐다. 수정사항이 있다는 뜻이다.
Pull 을 누르면 코드가 다운로드된다.
![alt text](<images/1_commit_push_discard/image copy 27.png>) 

vscode 에서도 변경된 코드를 확인할 수 있다.
![alt text](<images/1_commit_push_discard/image copy 28.png>)

## Discard, Undo, Revert 
discard, undo, revert 는 다 과거로 되돌리는 Ctrl Z 기능인데 약간 구분이 있다.
- discard 는 "커밋하기 전"에 수정사항을 수정한적이 없다고 없애버리는 기능이다. 되돌리기도 안된다. 그냥 없는 일로 하는 기능임. 커밋한 이후에는 discard 할 수 없다

- undo 는 "커밋"을 통채로 없애버리는 것이다. 그냥 없던 일이 되어서 복구가 안된다.

- revert 는 "커밋을 취소했다" 고 커밋하는 것이다. 그러면 취소한 커밋도 기록된다.

아얘 없던 일로 해버리면, 나중에 또 그 부분을 쓰려고 할 때 곤란해진다. (근데 코딩할때는 이런일이 꽤 자주 일어난다.)

그림 그리다가 망쳤다고 지우개로 박박 지워버리면, 나중에 아무리 그려도 그 그림이 제일 나았었으면 돌이킬 수 없다. revert 는 전부 기록해두기 때문에 나중에 다시 돌아갈 수 있다.

코드 앞에 인사말을 출력하는 코드를 추가해보자.
![alt text](<images/1_commit_push_discard/image copy 29.png>)

github desktop 에 가보면 수정사항이 기록되어있다. 커밋 메세지를 작성하고 커밋한다
![alt text](<images/1_commit_push_discard/image copy 30.png>)

그런데 인사하는 부분이 굳이 필요 없을 것 같다. 되돌리고 싶다. 그러면 revert 하면 된다.
History 탭에 들어가서, 커밋에 우클릭 한 후, Revert changes in commit 을 클릭한다.

![alt text](<images/1_commit_push_discard/image copy 32.png>)

그러면 코드가 전으로 돌아간다.
![alt text](<images/1_commit_push_discard/image copy 31.png>)

