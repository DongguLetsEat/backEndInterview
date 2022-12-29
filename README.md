# backEndInterview

## 자바
- JVM 이란 무엇이고 왜 필요한지 설명해 주실 수 있을까요? JVM의 스택과 힙메모리 영역에 대해 아는 만큼 설명해 주실 수 있을까요?
<details>
<summary>계현준</summary>
<div markdown="1">
  <p>JVM 이란 Java Virtual Machine으로 (Java Byte Code를) 어떤 운영체제에서든지 종속받지 않고 실행 가능하도록 만들어주는 역할을 합니다.</p>
  </br>
  <p>스택은 정적 메모리가 저장되는 영역입니다.</p>
  <p>즉, 스택은 원시타입의 데이터의 값과 힙 영역에서 생성된 Object 타입의 참조 값 등이 저장되며 함수가 호출될 때 사용되는 메모리입니다.</p>
  <p>힙 영역은 동적 메모리가 저장되는 영역입니다.</p>
  <p>즉, 힙은 프로그램을 실행하면서 생성한 모든 인스턴스들을 저장합니다.</p>
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
 <p>먼저 개발자가 자바 소스코드(.java)를 작성합니다.</p>
 <p>그리고 자바 컴파일러가 자바 소스파일을 컴파일한 후 컴파일된 바이트 코드를 JVM의 클래스로더에게 전달합니다.</p>
 <p>전달 받은 클래스 로더는 동적로딩을 통해 필요한 클래스들을 로딩 및 링크하여 런타임 데이터 영역, 즉 JVM의 메모리에 올립니다.</p>
 <p>마지막으로 실행엔진(Execution Engine)에서 JVM 메모리에 올라온 바이트 코드들을 명령어 단위로 하나씩 가져와서 실행하게 됩니다.</p>
 <br/> 
  자바 소스코드 작성 -> 자바 컴파일러에서 소스파일을 컴파일 -> 컴파일 된 바이트 코드를 클래스로더에 전달 -> 클래스로더에서 필요한 클래스들을 로딩 -> 로딩된 테이터들을 런타임 영역(JVM의 메모리)에 올림 -> 실행엔진에서 JVM 메모리에 올라와 있는 바이트 코드를 명령어 단위로 실행
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
<p>클래스란 객체를 만들어 내기 위한 설계도라고 볼 수 있습니다. 자세하게는 연관 되어 있는 변수와 메서드의 집합이라고 할 수 있습니다.</p> 
<p>인스턴스란 설계도를 바탕으로 스프트웨어 세계에 구현 된 구체적인 실체라고 볼 수 있습니다. 실체화 된 인스턴스는 메모리에 할당됩니다.</p>
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
  
  ![image](https://user-images.githubusercontent.com/95573777/209838624-fb9dc06f-9b0a-4e2a-8599-3def89e8b8fc.png)

  <p>JVM은 클래스 로더(Class Loader), 실행 엔진(Execution engine), 가비지 컬렉터 (Garbage Collector), 실행 데이터 영역(Runtime Data Area)의 구조로 이루어져 있습니다.</p>
  <p>클래스 로더는 동적으로 클래스를 로딩해주는 역할을 합니다. 또한 클래스 로더는 java소스를 컴파일 했을 때 생기는 class파일을 묶어서 JVM이 운영체제로 부터 할당받은 런타임 데이터 영역에 올립니다.</p>
  <p>실행 엔진은 바이트 코드들을 명령어 단위로 읽어서 실행하느 역할을 합니다. 이러한 실행엔진은 클래스 로더에 의해 실행되고 런타임 데이터 영역의 메서드 영역에 배치되어 실행됩니다.</p>
  <p>가비지 컬렉터는 더는 사용하지 않는 메모리를 자동으로 회수해 주는 역할을 합니다.</p>
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
  
## 자료구조,알고리즘
- 스택과 큐에 대한 개념과 활용 예시를 설명해 주실 수 있을까요?
<details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>스택은 LIFO(Last In First Out) 형태의 자료구조로 책을 쌓는 것처럼 가장 마지막에 넣은 데이터가 가장 먼저 삭제되는 자료구조입니다.</p>
    <p>스택은 자료의 순서를 뒤집는데 유용하게 사용됩니다. 스택은 LIFO구조로 되어 있기 때문에 스택에 넣은 요소를 다시 꺼내어 배열에 저장하면 데이터의 순서가 뒤집혀 저장됩니다.</p>
    <br/>
    <p>큐는 FIFO(First In First Out)의 형태의 자료구조로 가장 먼저 삽입된 자료가 가장 먼저 삭제되는 자료구조입니다. </p>
    <p>큐는 데이터가 입력된 시간순서 대로 처리되어야 하는 FIFO구조로 되어있기 때문에 프린터 출력처리나 은행창구의 대기 같이 대기열이 필요한 경우 사용합니다.</p>
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
<p>스택은 (LIFO) Last in first out 형태로 데이터를 저장하는 구조입니다.</p>
<p>가장 마지막에 들어온 데이터가 가장 먼저 나가고 가장 먼저 들어온 데이터가 가장 마지막에 나가는 구조입니다.</p>
<p>스택 활용 예시로는  1. 웹 브라우저 뒤로 가기를 하면 가장 나중에 열린 페이지부터 뒤로 가기 실행이 되는 스택 구조 2. 문서 작업에서 ctrl + z</p>
<br/>
<p>큐는 (FIFO) First in first out 형태로 데이터를 저장하는 구조입니다.</p>
<p>줄을 서서 기다리는 것을 의미하며 선입선출로 가장 먼저 들어온 데이터가 나가고 가장 마지막에 들어온 데이터가 마지막에 나가는 구조입니다.</p>
<p>예를 들자면 마치 뚫려있는 프링글스 통에 맨 밑에 과자가 먼저 빠져나가는 것입니다.</p>
<p>큐 활용 예시로는 프린트 출력이 있는데 가장 먼저 인쇄를 눌러 대기열에 오른 프린트가 먼저 출력</p>
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">
스택은 책상에 책을 쌓는 것처럼 차곡차곡 쌓아 올린 형태를 가진 자료구조입니다
책이 쌓인 것을 상상해보면 알겠지만 정해진 방향으로만 삽입, 삭제를 할 수 있습니다
LIFO 방식으로 가장 마지막에 삽입된 데이터가 가장 먼저 삭제된다는 특징을 가집니다

큐는 길게 줄을 서서 기다리는 사람들의 형태를 가진 자료구조입니다
줄을 서있는 모습을 상상해보면 알겠지만 한쪽 방향에서만 삽입 한쪽 방향에서만 삭제를 할 수 있습니다
FIFO 방식으로 가장 먼저 삽입된 데이터가 가장 먼저 삭제된다는 특징을 가집니다

스택의 실제 활용예시는 웹브라우저 뒤로가기 버튼이 있습니다

큐의 실제 활용예시는 프린트 출력인데 가장 먼저 인쇄를 눌러 대기열에 오른 프린트가 먼저 출력한다는걸 들을 수 있습니다
</div>
</details>
  
- 트리와 그래프를 비교해서 설명해 주실 수 있을까요? 
<details>
  <summary>계현준</summary>
  <div markdown="1">
    <p> 먼저 트리는 그래프라는 큰 집합 안에 속해 있는 자료구조 입니다.</p>  
    <p> 그래프는 LinkedList를 기반으로 노드와 노드 간을 연결하는 간선으로 구성되고 계층이 없는 자료구조입니다. </p>  
    <br/>
    <p> 트리는 그래프의 한 종류로 루트 노드가 존재하고, 부모-자식 관계로 이루어진 계층적인 모델의 자료구조입니다.</p>  
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
<p>트리는 그래프의 한 종류인 비순환 그래프에 해당되는 자료구조입니다.</p> 
<p>최상단에 하나의 루트 노드를 가지고 있고, 루트 노드에서부터 반드시 1개의 경로만을 가지고 밑에 노드로 연결되는 구조입니다.</p>
<p>1개의 경로만으로 연결되기에 트리는 사이클이 존재하지 않는 방향 그래프입니다.</p>
<p>이처럼 1개의 부모 노드만을 가지는 트리를 계층 모델이라고 부릅니다.</p>
<p>트리의 대표적인 예시로는 컴퓨터의 Dirctory 구조가 있습니다.</p>
<br/>
<p>그래프는 노드와 엣지로 이루어진 자료 구조로 방향,순환에 따라 종류를 나눌 수 있습니다.</p>
<p>그래프는 루트 노드가 없고, 노드 사이에 2개 이상의 경로가 존재할 수 있어 네트워크 모델이라고 부릅니다.</p>
<p>루트나 부모-자식 개념이 없이 연결된 그래프의 예시로는 지하철 노선도가 있습니다.</p>
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">
트리는 그래프에 포함되며 둘 다 노드와 노드간 연결하는 간선으로 구성된 자료구조 입니다

먼저 트리는 두 개의 노드 사이에 반드시 1개의 경로만을 가지며 사이클이 존재하지 않는 방향 그래프입니다

루트와 부모 노드를 가지는 특징이 있으며 회사의 조직도가 트리의 대표적인 예시라고 할 수 있습니다

그래프는 노드 사이에 둘 이상의 경로가 가능하며 순환, 비순환 사이클이 존재하며 방향, 무방향 둘 다 가능합니다

루트나 부모-자식 개념이 없으며 지하철 노선도가 그래프의 대표적인 예시라고 할 수 있습니다
</div>
</details>  

- 시간복잡도와 공간복잡도가 무엇인지 설명해 주실 수 있을까요?
<details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>시간복잡도는 알고리즘이 어떤 문제를 해결하는데 걸리는 시간을 의미하고 공간복잡도는 작성한 프로그램이 얼마나 많은 공간(메모리)을 차지하느냐를 분석하는 방법입니다.</p>
    <br/>
    <p>+복잡도란 알고리즘 성능을 평가하기 위한 척도이며 복잡도가 낮을수록 좋은 알고리즘이라고 합니다.</p>
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
<p>시간복잡도는 알고리즘이 문제를 해결하는데 걸리는 시간을 의미합니다.</p>
<p>공간복잡도는 알고리즘이 문제를 해결하는데 얼마나 많은 공간 즉 메모리를 차지 하는 지를 의미합니다.</p>
<p>프로그램에는 데이터의 양을 효율적으로 처리할 알고리즘이 필요합니다.</p>
<p>효율적인 알고리즘을 평가할 때 복잡도라는 개념이 나온건데 복잡도가 낮을수록 좋은 알고리즘이라고 합니다.</p>
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">
시간복잡도는 특정 알고리즘이 어떤 문제를 해결하는데 걸리는 시간을 의미합니다

공간복잡도는 작성한 프로그램이 얼마나 많은 메모리를 차지 하느냐를 분석하는 방법입니다
</div>
</details>  
