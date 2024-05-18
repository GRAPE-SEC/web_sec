
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
![alt text](<images/1_commit_push_discard/image copy 9.png>) 
![alt text](<images/1_commit_push_discard/image copy 10.png>) 
![alt text](<images/1_commit_push_discard/image copy 11.png>) 
![alt text](<images/1_commit_push_discard/image copy 12.png>) 
![alt text](<images/1_commit_push_discard/image copy 13.png>) 
![alt text](<images/1_commit_push_discard/image copy 14.png>) 
![alt text](<images/1_commit_push_discard/image copy 15.png>) 
![alt text](<images/1_commit_push_discard/image copy 16.png>) 
![alt text](<images/1_commit_push_discard/image copy 17.png>) 
![alt text](<images/1_commit_push_discard/image copy 19.png>) 
![alt text](<images/1_commit_push_discard/image copy 20.png>) 
![alt text](<images/1_commit_push_discard/image copy 21.png>) 
![alt text](<images/1_commit_push_discard/image copy 22.png>) 
![alt text](<images/1_commit_push_discard/image copy 23.png>) 
![alt text](<images/1_commit_push_discard/image copy 24.png>) 
![alt text](<images/1_commit_push_discard/image copy 25.png>) 
![alt text](<images/1_commit_push_discard/image copy 26.png>) 
![alt text](<images/1_commit_push_discard/image copy 27.png>) 
![alt text](<images/1_commit_push_discard/image copy 28.png>)