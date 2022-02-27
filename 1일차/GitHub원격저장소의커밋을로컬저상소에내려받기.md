# GitHub 원격저장소의 커밋을 로컬저장소에 내려받기



## 원격저장소의 커밋을 로컬저장소에 내려받기

> 원격저장소의 코드와 버전 전체를 내 컴퓨터로 내려받는 것을 클론`clone`이라고 합니다. 클론을 하면 최신 버전뿐만 아니라 이전 버전들과 원격저장소 주소 등이 내 컴퓨터의 로컬저장소에 저장됩니다.

1. 먼저 아래 경로로 내 컴퓨터에 [GIT] 폴더를 만들어 줍니다.

```bash
~/Desktop/git
```

2. 방금 이 폴더를 만들었으니 여기에는 아무 것도 들어있지 않겟죠? Terminal을 열어줍니다
3. clone 명령어 뒤에 원격저장소 주소를 입력하면 어느 원격저장소든 내 컴퓨터의 로컬 저장소에 내려받을 수 있습니다.

```bash
❯ git clone https://github.com/HoonyCode/GIT_TEST.git
'GIT_TEST'에 복제합니다...
remote: Enumerating objects: 70, done.
remote: Counting objects: 100% (29/29), done.
remote: Compressing objects: 100% (18/18), done.
remote: Total 70 (delta 5), reused 22 (delta 1), pack-reused 41
오브젝트를 받는 중: 100% (70/70), 8.29 KiB | 1.66 MiB/s, 완료.
델타를 알아내는 중: 100% (13/13), 완료.
```



4. GIT_TEST [.git] 폴더(로컬저장소 - 숨겨진 폴더)가 보이면 성공입니다. 클론을 하면 이렇게 로컬 저장소가 자동으로 생깁니다.
   고양이가 Git 초기화를 해서 만들었던 로컬저장소를 받아온 겁니다.

```bash
❯ ls -al
total 24
drwxr-xr-x   5 hoony  staff   160  2 27 18:16 .
drwxr-xr-x@  8 hoony  staff   256  2 27 18:16 ..
-rw-r--r--   1 hoony  staff  6148  2 27 18:16 .DS_Store
drwxr-xr-x  12 hoony  staff   384  2 27 18:17 .git
-rw-r--r--   1 hoony  staff    16  2 27 18:16 README.md
```



5. [GIT-TEST] 폴더에 있는 README.md 파일을 열어 보면 우리가 원격저장소에 커밋했던 것과 동일합니다.

```bash
❯ cat README.md
# Git 설명 짱
```



6. 여기서 새로 커밋을 만들어 올려보겠습니다. README.md 파일을 아래처럼 수정하고 저장합니다.

<img width="588" alt="image" src="https://user-images.githubusercontent.com/44612896/155876406-8d11dd05-7f02-4721-8644-4b33d4f9e354.png">

7. Terminal 에서 아래 세 개의 명령어를 실행합니다. 세 번째 명령어 실행 후에 100% 메세지가 나오면 성공입니다

```bash
❯ clear
❯ git add README.md
❯ git commit -m "update 개발자 목록 추가"
[main 0d4e6d0] update 개발자 목록 추가
 1 file changed, 7 insertions(+), 1 deletion(-)
❯ git push origin main
오브젝트 나열하는 중: 5, 완료.
오브젝트 개수 세는 중: 100% (5/5), 완료.
Delta compression using up to 8 threads
오브젝트 압축하는 중: 100% (3/3), 완료.
오브젝트 쓰는 중: 100% (3/3), 368 bytes | 368.00 KiB/s, 완료.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/HoonyCode/GIT_TEST.git
   25f6b7d..0d4e6d0  main -> main
```



8. GitHub의 원격저장소에 들어가서 새로고침을 해보면 우리가 푸시한 '개발자 목록 추가' 커밋이 올라가 있는 것을 확인할 수 있습니다.

<img width="919" alt="image" src="https://user-images.githubusercontent.com/44612896/155879780-d0ff62aa-0ca2-40bd-97f1-053cda967f0e.png">



## 원격저장송의 새로운 커밋을 로컬저장소에 갱신하기

> 앞서 폴더에서 문어가 새로운 커밋을 만들어서 원격저장소에 올렸습니다.
> 따라서 [GIT-TEST] 폴더에 있는 텍스트 파일은 GIT 설명 짱 커밋이 반영되어 있습니다.
> 그러나 [TEST] 폴더에 있는 텍스트 파일은 그렇지 않습니다. 

1. [TEST] 폴더로 가서 README.md 파일을 엽니다. 세 번째 커밋이 반영되지 않은 옛날의 두 번째 '설명 업데이트' 커밋의 상태에 머물러 있음을 알 수 있습니다.

2. 이제 [TEST] 로컬 저장소에 내려 받아서 현재 상태를 갱신해 보겠습니다.
3. 아래 명령어를 입력합니다. pull 원격저장소에 새로운 커밋이 있다면 그걸 내 로컬저장소에 받아 오라는 명령어 입니다.

```bash
❯ git pull origin main
```

4. `1 file changed` 메세지가 나오면 성공입니다.
5. TEST 폴더에서 README.md 파일을 다시 열어서 확인해 보겠습니다.
   개발자 목록이 잘 추가되었네요

```bash
❯ cat README.md
# Git 설명 짱

개발자 목록

1. HoonyCode%
```



# 복습하기 

`Git` 깃이라고 하고 버전 관리 시스템입니다.

`GitHub` 깃허브라고 읽고, Git으로 관리하는 프로젝트를 올려둘 수 있는 사이트입니다.

`GUI` 그래픽 유저 인테페이스, 즉 명령어를 하나씩 입력하는 방식입니다.

`Git Bash` CLI 방식으로 Git을 사용할 수 있는 환경입니다.

`커밋` 버전 관리를 통해 생성된 파일, 혹은 그 행위를 의미합니다.

`log 명령어` 지금까지 만든 커밋을 모두 확인합니다.

`checkout` checkout으로 원하는 지점으로 되돌릴 수 있습니다. 타임머신과 같죠

`로컬저장소` Git으로 버전 관리하는 내 컴퓨터 안의 폴더를 의미합니다

`원격저장소` GitHub에서 협업하는 공간(폴더)를 의미합니다.

`레포지토리` 원격저장소를 의미합니다.

`푸시` 로컬저장소의 커밋을 원격 저장소에 올리는 것입니다.

`풀` 원격저장소의 커밋을 로컬저장소에 내려받는 것입니다.

