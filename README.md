# backEndInterview

## 자바
- JVM 이란 무엇이고 왜 필요한지 설명해 주실 수 있을까요? JVM의 스택과 힙메모리 영역에 대해 아는 만큼 설명해 주실 수 있을까요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
<p>자바 가상 머신(Java Virtual Machine)을 줄여 부르는 JVM의 역할은 바이트 코드로 컴파일된 자바 애플리케이션을 클래스 로더를 통해 읽어 자바 API와 함께 실행하는 것입니다.</p>
<p>JVM을 사용함으로 개발자가 작성하는 java 파일을 다양한 환경에서 실행할 수 있습니다.</p>
<p>다른 환경에서 만들어진 바이트 코드를 해당 OS의 JVM이 알맞게 기계어로 바꿔서 읽기 때문입니다.</p>
<p>즉, 모든 환경에서 사용할 수 있게 호환성을 위해 JVM이 필요합니다.</p>
  
<p>Stack과 Heap 영역은 JVM의 실행 데이터 영역(Runtime Data Area) 안에 구성되어 있습니다.</p>
<p>Stack 영역은 프로그램 실행 중 발생하는 메소드 호출과 복귀에 대한 정보를 저장합니다.</p>
<p>Heap 영역은 사용자가 관리하는 인스턴스가 생성되는 공간으로 객체를 동적으로 생성하면 인스턴스가 Heap 영역의 메모리에 할당되어 사용됩니다.</p>

</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">
한마디로 정의해보자면 OS에 종속받지 않고 CPU가 자바를 인식하고 실행할 수 있게 해주는 가상 컴퓨터입니다
한번 쓴 것은 어디서든지 읽혀야한다 라는 철학으로 만들어진 자바이다 컴파일된 뒤 바이트코드로 변형된 자바를
어느 OS든 사용할 수 있게 하기 위해 JVM이 필요하다고 생각합니다

일반 프로그램들은 OS에 종속되어있어 OS가 바뀌면 그 OS에 적용하기 위해 많은 노력이 필요한데
자바 프로그램은 JVM이라는 가상 컴퓨터를 중간에 끼워 사용하기에 JVM만 OS에 맞춰 바꿔주면
자바 소스코드를 컴파일러가 JVM이 인식할 수 있는 자바 바이트 코드로 변환해서 넘겨주고 
이를 JVM에서 바이너리 코드로 바꿔 OS가 이해할 수 있게 해석해줍니다

스택은 자바 프로그램이 컴파일 되어 생성되는 바이트 코드가 아닌 실제 실행할 수 있는
기계어로 작성된 프로그램을 실행시키는 영역입니다 각종 형태의 변수나 스레드나 메서드의 정보를 저장합니다

힙메모리는 객체를 저장하는 공간으로서 new 연산자로 생성되는 객체와 배열을 저장합니다
</div>
</details>

- Java가 컴파일되는 과정은 어떻게 되는지 설명해 주실 수 있을까요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
<p>개발자가 .java로 되어있는 파일을 만들어 코드를 작성합니다. 그 파일에 작성한 코드가 자바 소스 코드가 됩니다.</p>
<p>인텔리제이같은 툴을 쓴다면 Build를 사용하여 소스파일을 컴파일합니다.</p>
<p>자바 컴파일러(javac)가 작성한 자바 소스 코드(.java)를 읽어 바이트 코드(.class)로 컴파일을 하는 것을 말합니다.</p>
<p>컴파일된 해당 바이트 코드(.class)는 JVM의 클래스 로더가 전달받습니다.</p>
 
<p>클래스 로더는 동적 로딩을 통해 필요한 클래스들을 로딩 및 링크하여 JVM내로 로드합니다.</p>
<p>JVM 내에 있는 실행 엔진(Execution engine)에 의해 기계어로 해석되어 실행 데이터 지역(Runtime Data Areas)에 배치됩니다.</p>
<p>java가 설치된 os라면 기계어로 해석된 파일을 실행할 수 있게됩니다.</p>
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">
개발자가 자바로 코드를 작성하면 자바 소스코드 파일인 .java 파일이 만들어지고
이를 자바 컴파일러가 컴파일해서 바이트코드 파일인 .class 파일을 만듭니다
이를 JVM 클래스 로더에게 전달해 검증해서 JVM 메모리에 올리게 되고 실행 엔진에 의해 실행됩니다
이때 인터프리터나 JIT 컴파일러에 의해 바이너리 코드로 변환된다고 설명드릴 수 있습니다
</div>
</details>

- 클래스와 인스턴스의 차이에 대해 설명해 주실 수 있을까요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
<p>클래스는 객체가 어떤 속성을 갖는지 어떤 모양을 갖는지 미리 틀로 정해 놓는 설계도입니다.</p>
<p>인스턴스는 그 설계도를 통해 만들어진 객체를 말합니다.</p>
<p>클래스 안에서 인스턴스는 필드와 메소드만 바꿔서 다양하게 만들어 줄 수 있습니다.</p>
<p>이렇게 클래스 안에서 메소드를 실행시키는 객체를 만드는 행위를 인스턴스화라고 합니다.</p>
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">
클래스는 변수와 메서드의 집합 이고 쉽게 말해 설계도와 같다고 볼 수 있습니다
인스턴스는 그런 클래스를 바탕으로 소프트웨어 세계에 구현된 구체적인 실체라고 볼 수 있습니다
oop의 관점에서 보자면 객체가 메모리에 할당되어 실제 사용될때 인스턴스라고 할 수 있습니다
</div>
</details>

- JVM의 구조에 대해 설명해 주실 수 있을까요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
<p>JVM의 구조는 클래스 로더(Class Loader), 실행 엔진(Execution engine), 실행 데이터 영역(Runtime Data Area) 등으로 이루어져 있습니다.</p>
<ul>  
<li>클래스 로더(Class Loader) : JVM 내로 바이트 코드(.class)를 로드하고, 링크를 통해 배치하는 작업을 합니다.</li>
<li>실행 엔진(Execution engine) : 클래스 로더에 의해 실행 데이터 영역에 배치된 바이트 코드(.class)를 실행하는 역할을 합니다.</li>
<li>실행 데이터 영역(Runtime Data Area) : JVM의 메모리 영역으로 Method영역, Heap 영역, Stack 영역, 네이티브 메소드 스택 영역(Native Method Library)으로 구성되어 있습니다.</li>
<ul>  
<li>Method영역 : 클래스의 멘버 변수, 메소드 정보, Type 정보, static, final 변수 등이 생성됩니다.</li>
<li>Heap 영역 : 사용자가 관리하는 인스턴스가 생성되는 공간으로 객체를 동적으로 생성하면 인스턴스가 Heap 영역의 메모리에 할당되어 사용됩니다.</li>
<li>Stack 영역 : 프로그램 실행 중 발생하는 메소드 호출과 복귀에 대한 정보를 저장합니다.</li>
<li>네이티브 메소드 스택 영역(Native Method Library) : Java 이외의 C언어와 같은 다른 언어가 필요한 경우, JNI 기술을 통해서 네이티브 메소드들이 바이트 코드로 변환되면서 사용되는 영역입니다.</li>
<li>PC Register : 스레드가 시작될 때 생성되며 현재 수행 중인 JVM 명령의 주소를 갖고 있습니다.</li>
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">
JVM의 구조는 클래스 로더(Class Loader), 실행 엔진(Execution engine), 실행 데이터 영역(Runtime Data Area), 가비지 컬렉터 (Garbage Collector)등으로 이루어져 있습니다

- 클래스로더는 동적으로 클래스를 로딩해주는 역할을 하는데 class파일을 묶어서 JVM이 운영체제로부터 할당받은 메모리 영역인 Runtime Data Area로 적재합니다
- 실행엔진은 클래스 로더에 의해 실행 데이터 영역의 Method Area에 배치됩니다 그리고 배치된 바이트코드를 실행하는 역할을 합니다
- 가비지컬렉터는 더는 사용하지 않는 메모리를 자동으로 회수해줍니다 heap메모리 영역에 생성된 객체들 중에 참조되지 않은 객체들을 탐색 후 제거하는 역할을 하며
해당 역할을 하는 시간은 정확히 언제인지 모릅니다 가비지컬렉터 역할을 하는 스레드를 제외한 나머지 모든 스레드들은 일시정지 상태가 됩니다
- 실행 데이터 영역은 메서드영역, 힙영역, 스태경역, 네이티브메서드 스택영역으로 구성되어있습니다
</div>
</details>

