1주차
💻 깃 (Git) & 깃허브 (GitHub) 핵심 정리
1. 📂 깃 (Git) 기본 개념: '내 컴퓨터' 안에서의 버전 관리!
Git은 내 컴퓨터(로컬)에서 파일의 **변경 이력(버전)**을 관리하는 시스템이다.

저장소 (Repository, Repo): Git이 파일을 관리하는 공간.

로컬 저장소 (Local Repo): 내 컴퓨터에 있는 저장소.

커밋 (Commit): 변경된 내용을 하나의 버전으로 확정하고 기록하는 행위. ctrl+s와 달리, 어떤 내용을 바꿨는지 메시지를 남긴다.

브랜치 (Branch): 독립적으로 작업을 진행하기 위한 가지. 메인 줄기(main/master)에 영향을 주지 않고 새로운 기능을 개발할 때 사용한다.
2. 🔗 깃허브 (GitHub) 개념: '인터넷'에 프로젝트 저장하기!
GitHub는 Git으로 관리되는 프로젝트를 **원격(Remote)**에 저장하고 여러 사람과 협업할 수 있게 해주는 웹 서비스이다.

원격 저장소 (Remote Repo): GitHub 서버에 있는 저장소.

푸시 (Push): 로컬 저장소의 커밋을 원격 저장소로 업로드하는 행위.

풀 (Pull) / 클론 (Clone): 원격 저장소의 내용을 내 컴퓨터로 다운로드하는 행위.
➡️ GitHub에 프로젝트 올리는 표준 절차 (최초 1회)
로컬 초기화: git init

원격 연결: git remote add origin [GitHub Repo 주소]

파일 준비: git add .

로컬 기록: git commit -m "Initial commit"

업로드: git push origin main
새 프로젝트 시작	git init	현재 폴더를 Git 관리 대상으로 만듦 (저장소 초기화)
원격 연결	git remote add origin [URL]	GitHub 주소를 origin이라는 이름으로 저장소에 등록
추적 시작	git add .	모든 변경 파일을 다음 커밋에 포함하도록 준비 (Stage)
버전 기록	git commit -m "메시지"	버전 기록 확정. 메시지는 짧고 명확하게!
업로드	git push origin main	로컬 기록을 GitHub (main 브랜치)로 최종 전송
다운로드	git pull origin main	GitHub의 최신 변경 사항을 내 컴퓨터로 가져옴
상태 확인	git status	현재 파일의 변경 상태 확인 (가장 자주 씀!)
