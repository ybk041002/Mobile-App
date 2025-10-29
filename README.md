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


2주차
📒 코틀린(Kotlin) 핵심 문법 및 객체지향
1. 🚀 코틀린 기본 문법: '시작하기'
개념,문법 (예시),핵심 정리
변수 선언,"val name = ""Kim""",val: 값 변경 불가능 (Immutable)
          var age = 20,var: 값 변경 가능 (Mutable)
함수 정의,"fun sum(a: Int, b: Int): Int { ... }",fun 키워드로 함수 시작! : 뒤에 리턴 타입 명시.
조건문,if (age > 10) { ... },"자바와 비슷하지만, if가 값을 리턴할 수 있다! (표현식)"
널 안정성,var data: String? = null,타입 뒤에 ? 붙이면 널(null) 허용. 널이 아니라는 확신이 있을 때만 !! 사용!
반복문,for (i in 1..10) { ... },..는 범위 지정! (1부터 10까지 포함)

2. 🧱 코틀린 객체지향 (OOP)
OOP는 현실 세계의 물건처럼 객체를 만들고 그 관계를 정의하는 프로그래밍 방식!
클래스 정의	class Person(val name: String, var age: Int)	클래스 선언과 동시에 주 생성자와 프로퍼티(변수) 선언 가능! 코드가 엄청 줄어든다.
객체 생성	val p1 = Person("Alice", 25)	자바처럼 new 키워드가 필요 없다!
상속	open class Parent { ... }	상속할 클래스에 반드시 open 키워드를 붙여야 한다! (기본적으로 final임)
      class Child : Parent() { ... }	상속받을 때는 : 사용.
2-2. 유용한 OOP 기법
데이터 클래스	data class User(val id: Int, val name: String)	데이터 저장용 클래스! toString(), equals() 같은 유용한 함수들이 자동으로 만들어진다.
싱글톤	object Singleton { ... }	클래스 대신 object 키워드를 사용! 앱 전체에서 딱 하나의 인스턴스만 만들 때 사용.
확장 함수	fun String.lastChar(): Char = this[this.length - 1]	기존 클래스(예: String)를 수정하지 않고 새로운 함수를 추가할 수 있다!
3. 🛠️ 코틀린의 '유용한 기법'
널 안전 호출	name?.length	name이 널이 아니면 .length 실행! 널이면 그냥 null 반환. 널 체크를 깔끔하게 해준다.
엘비스 연산자	val len = name?.length ?: 0	앞의 값이 널이면 ?: 뒤의 값(0)을 대신 사용!
When 문	when (value) { 1 -> ... else -> ... }	자바의 switch보다 훨씬 강력하다! 조건이나 범위 비교도 가능.
람다/고차 함수	list.filter { it > 5 }	함수를 다른 함수의 인자로 전달 가능! 컬렉션(리스트, 배열) 다룰 때 코드가 엄청 짧아진다.


3주차
📄 안드로이드 화면 구성 및 협업 환경(Git/GitHub)
1. 안드로이드 화면 구성 방식 비교 및 분석
안드로이드 UI 개발은 전통적인 XML 뷰 시스템과 최신 기술인 Jetpack Compose 두 가지 패러다임으로 나뉩니다.

1-1. UI 구성 패러다임 비교
핵심 원리	상속 기반 (Inheritance)	구성 기반 (Composition)
설명	모든 UI 요소는 View 클래스를 상속하며, 기능을 확장하여 TextView, Button 등이 생성됩니다.	UI 요소는 작은 Composable 함수들의 트리(Tree) 구조로 조합하여 전체 화면을 구성합니다.
방식	명령형 (Imperative): 코드가 직접 UI 요소의 속성을 변경하도록 명령합니다.	선언형 (Declarative): UI의 최종 상태를 선언하면, 시스템이 상태 변화에 따라 UI를 자동으로 갱신합니다.
주요 요소	View 클래스, 레이아웃 XML 파일	@Composable 함수, Column, Row, Box 등의 레이아웃 컴포넌트

1-2. Jetpack Compose의 주요 요소
컴포저블 함수 (@Composable): UI 요소를 생성하고 조립하는 함수입니다. 이 함수들은 특수한 람다(content: @Composable () -> Unit)를 매개변수로 받아 하위 요소를 포함하는 트리 구조를 형성합니다.

Modifier: 컴포저블의 모양, 크기, 동작 방식 등을 선언적으로 지정하는 속성들의 집합체입니다. Modifier 체이닝 시, 각 속성은 순서대로 적용되며 그 순서가 최종 렌더링 결과에 영향을 미칩니다.

2. Git 및 GitHub 기반 버전 관리 시스템
효율적인 소프트웨어 개발 및 협업을 위해 분산 버전 관리 시스템인 Git과 이를 활용한 원격 저장소 서비스인 GitHub를 사용합니다.

2-1. Git의 핵심 개념 및 기능
저장소 (Repository)	프로젝트의 모든 파일과 변경 이력이 저장되는 공간 (로컬 및 원격).	프로젝트의 단일 진실 공급원 (Single Source of Truth) 역할을 수행합니다.
커밋 (Commit)	파일 변경 사항을 하나의 버전 스냅샷으로 영구히 기록하는 행위.	특정 시점의 프로젝트 상태를 보존하여 언제든지 해당 버전으로 복원 가능성을 제공합니다.
브랜치 (Branch)	메인 흐름과 독립적으로 새로운 기능을 개발하거나 버그를 수정할 수 있는 작업 공간.	안정적인 메인 코드 베이스를 유지하면서 병렬적인 개발을 가능하게 합니다.

2-2. Git 명령어와 GitHub 연동 절차
git init	저장소 초기화	현재 디렉토리를 로컬 Git 저장소로 설정합니다. (최초 1회)
git remote add origin [URL]	원격 저장소 등록	로컬 저장소에 GitHub의 URL을 **origin**이라는 별칭으로 연결합니다. (최초 1회)
git add .	변경 파일 추적	수정 또는 생성된 파일을 다음 커밋에 포함되도록 **준비 영역 (Staging Area)**에 추가합니다.
git commit -m "메시지"	버전 기록	준비된 파일들의 변경 내용을 로컬 저장소에 확정 기록합니다.
git push origin [Branch]	원격 저장소 전송	로컬 커밋 이력을 GitHub 원격 저장소로 업로드하여 반영합니다.
git pull origin [Branch]	원격 내용 동기화	원격 저장소의 최신 내용을 로컬 저장소로 다운로드하여 동기화합니다.


4주차
📄 안드로이드 뷰 배치 레이아웃 및 버전 관리

1. 안드로이드 뷰 배치 레이아웃 유형별 분석
안드로이드 UI는 여러 **뷰(View)**를 특정 규칙에 따라 배치하는 뷰 그룹(ViewGroup), 즉 **레이아웃(Layout)**을 통해 구성됩니다. 최신 개발 방식인 Jetpack Compose에서는 전통적인 XML 레이아웃과 대응되는 개념을 사용합니다.

1-1. 전통적인 XML 레이아웃과 Compose 대응 요소
XML 레이아웃 (뷰 시스템)	: Compose 대응 요소	: 배치 특성
LinearLayout	Column, Row	단일 방향으로 자식 뷰를 수직(Column) 또는 수평(Row)으로 순차 배치합니다.
RelativeLayout	ConstraintLayout (Compose)	뷰 간의 상대적 위치 관계를 정의하여 복잡한 배치를 구현합니다. (Compose에서는 Modifier와 함께 사용)
FrameLayout	Box	뷰들을 겹쳐서 배치하며, 주로 단일 뷰를 표시하거나 뷰를 중첩하여 사용할 때 활용됩니다.
GridLayout	LazyVerticalGrid	뷰를 격자(Grid) 형태로 배치합니다. Compose에서는 Lazy 시리즈를 통해 스크롤 시 효율성을 높입니다.
RecyclerView	LazyColumn, LazyRow	스크롤 가능한 긴 리스트를 효율적으로 관리하며, 화면에 보이는 항목만 메모리에 올려 성능을 최적화합니다.

1-2. Compose의 Modifier 속성 중요성
Modifier의 역할: Compose에서 XML의 android:layout_width, android:gravity 등의 속성을 대체하며, Composable 함수의 모양, 크기, 배치, 상호작용 방식을 정의하는 데 사용되는 핵심 요소입니다.
체이닝 순서의 중요성: Modifier 속성은 체이닝되는 순서대로 적용되며, 이 순서에 따라 최종 렌더링 결과가 달라집니다. 예를 들어, background() 함수는 해당 시점까지의 크기에 맞춰 칠해지므로, 크기를 결정하는 함수(예: fillMaxWidth()) 다음에 배치하는 것이 중요합니다.

2. Git/GitHub 기반 협업 및 버전 관리 방안
2-1. Git/GitHub을 활용한 개발 환경 관리
버전 관리	프로젝트 변경 이력의 정확한 기록 및 추적	git add ., git commit -m "메시지"
원격 동기화	코드의 안전한 백업 및 팀원 간 코드 공유	git push origin [Branch], git pull origin [Branch]
개인 포트폴리오	과제 및 개인 프로젝트 코드를 GitHub Repository에 체계적으로 축적하여 개발 이력을 증명합니다.	git clone [URL] (프로젝트 복제)

2-2. 공용 PC 환경에서의 보안 관리 (SSH 기준)
공용 강의실 PC에서 GitHub를 사용할 경우 보안을 위해 SSH 키를 이용하며, 개인 키(id_ed25519)가 외부에 유출되지 않도록 엄격히 관리해야 합니다.
키 관리 원칙: 개인 키는 반드시 USB 드라이브 등 개인 보관 공간에 위치시키고, 공용 PC에는 복사/저장하지 않습니다.
세션 종료 시 정리: 수업 종료 시에는 반드시 다음 명령어를 실행하여 ssh-agent에 등록된 개인 키를 메모리에서 삭제해야 합니다.
ssh-add -D
이후 GitHub 로그아웃 및 USB 제거를 통해 보안을 완벽히 유지합니다.
