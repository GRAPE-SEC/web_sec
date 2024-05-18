# 풀리퀘스트(Pull Request)
풀리퀘해주세요, PR 해주세요, Pull Request, 하면 이 기능을 말한다.
쉽게 얘기하면 내가 코딩한거 함 보시고 니 코드에 합쳐주세요 하고 부탁하는 기능이다

실습해보면 쉽게 이해할 수 있다.

## branch (브랜치)
브랜치는 git 에 있는 코드 구분 기능인데, 영어로 가지치다, 나뭇가지 라는 뜻이다.
코드를 복제해서 약간씩 다른 여러 버전을 이름을 붙여 구분하고, 나중에 합칠 수 있다.
어떤 코드에서 branch 로 나가는 거를 분기한다고 표현한다. (해보면 안다.)

## 풀리퀘스트 과정
풀리퀘스트에는 순서가 있는데,
1) 새로운 branch 로 코드를 분기하기

2) 풀리퀘스트 열기 (open) -> 문을열다 할때 열다 보다는 공론화하다 뭐 이런 뜻이다.

3) 브랜치끼리 합치는 merge

이렇게 세단계로 구성된다.

# 실습
Current Branch 라는 버튼을 눌러서 브랜치 탭을 열고 New branch 를 클릭
![alt text](<images/2_pull_request/image copy 30.png>) 

temp (temporary 임시의 약자인데 코딩할때 많이 쓰는 말임) 라는 브랜치를 만든다. 뭐 이름은 나중에 바꿀 수 있으니까 아무거나 써도된다. asdf 라고 써도 됨 ㅇㅇ
![alt text](<images/2_pull_request/image copy 31.png>) 

이제 이 코드는 원래 코드와 토씨 하나 안틀린 복제본이다. 근데 git 에서 이 branch 가 선택된 동안 코드를 수정하면 기존 코드와 무관하게 수정된다.

먼말이냐면, 당신의 복제인간을 만들면 복제인간을 만든 순간엔 둘이 똑같을 것 이다. 근데 복제인간이 머리를 염색하면 당신의 머리에는 아무 영향이 없다.

![alt text](<images/2_pull_request/image copy 32.png>)

어떤 branch 에 있는지는 Current Branch 에서 확인할 수 있다.
![alt text](<images/2_pull_request/image copy 33.png>) 

이제 temp 브랜치에서 코드를 수정해보자.

대충 프로그램의 제목을 출력하는 그런 기능을 추가했다.
![alt text](<images/2_pull_request/image copy 34.png>)

커밋한다.
![alt text](<images/2_pull_request/image copy 35.png>) 

커밋한 이후에는 브랜치끼리 이동할 수 있다(switch)

(복제인간이 염색을 하고 커밋을 한 후, 원래인간으로 돌아가면 원래인간은 염색이 안된다. 근데 커밋을 안하고 원래인간으로 돌아가면 원래인간이 염색된다.)
![alt text](<images/2_pull_request/image copy 36.png>)

![alt text](<images/2_pull_request/image copy 37.png>) 

history 탭을 눌러보면 수정사항이 표시된다.
![alt text](<images/2_pull_request/image copy 38.png>) 

Current branch 버튼을 눌러서 main 으로 다시 바꾸면(switch),

![alt text](<images/2_pull_request/image copy 39.png>)

temp 브랜치를 수정했는데 main 은 그대로이다. 복제인간과 기존인간은 다른 생명체인 것 처럼 서로 달라진거임.
![alt text](<images/2_pull_request/image copy 40.png>) 


변경사항이 있는 상태에서 커밋을 안하고 브랜치를 바꾸려고하면, 옮길 브랜치에 변경사항을 덮어씌울지, 이 브랜치에 저장해두고 이동할 브랜치에 갈지 고를 수 있다.

잠깐 브랜치에 변경사항을 저정하는 것을 stash 라고 부른다.

![alt text](<images/2_pull_request/image copy 39-1.png>)

다시 temp 에 돌아와보면 Stased Changes 가 뜬다. 클릭하면 이것을 복구(Restore)할지 버릴지(Discard) 고를 수 있다.
![alt text](<images/2_pull_request/image copy 39-2.png>) 



# 풀리퀘로 협업하기 시뮬레이션
이제 다른 팀원과 같이 코딩을 하는 상황을 가정해보자.
협업 전에, 각자 기능을 추가할 때에는 브랜치를 새로 만들어서 작업하고, 서로 브랜치는 건드리지 않기로 협업규칙을 정하여 합의한다.

지금은 혼자 실습하고 있으니까, 새 브랜치를 만들고 이 브랜치는 다른 사람이 코딩하고 있다고 가정해보자.

10까지 세는 코드를 100까지 세는 코드로 바꾸는 기능을 추가하는 일을 다른 팀원이 하고 있다고 가정해보자
![alt text](<images/2_pull_request/image copy 41.png>) 

count_to_hundred 라는 브랜치를 만들고 거기로 분기한다(branch한다).
![alt text](<images/2_pull_request/image copy 42.png>)

코드를 고친다. 다른 팀원이 어디를 수정하는지 나는 모르겠고, 어쨌든 100까지 세도록 기능을 추가한다.
![alt text](<images/2_pull_request/image copy 43.png>) 

커밋한다. 커밋 메세지는 남이 읽을거니까 100을 세게하는 기능을 추가했습니다 뭐 이런 친절한 메세지를 적으면 좋겠죠?
![alt text](<images/2_pull_request/image copy 44.png>) 

이제 브랜치들을 클릭해보면 두개의 브랜치는 다른 코드이다.

팀원과 협업하고 있으니, 각각 브랜치는 서로 다른 컴퓨터에서 수정되고 있다.
![alt text](<images/2_pull_request/image copy 45.png>)

햇갈리니까 temp 브랜치의 이름을 수정내용과 관련된걸로 수정하자
![alt text](<images/2_pull_request/image copy 46.png>) 
![alt text](<images/2_pull_request/image copy 47.png>) 

프로그램의 제목과 종료를 출력하는 기능과 관련된 브랜치니까 이름은 add_title 정도가 좋을 것 같다.
![alt text](<images/2_pull_request/image copy 48.png>)

# Publish
퍼블리시(Publish) 는 브랜치를 remote(원격서버에 있는 저장소, 여기서는 github를  말함) 에 업로드하는 것을 말한다.

Publish branch 를 누르면 remote 에 branch 가 생성된다

각 브랜치에 들어가서 Publish 를 해준다.
![alt text](<images/2_pull_request/image copy 49.png>) 

이제 github 에 들어가보면 branch 가 두개 생성되어있다.
![alt text](<images/2_pull_request/image copy 50.png>) 

이제 Pull Request 를 해보자. 한국에서는 "풀리퀘한다"고들 한다. 영어로는 PR 한다고 한다.
![alt text](<images/2_pull_request/image copy 51.png>)

github desktop 앱에서도 할 수 있고, github 웹페이지에서도 할 수 있다.

github desktop 앱에서 하는 방법은 아래와 같다.
![alt text](<images/2_pull_request/image copy 52.png>) 
![alt text](<images/2_pull_request/image copy 53.png>) 

github 웹페이지에서 하는 방법은 아래와 같다.
![alt text](<images/2_pull_request/image copy 54.png>) 
![alt text](<images/2_pull_request/image copy 55.png>) 
![alt text](<images/2_pull_request/image copy 56.png>)


![alt text](<images/2_pull_request/image copy 57.png>) 
![alt text](<images/2_pull_request/image copy 58.png>) 
![alt text](<images/2_pull_request/image copy 59.png>) 
![alt text](<images/2_pull_request/image copy 60.png>) 
![alt text](<images/2_pull_request/image copy 61.png>) 
![alt text](<images/2_pull_request/image copy 62.png>) 
![alt text](<images/2_pull_request/image copy 63.png>) 
![alt text](<images/2_pull_request/image copy 64.png>) 
![alt text](<images/2_pull_request/image copy 65.png>) 
![alt text](<images/2_pull_request/image copy 66.png>) 
![alt text](<images/2_pull_request/image copy 67.png>) 
![alt text](<images/2_pull_request/image copy 68.png>) 
![alt text](<images/2_pull_request/image copy 69.png>) 
![alt text](<images/2_pull_request/image copy 70.png>) 
![alt text](<images/2_pull_request/image copy 71.png>) 
![alt text](<images/2_pull_request/image copy 72.png>) 
![alt text](<images/2_pull_request/image copy 73.png>) 
![alt text](<images/2_pull_request/image copy 74.png>) 
![alt text](<images/2_pull_request/image copy 75.png>) 
![alt text](<images/2_pull_request/image copy 76.png>) 
![alt text](<images/2_pull_request/image copy 77.png>) 
![alt text](<images/2_pull_request/image copy 78.png>) 
![alt text](<images/2_pull_request/image copy 79.png>)