# GitHub 원격저장소에 커밋 올리기

## 원격저장소 만들기

> 이번에는 GitHub에 협업할 공간인 원격저장소를 만듭니다. 쉽게 설명하면 GitHub 웹 사이트에 프로젝트를 위한 공용 폴더를 만드는 것입니다.
> 로컬저장솟와 구분하는 개념으로 원격저장소라고 합니다. GitHub에서는 원격저장소를 래포지토리`Repository`라고 부릅니다.

1. [GitHub](https://GitHub.com/) 에 접속하고 로그인을 합니다. 상단 네비게이션 바에서 오른쪽에 있는 [+] 아이콘을 클릭한 훌[New repository] 메뉴를 선택합니다.

<img width="957" alt="image" src="https://user-images.githubusercontent.com/44612896/155874836-62fec213-258b-494c-8c38-af10302ed316.png">



2. 어떤 저장소를 만들지 세부 항복을 작성하는 페이지가 나옵니다. 나머지 옵션은 별도로 변경하지 않고 `Create repository` 버튼을 클릭합니다.

<img width="845" alt="image" src="https://user-images.githubusercontent.com/44612896/155874892-230eead2-a3bc-4062-accf-5e1027d96fca.png">



3. GIT_TEST라는 이름의 원격저장소를 만들었습니다. 필자의 원격저장 주소는 아래와 같습니다. 
   `https://github.com/HoonyCode/GIT_TEST.git` 
   앞으로 위 주소를 통해 원격저장소에 접속할 수 있습니다. 다른 개발자와 함께 작업하고 싶다면 이주소를 알려주면 됩니다. 또한 이 주소는 내 컴퓨터의 로컬저장소와 연결할 때도 사용합니다. 

<img width="926" alt="image" src="https://user-images.githubusercontent.com/44612896/155875069-1ee47489-fb6f-4b6f-b8e1-6d0a37da22ae.png">



## 원격저장소에 커밋 올리기

이제 GitHub에서 만든 [Git-TEST] 원격저장소 주소를 내 컴퓨터의 [TEST] 로컬 저장소에 알려주고, 로컬저장소에 만들었던 커밋들을 원격저장소에 올려 보겠습니다.



1. [TEST] 폴더의 Terminal 로 들어옵니다. `remote add origin` 명령어는 로컬저장소에 원격저장소 주소를 알려줍니다. 원격저장소 주소는 여러분의 원격저장소 주소를 입력합니다. 붙여넣기를 해도 됩니다.

```bash
❯ git remote add origin https://github.com/HoonyCode/GIT_TEST.git
```



2 이제 로컬 저장소에 있는 커밋들은 `push` 명령어로 원격저장소에 올려보겠습니다. `origin`, `master` 등의 낯선 용어가 무엇을 의미하는지는 차차 설명하겠습니다. 아래 명령어를 입력하고 `Eenter`를 누르면 Github의 로그인 창이 뜹니다. 여러분의 GitHub 계정 정보를 입력하고 로그인합니다.

```bash
❯ git push origin main
오브젝트 나열하는 중: 4, 완료.
오브젝트 개수 세는 중: 100% (4/4), 완료.
Delta compression using up to 8 threads
오브젝트 압축하는 중: 100% (2/2), 완료.
오브젝트 쓰는 중: 100% (3/3), 306 bytes | 306.00 KiB/s, 완료.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/HoonyCode/GIT_TEST.git
   328182e..25f6b7d  main -> main
```



3. 로그인에 성공하면 입력했던 명령어가 실행되는데 100% 완료 텍스트가 나오면 성공입니다.
4. GitHub의 원격저장소에서 확인해보겠습니다. 커밋과 README.md  파일이 잘 올라왔네요
   README.md 파일의 내용도 확인할 수 있습니다.

<img width="926" alt="image" src="https://user-images.githubusercontent.com/44612896/155875839-252b860b-f771-4d6d-a9dd-67ea78c9f074.png">

> 우리는 로컬저장소에서 만들었던 커밋들을 원격저장소애 성공적으로 올렸습니다. 이렇게 로컬저장소의 커밋을 원격저장소로 push 명령어를 사용해서 올리는 일을 푸시한다고 합니다. 다음 절에서는 반대로 원격저장소의 커밋을 로컬저장소로 내려받는 실습을 해 보겠습니다.

