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
____________________________________________________________________________________________________________________________@Composable
fun Greeting(name: String, modifier: Modifier = Modifier) {
    Text(
        text = "Hello $name!",
        modifier = modifier
    )
}

@Preview(showBackground = true)
@Composable
fun GreetingPreview() {
    // 테마 적용
    ComposeLabTheme {
        Greeting("Android") 
    }
}
설명: @Composable 어노테이션이 붙은 Greeting 함수는 화면에 표시될 UI 요소(여기서는 Text)를 정의합니다. Compose는 이 함수들을 **트리 구조(Composable Tree)**로 조립하여 전체 화면을 구성합니다. @Preview 함수는 실제 기기나 에뮬레이터 없이도 UI를 미리 볼 수 있도록 지원하여 개발 효율성을 높입니다.
____________________________________________________________________________________________________________________________


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
____________________________________________________________________________________________________________________________
fun processText(text: String?) {
    // 널 안전 호출: text가 null이 아니면 .length 실행, null이면 null 반환
    val len: Int? = text?.length
    
    // 엘비스 연산자: len이 null이면 0을, 아니면 len의 값을 사용
    val safeLength: Int = len ?: 0 

    println("텍스트 길이: $safeLength")
}
설명: 코틀린은 변수 타입에 ?를 붙여 널 허용(Nullable) 변수를 명시적으로 구분합니다. ?. (안전 호출 연산자)는 수신 객체가 널이 아닐 때만 멤버 접근을 허용하여 NullPointerException 발생을 방지합니다. ?: (엘비스 연산자)는 앞의 표현식이 널일 경우 뒤의 값(대체 값)을 반환하도록 하여 널 처리 로직을 간결하게 만듭니다.
____________________________________________________________________________________________________________________________


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
____________________________________________________________________________________________________________________________
@Composable
fun LoginLayout() {
    Column(
        modifier = Modifier
            .fillMaxWidth()
            .padding(16.dp),
        horizontalAlignment = Alignment.CenterHorizontally // 자식 요소 중앙 정렬
    ) {
        Text("로그인", style = MaterialTheme.typography.headlineMedium)
        Spacer(modifier = Modifier.height(20.dp))

        // 비밀번호 입력창 (TextField)
        OutlinedTextField(
            value = "", 
            onValueChange = { /* ... */ },
            keyboardOptions = KeyboardOptions(keyboardType = KeyboardType.Password),
            modifier = Modifier.fillMaxWidth()
        )

        // 확인 버튼 (Button)
        Button(
            onClick = { /* 로그인 로직 */ }, 
            modifier = Modifier.fillMaxWidth().padding(top = 16.dp)
        ) {
            Text("확인")
        }
    }
}
설명: Column은 자식 요소들을 수직 방향으로 순차적으로 배치하는 가장 기본적인 컨테이너입니다. Modifier는 UI 요소의 크기, 패딩, 배경색 등 스타일과 레이아웃 속성을 선언적으로 정의하는 핵심 도구이며, 체이닝 순서에 따라 적용 결과가 달라질 수 있습니다.
____________________________________________________________________________________________________________________________
컴포즈커피
import androidx.compose.foundation.Image
import androidx.compose.foundation.layout.*
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.res.painterResource
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
// import com.example.app.R // 프로젝트의 R 파일 경로에 맞게 조정 필요

@Composable
fun ComposeCoffeeDisplay() {
    Column(
        modifier = Modifier.fillMaxSize().padding(16.dp),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center // 중앙 정렬
    ) {
        // 1. "Compose Coffee" 제목
        Text(
            text = "Compose Coffee",
            style = MaterialTheme.typography.headlineLarge,
            modifier = Modifier.padding(bottom = 32.dp)
        )

        // 2. 매장 이미지 (res/drawable 폴더에 이미지 파일이 있어야 합니다)
        // 예를 들어, compose_coffee_store.jpg 라는 파일이 있다면 R.drawable.compose_coffee_store
        Image(
            painter = painterResource(id = R.drawable.compose_coffee_store), // 이미지 리소스 ID
            contentDescription = "Compose Coffee 매장 전경",
            modifier = Modifier
                .fillMaxWidth(0.8f) // 화면 너비의 80% 차지
                .aspectRatio(16f / 9f) // 이미지 비율 유지 (가로:세로 = 16:9)
                .clip(MaterialTheme.shapes.medium) // 둥근 모서리 적용
        )

        // 3. 이미지와 텍스트 사이 간격
        Spacer(modifier = Modifier.height(32.dp))

        // 4. "위치: 우송대 정문 앞" 텍스트
        Text(
            text = "위치: 우송대 정문 앞",
            style = MaterialTheme.typography.titleLarge
        )
    }
}

@Preview(showBackground = true, widthDp = 360, heightDp = 640)
@Composable
fun ComposeCoffeeDisplayPreview() {
    // 실제 프로젝트의 테마를 여기에 적용할 수 있습니다.
    // YourAppTheme {
        ComposeCoffeeDisplay()
    // }
}
____________________________________________________________________________________________________________________________


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
____________________________________________________________________________________________________________________________
@Composable
fun WeightedRow() {
    Row(modifier = Modifier.fillMaxWidth()) {
        Text(
            "버튼 1 (1:3 비율)",
            modifier = Modifier
                .weight(1f) // 1의 비율
                .background(Color.Yellow)
        )
        Text(
            "버튼 2 (3:3 비율)",
            modifier = Modifier
                .weight(3f) // 3의 비율
                .background(Color.Cyan)
        )
    }
}
설명: Row는 자식 뷰를 수평 방향으로 배치하는 컨테이너입니다. Modifier.weight(Float)는 해당 컨테이너 내에서 남은 공간을 비율에 따라 나누어 가지도록 정의합니다. 이처럼 Compose는 XML의 layout_weight 속성 대신 Modifier를 사용하여 유연하고 직관적인 레이아웃 구성을 가능하게 합니다.
____________________________________________________________________________________________________________________________


5주차
📄 안드로이드 이벤트 처리 및 리소스 관리

1. 사용자 이벤트 처리 및 상태 관리
사용자 이벤트는 애플리케이션과 사용자 간의 상호작용을 의미하며, 이를 처리하기 위해 리스너(Listener) 패턴과 상태 관리 개념이 활용됩니다.
1-1. 이벤트 처리의 구조 및 분류
뷰 이벤트 (View Event)	버튼 클릭, 텍스트 입력 등 특정 UI 요소에서 발생하는 이벤트.	Composable 함수의 onClick 등 람다 함수 매개변수를 통해 이벤트 로직을 직접 구현합니다. (전통적인 뷰 시스템의 리스너 역할)
터치 이벤트	화면 터치, 드래그, 제스처 등 좌표 기반의 저수준(Low-Level) 이벤트.	Modifier.pointerInput 등을 활용하여 터치 다운(onDown), 이동(onMove), 업(onUp) 등의 동작을 처리합니다.
키 이벤트	물리적 버튼(볼륨, 시스템 뒤로가기)이나 키보드 입력 시 발생하는 이벤트.	onKeyDown(), onKeyUp() 함수를 재정의하여 처리하며, 최근 뒤로가기 이벤트는 OnBackPressedCallback 함수 사용이 권장됩니다.

1-2. Compose의 상태 관리 기초
상태 저장 (State Storage): remember 및 mutableStateOf를 사용하여 UI 상태(예: 카운터 숫자, 체크박스 상태)를 저장하고 관리합니다.
리렌더링 (Re-rendering): 상태가 업데이트되면 Compose 시스템이 자동으로 해당 상태를 사용하는 Composable 함수만 다시 실행하여 화면을 갱신합니다. 이를 **재구성(Recomposition)**이라고 합니다.

2. 애플리케이션 리소스의 활용 및 관리
리소스(Resource)는 이미지, 문자열, 색상 등 코드가 아닌 외부에 분리하여 관리되는 파일들을 의미하며, 이는 코드의 가독성과 유지보수성, 다국어 지원 및 호환성을 향상시킵니다.

2-1. 리소스의 종류 및 접근 방식
문자열 (String)	res/values/strings.xml	다국어 지원, 중앙 집중식 문자열 관리.	stringResource(id = R.string.식별자)
색상 (Color)	res/values/colors.xml	앱 테마 색상, 색상 표준화.	colorResource(id = R.color.식별자)
이미지/드로어블 (Drawable)res/drawable/UI 구성 요소의 배경, 아이콘, 이미지 등.painterResource(id = R.drawable.식별자)

2-2. 리소스 조건 설정 및 호환성
리소스 조건 설정: res/ 폴더 내에 -ko, -en, -land, -mdpi 등의 **조건자(Qualifier)**를 사용하여 디렉터리를 생성하면, 기기의 설정(언어, 화면 방향, 밀도 등)에 따라 적절한 리소스를 자동으로 선택하여 적용합니다. (예: values-ko, drawable-land)
폰 크기 호환성 단위:
dp (Density-independent pixels): 화면 밀도(DPI)에 독립적인 단위로, 실제 픽셀 수와 관계없이 모든 화면에서 물리적인 크기를 유사하게 유지하도록 설계되었습니다. 크기 지정 시 주로 사용됩니다.
sp (Scale-independent pixels): 폰트 크기 지정에 사용되며, dp와 유사하게 밀도 독립적이지만, 사용자 설정의 글꼴 크기 배율에 따라 크기가 조절되어 접근성을 높입니다.
____________________________________________________________________________________________________________________________
@Composable
fun SimpleCounter() {
    // 1. remember와 mutableStateOf를 사용하여 '상태'를 저장
    val count = remember { mutableStateOf(0) } 

    // 2. Button 컴포저블: 사용자 '이벤트' (onClick) 처리
    Button(onClick = { 
        count.value++ // 상태 업데이트
    }) { 
        // 3. Text 컴포저블: 상태 변화 시 '재구성(Recomposition)' 발생
        Text("클릭 횟수: ${count.value}") 
    }
}
설명: remember와 mutableStateOf는 UI 상태를 저장하는 데 사용되며, 상태(count.value)가 변경되면 해당 상태를 사용하는 모든 Composable 함수가 자동으로 **재구성(Recomposition)**되어 화면을 갱신합니다. 이는 전통적인 뷰 시스템에서 개발자가 직접 setText()를 호출해야 했던 명령형(Imperative) 방식과 대비되는 선언형(Declarative) 방식의 핵심입니다.
____________________________________________________________________________________________________________________________
스톱워치
import androidx.compose.foundation.layout.*
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp
import kotlinx.coroutines.delay

@Composable
fun StopwatchApp() {
    // 상태 정의: 시간(초) 및 실행 상태
    val seconds = remember { mutableIntStateOf(0) }
    val isRunning = remember { mutableStateOf(false) }

    // 부수 효과: isRunning이 true일 때 1초마다 시간 증가
    LaunchedEffect(isRunning.value) { 
        while (isRunning.value) {
            delay(1000)
            seconds.intValue++ 
        }
    }

    Column(
        modifier = Modifier.fillMaxSize().padding(24.dp),
        horizontalAlignment = Alignment.CenterHorizontally,
        verticalArrangement = Arrangement.Center
    ) {
        // 시간 표시 UI
        Text(
            text = formatTime(seconds.intValue),
            style = MaterialTheme.typography.displayLarge
        )
        Spacer(modifier = Modifier.height(40.dp))

        Row(horizontalArrangement = Arrangement.SpaceEvenly, modifier = Modifier.fillMaxWidth(0.8f)) {
            // 시작/중지 버튼
            Button(
                onClick = { isRunning.value = !isRunning.value },
                colors = ButtonDefaults.buttonColors(
                    containerColor = if (isRunning.value) Color.Red else Color.Green
                )
            ) {
                Text(if (isRunning.value) "일시 중지" else "시작")
            }

            // 초기화 버튼
            Button(
                onClick = { 
                    isRunning.value = false
                    seconds.intValue = 0 
                },
                enabled = !isRunning.value && seconds.intValue > 0
            ) {
                Text("초기화")
            }
        }
    }
}

// 시간 포맷 (분:초)
private fun formatTime(totalSeconds: Int): String {
    val minutes = totalSeconds / 60
    val secs = totalSeconds % 60
    return String.format("%02d:%02d", minutes, secs)
}

@Preview(showBackground = true)
@Composable
fun StopwatchPreview() {
    StopwatchApp()
}
____________________________________________________________________________________________________________________________


6주차
📄 안드로이드 사용자 피드백 및 최신 UI/버전 관리 기법

1. 다이얼로그와 알림을 활용한 사용자 피드백 시스템
사용자에게 중요한 정보나 즉각적인 결정을 요구할 때 다이얼로그(Dialog)를 사용하며, 앱 외부에서 정보를 전달할 때 알림(Notification)을 사용합니다.
1-1. 다이얼로그 유형 및 역할
다이얼로그는 사용자 상호작용의 필수적인 일시적 팝업 형태이며, 사용자의 즉각적인 주의와 응답을 요구합니다.
AlertDialog	오류 메시지, 최종 확인 등 결정을 요구하는 간단한 메시지 전달.	타이틀, 내용, 버튼(긍정/부정/중립)으로 구성되며, 사용자가 버튼을 누르기 전까지 다른 작업을 방해(모달)할 수 있습니다.
DatePickerDialog	사용자에게 날짜 선택 기능을 제공.	달력 형태로 날짜를 선택하도록 유도하여 정확한 데이터 입력을 돕습니다.
ProgressDialog	서버 통신이나 대용량 파일 처리 등 장시간 작업 진행 중임을 표시.	사용자에게 대기 시간을 인지시켜 이탈을 방지합니다.

1-2. 알림 (Notification) 시스템
알림은 앱이 백그라운드에 있거나 실행 중이지 않을 때 사용자에게 정보를 전달하는 핵심 비동기 통신 채널입니다.
구조: 알림은 반드시 **채널(Channel)**을 통해 사용자에게 전달되어야 합니다. 채널을 이용하면 사용자가 알림의 중요도나 종류별로 설정(소리, 진동 여부 등)을 개별적으로 제어할 수 있습니다.
고급 기능: 알림은 단순 텍스트 외에 액션 버튼 추가, **원격 입력(Remote Input)**을 통한 즉각적인 응답, 진행 상황을 표시하는 프로그레스 바(Progress Bar) 등 다양한 형태로 확장될 수 있습니다.

2. Jetpack Compose 고급 상태 및 효과 관리
Jetpack Compose는 선언형 UI 모델을 구현하며, 특히 **상태(State)**의 변화를 효율적으로 관리하여 UI를 갱신합니다.
재구성 (Recomposition)	데이터 상태(State)가 변경될 때, 해당 상태를 사용하는 Composable 함수만 다시 호출되어 UI가 갱신되는 과정.	mutableStateOf, remember
부수 효과 (Side Effect)	컴포저블 함수 외부의 요소(예: 데이터베이스, 네트워크, 리스너)와 상호작용할 때 발생하는 비동기적인 작업.	LaunchedEffect, DisposableEffect
LaunchedEffect	컴포지션 생명주기 동안 코루틴을 실행하여 부수 효과(예: 비동기 데이터 로드)를 안전하게 처리합니다. 키(Key)가 변경되면 기존 코루틴을 취소하고 새로 시작합니다.	코루틴(Coroutine), 키(Key)
DisposableEffect	리스너 등록/해제와 같이 **리소스 정리(Cleanup)**가 필요한 부수 효과를 관리합니다. 컴포지션이 종료되거나 키가 변경될 때 onDispose 블록의 정리 로직이 실행됩니다.	onDispose, 메모리 누수 방지
____________________________________________________________________________________________________________________________
@Composable
fun GameScreen(viewModel: GameViewModel = viewModel()) {
    // StateFlow를 관찰하여 UI 상태를 받음. 상태 변경 시 자동 Recomposition
    val uiState by viewModel.uiState.collectAsState() 

    // ViewModel이 관리하는 상태를 사용하여 UI 렌더링
    Text(
        text = "점수: ${uiState.currentUserData.totalScore}",
        // ... (다른 UI 요소)
    )

    // View 이벤트는 ViewModel로 전달 (Upstream)
    Button(onClick = { viewModel.addPoint() }) {
        Text("버블 맞추기")
    }
}
설명: ViewModel은 비즈니스 로직을 수행하며 StateFlow를 통해 UI에 필요한 **상태(UI State)**를 발행합니다. collectAsState() 함수는 이 StateFlow를 관찰(Observe)하여 값이 변경될 때마다 UI를 자동으로 갱신합니다. 이를 통해 단방향 데이터 흐름(UDF) 원칙을 확립하여 UI 계층(View)과 비즈니스 로직(ViewModel)의 관심사 분리를 달성합니다.
____________________________________________________________________________________________________________________________
버블버블
import androidx.compose.foundation.background
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.shape.CircleShape
import androidx.compose.material3.MaterialTheme
import androidx.compose.material3.Text
import androidx.compose.runtime.Composable
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.draw.clip
import androidx.compose.ui.graphics.Color
import androidx.compose.ui.tooling.preview.Preview
import androidx.compose.ui.unit.dp

@Composable
fun BubbleGameScreenshotView() {
    Column(
        modifier = Modifier.fillMaxSize().background(Color(0xFFFBF8F9)), // 이미지 배경색과 유사하게 설정
        horizontalAlignment = Alignment.CenterHorizontally // 점수 텍스트 중앙 정렬
    ) {
        // 1. 점수 표시 텍스트
        Text(
            text = "Score: 0",
            style = MaterialTheme.typography.headlineMedium,
            modifier = Modifier.padding(top = 16.dp, bottom = 100.dp) // 위쪽 여백과 아래쪽 여백으로 위치 조정
        )

        // 2. 버블들을 포함할 Row (수평 배치)
        Row(
            modifier = Modifier.fillMaxWidth(),
            horizontalArrangement = Arrangement.SpaceEvenly, // 버블들을 고르게 배치
            verticalAlignment = Alignment.CenterVertically
        ) {
            // 왼쪽 버블 (하늘색)
            Box(
                modifier = Modifier
                    .size(60.dp) // 버블 크기
                    .clip(CircleShape) // 원형으로 클리핑
                    .background(Color(0xFFB3E0E6)) // 이미지의 하늘색 버블과 유사한 색상
            )
            // 오른쪽 버블 (갈색)
            Box(
                modifier = Modifier
                    .size(60.dp) // 버블 크기
                    .clip(CircleShape) // 원형으로 클리핑
                    .background(Color(0xFFB0946B)) // 이미지의 갈색 버블과 유사한 색상
            )
        }
    }
}

@Preview(showBackground = true, widthDp = 360, heightDp = 640)
@Composable
fun BubbleGameScreenshotPreview() {
    // YourAppTheme { // 실제 프로젝트의 테마 적용
        BubbleGameScreenshotView()
    // }
}
____________________________________________________________________________________________________________________________
7주차
📄 안드로이드 백엔드 서비스(BaaS) 및 공식 아키텍처(MVVM)
1. 안드로이드 공식 아키텍처: MVVM 구조 분석
복잡한 애플리케이션의 유지보수성, 테스트 용이성, 확장성을 확보하기 위해 Google은 MVVM(Model-View-ViewModel) 아키텍처 패턴을 공식적으로 권장합니다.
1-1. MVVM의 핵심 원칙 및 구성 요소
View (UI 계층)	화면 표시 및 사용자 상호작용(이벤트) 처리.	화면 렌더링 및 사용자 이벤트 ViewModel로 전달. (Activity, Composable 등)
ViewModel	View가 필요로 하는 상태(State)를 관리하고, View의 요청에 따라 비즈니스 로직을 수행 (Model과 통신).	View를 위한 UI 상태 관리 및 데이터 계층과의 상호작용 중개.
Model (데이터 계층)	애플리케이션의 비즈니스 로직 및 데이터 관리 (Repository, Service, DB 등).	**단일 진실 공급원(SSOT)**으로서 데이터의 일관성 및 무결성 보장.

1-2. 단방향 데이터 흐름 (UDF)
MVVM 구조는 **단방향 데이터 흐름(Unidirectional Data Flow, UDF)**을 따르는 것이 중요합니다.
상태 흐름: 데이터 계층(Model) → ViewModel → UI 계층(View)으로 **하향식(Downstream)**으로 흐르며 UI를 갱신합니다.
이벤트 흐름: 사용자 상호작용(이벤트)은 UI 계층 → ViewModel로 **상향식(Upstream)**으로 전달되어 상태를 변경합니다.
적용: 스톱워치 게임 사례에서, Repository가 데이터의 SSOT를 갱신하면, ViewModel의 StateFlow를 통해 UI 상태가 변경되고, View는 이를 관찰하여 화면을 재구성(Recomposition)합니다.

2. 백엔드 서비스(BaaS) 비교: Firebase vs Supabase
BaaS는 서버 구축 및 관리에 대한 부담 없이 인증, 데이터베이스, 스토리지 등의 백엔드 기능을 앱에 즉시 연동할 수 있게 해주는 서비스입니다.
핵심 특징	NoSQL 기반 (Cloud Firestore), Google 생태계 통합.	PostgreSQL 기반 (RDBMS), 오픈 소스 및 자체 호스팅 가능.
데이터베이스	NoSQL (문서 기반), 실시간 동기화에 최적화.	SQL (관계형), 전통적인 관계형 데이터 관리에 유리.
디자인 철학	개발 속도와 확장성을 최우선.	데이터 제어, 보안, SQL 사용성을 중시 ('오픈소스 Firebase' 지향).
주요 기능	인증, FCM(클라우드 메시징), 리얼타임 DB, Storage.	인증, 실시간 구독, 자동 API 생성, 스토리지.
검색 기능	(Cloud Firestore) 인덱스 기반 검색.	하이브리드 검색 (tsvector + pgvector) 지원으로 고도화된 AI 검색 가능.
연동	Android SDK를 통해 클라이언트에서 DB 및 서비스에 직접 접근.	클라이언트 SDK를 통해 DB 및 서비스에 직접 접근.

3. Firebase를 활용한 원격 기능 구현 사례
Firebase는 특히 푸시 알림(FCM) 구현에서 핵심적인 역할을 수행합니다.
FCM 구조: 앱은 FCM 서버로부터 **등록 토큰(Registration Token)**을 발급받아 서버에 전달합니다. 서버는 이 토큰을 이용해 Firebase 서버에 알림 메시지를 전송하고, Firebase 서버가 메시지를 해당 앱 인스턴스에 푸시합니다.
안드로이드 구현:
서비스 컴포넌트: MyFirebaseMessageService를 생성하여 FCM 서버가 보낸 메시지 및 토큰을 수신하고 처리합니다.
매니페스트 설정: AndroidManifest.xml에 해당 서비스 컴포넌트를 등록해야 FCM이 정상적으로 작동합니다.
활용: 버블 게임의 종료 조건 충족 시, AlertDialog를 통해 사용자에게 즉각적인 피드백을 제공하고, **알림(Notification)**을 통해 앱 외부에서도 게임 종료 상황을 전달하는 등의 방식으로 통합될 수 있습니다.
____________________________________________________________________________________________________________________________
1. 변경된 모든 파일을 스테이징 영역에 추가 (추적 준비)
git add . 

2. 스테이징된 파일들을 로컬 저장소에 버전으로 기록 (Commit)
# 메시지에는 커밋 내용을 명확히 요약해야 함
git commit -m "feat: [기능 구현] 6주차 MVVM 구조 구현 및 스톱워치 기능 추가" 

3. 로컬 저장소의 커밋 이력을 원격 저장소(origin)의 main 브랜치로 전송 (Push)
git push origin main
설명: Git은 개발 과정 중 파일의 변경 사항을 **커밋(Commit)**이라는 스냅샷 단위로 기록하여 버전 관리를 수행합니다. 위 명령어는 작업 디렉토리의 변경 내용을 add를 통해 스테이징 영역에 올리고, commit으로 로컬 저장소에 확정 기록한 후, push를 통해 GitHub 원격 저장소에 반영하는 표준적인 버전 기록 및 동기화 절차입니다. 이는 프로젝트의 백업, 이력 추적, 그리고 팀원 간 코드 공유를 위한 필수적인 과정입니다.
____________________________________________________________________________________________________________________________
