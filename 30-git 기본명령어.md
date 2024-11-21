# ▣ git 기본명령어

    1. git help <명령어>

    2. 로컬저장소로 사용할 폴더에서
      git init 명령어를 실행하여 초기화 -> .git 이라는 숨김폴더가 생성
      -> "지금부터 이 폴더를 버전관리 하겠다" 는 의미

    3. 커밋정보 등록
      git config --global user.name "duly/uiux"
      git config --global user.email "duly@hotmail.com"

    4. .gitignore -> 업로드 예외설정 파일 (확장자 없음)
        예시)
          git_사용법.md
          homework/
          setup/
          *.zip
          *.pptx
          팀뷰어접속번호.txt

    5. 현재 로컬저장소의 git 현황/상태 보기
        git status

    6. 깃으로 관리할 워킹카피 영역에 있는 파일을 index 영역으로 보냄
        git add 파일명

        git add --all		-> 모든파일
        git add .			-> 모든파일
        git add -u  		-> 이전에 커밋한 적이 있는 파일만 index 영역으로 이동시킴

        git commit -a -m "버전생성메세지"  -> 워킹카피 영역에서 바로 커밋 가능함

    7. 워킹카피 영역으로 내림
      git rm --cached 파일명   -> (add 취소 - 워킹카피 영역으로 내림)
      git rm --cached *.* -> 모든파일
      git rm --cached -r {파일명 파일명 ...} // 여러 개 한꺼번에 내림
      git rm --cached -f 파일명   -> -f 는 강제삭제


    8. 새로운 버전 생성 -> commit 한다 라고 표현
      commit 할때는 간단한 설명을 기록해야 하는데 내가 이 파일을 왜 만들었는지, 왜 수정했는지 또는 왜 기록하는지 알수 있도록 한다.
      반드시 쌍따옴표 사용

      git commit -m "간단한 설명"

      예시) git commit -m "마켓컬리 프로젝트 기본구조"

    9. 지금까지 commit한 모든 버전정보를 열람, 종료시 q
        git log

        git log 파일명 -> 특정파일의 커밋정보만 열람
        git log 커밋번호

        git log --oneline  -> commit id의 일부와 commit message만 보여줍니다.
        git log -p -> 각각의 커밋과 커밋사이의 소스 차이점 확인 가능
        git show 커밋번호  -> 커밋의 상세내용 확인

        git diff  -> 커밋하기전 워킹카피와 인덱스 영역사이의 변경된 모든 파일내용 차이 확인
        gif diff --cached  -> 인덱스와 저장소사이의 내용차이 확인
        git diff 커밋아이디1..커밋아이디2 - 두개의 특정 커밋 사이의 소스상 차이점 보여줌
