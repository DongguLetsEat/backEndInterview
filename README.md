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

- 오버로딩과 오버라이딩 차이에 대해 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>오버로딩은</p>
    <p>같은 이름의 메서드를 재 정의할 수 있는데 
      비슷한 기능을 가진 메서드들의 이름을 지을 때, 각 메서드 별로 이름을 구별하지 않고 하나의 이름으로 통일성 있게 사용할 수 있다는 장점이 있습니다.</p>
    <p>오버로딩은 매개변수가 달라야 하거나 타입이 달라야 사용이 가능합니다.<p/>
    <br/>
    <p>오버라이딩은</p>
    <p>부모클래스로 부터 상속 받은 메서드를 재 정의 하는 것이라고 할 수 있는데
    부모로부터 상속받은 메서드를 그대로 사용하는 경우도 있지만 필요에 따라 재정의 해야할 때 사용하게 됩니다.</p>
    <p>오버라이딩은 매개변수가 같아야 하고 리턴타입이 같아야 사용이 가능합니다.</p>
    
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>Override는 상속과 관련된 개념으로 부모 클래스의 메소드를 재 정의합니다.</p>
<p>Overload는 이름이 비슷하지만 상속과는 관련 없는 내용입니다.</p>
<p>Overload는 같은 메소드라도 매개변수만 다르면 정의하고 사용할 수 있는 개념입니다.</p>
<p>Overload는 다른 기능을 하는 메소드를 하나의 이름으로 사용하기 위해 쓰는 개념입니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>오버로딩은 비슷한 기능의 메서드를 같은 이름으로 여러개 만들때 사용하며 매개변수의 타입이나 개수가 달라야합니다</p>
<p>오버라이딩은 부모에게 상속받은 메서드를 재정의해서 사용하며 구현부를 제외한 매개변수와 리턴타입 과같은것들이 모두 같아야 합니다</p>
</div>
</details>

- 오버로딩과 오버라이딩은 어떤 상황에서 사용하나요?
<details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>오버로딩은 주로 생성자가 여러개 필요한 경우 유용하게 사용됩니다.</p>
    
    <p>오버라이딩은 결합도를 낮추기 위해 interface가 사용되는데 이때 오버라이딩이 적극 사용됩니다.</p>
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>오버로딩 (Overloading) == 확장</p>
<p>같은 이름의 메서드 여러 개를 가지면서
매개변수의 타입과 개수를 다르게 해서 사용하는 것</p>
<p>1) 같은 기능을 하는 메서드를 하나의 이름으로 사용할 수 있다
ex) 우리가 흔히 쓰는 println 라는 메서드를 대표적인 예로 볼 수 있다
println에 인자 값으로 다양한 타입을 넣어도 잘 출력 해주는게
오버로딩으로 선언해 놓았기 때문이다

2) 메서드의 이름을 절약할 수 있다
ex) println을 예로 보면 타입에 따라 이름을 다 다르게 한다고하면
pringlnInt, printlnDouble 이런식으로 써야할텐데 그러지 않아도 된다</p>

<p>오버라이딩 (Overriding) == 재정의</p>
<p>상위 클래스가 가지고 있는 메서드를
하위 클래스가 재정의해서 사용하는 것</p>
<p>1) 메서드를 하나로 통일할 수 있다
ex) 예를들어 강아지, 고양이 가 있는데 두 동물 다 우는 메서드를 만들때
메서드를 각각 해서 2개를 만드는 상황에서 동물이라는 상위 클래스를 만들어
상속을 시키고 동물의 우는 메서드를 하나 만들어 이를 각각 객체에서
오버라이딩해 재정의해서 사용하면 편리하게 이용이 가능하고
동물이 100개 1000개 수가 늘어 날 수록 필요성이 더욱 느껴집니다</p>
</div>
</details>

- 객체지향(oop)란 무엇인지 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    객체지향이란, 데이터를 추상화시켜 객체를 만들고 객체들 간의 상호작용을 통해 로직을 구성하는 프로그래밍 방법입니다.
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>프로그래밍에서 필요한 데이터를 추상화 시켜 (클래스로)
상태(변수) 와 행위(메서드)를 가진 객체(인스턴스 화)를 만들고
그 객체들 간의 유기적인 상호작용을 통해 로직을 구성하는 프로그래밍 방법이다</p>
</div>
</details>


- 객체지향(oop)의 특징에 대해 설명해주세요.(+예시)
<details>
  <summary>계현준</summary>
  <div markdown="1">
    - 캡슐화
    <p>캡슐화는 정보은닉이 필요한 경우, 즉 외부에서 해당 정보에 접근하지 못하게 제한한다는 개념입니다.</p>
    <p>주로 접근제한자를 사용하여 캡슐화를 합니다.</p>
    <p>캡슐화는 높은 응집도와 낮은 결합도로 유연함과 유지보수성이 증가된다는 장점이 있습니다.</p>
    <p>예시 : 나의 이름이라는 정보는 외부에서 접근하여 변경하게 되면 문제가 생길 수 있기 때문에 나의 특징 중 이름이라는 정보는 캡슐화를 합니다.</p>
    - 추상화
    <p>객체의 공통적인 특징을 파악해서 하나의 개념으로 추상화 시켜 다루는 개념입니다.</p>
    <p>장점으로는 공통적인 특징을 따로 정의 해두면 객체를 만들 때 매번 정의하지 않고 상속 받아서 사용하면 되기 때문에 코드의 낭비를 줄일 수 있고 가독성이 향상된다는 장점이 있습니다.</p>
    <p>예시 : '사람1' 이라는 객체와 '사람2' 라는 객체를 만들 때 사람의 공통적인 특징인 '호흡한다', '밥을 먹는다' 라는 공통적인 특징을 정의하는 것입니다.</p>
    - 상속
    <p>상속은 부모클래스의 특징을 받아와 자식클래스에서 사용한다는 개념니다.</p>
    <p>상속은 코드의 낭비를 줄일 수 있고 가독성이 향상된다는 장점이 있습니다.</p>
    <p>예시 : 부모님의 음악적 재능을 자식이 물려받아 사용하는 것을 예시로 들 수 있습니다.</p>
    - 다형성
    <p>다형성이란 형태는 같지만 다향한 기능으로 동작하는 것을 의미합니다.</p>
    <p>다형성은 오버라이딩과 오버로딩이라는 개념을 예시로 들 수 있습니다.</p>
    <p>예시1 : 오버로딩 - 매개변수의 개수가 다르거나 다른 타입의 변수을 받았을 때 같은 이름의 메서드라도 다르게 동작합니다. </p>
    <p>예시2 : 오버라이딩 - 자식클래스에서 부모클래스에 있는 메서드를 받아 재정의 하여 사용합니다.</p>
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>캡슐화</p>
<p>데이터와 코드의 형태를 외부로부터 알 수 없게 하고
데이터의 구조와 역할, 기능을 하나의 캡슐 형태로 만드는 것이다</p>
<p>상속화</p>
<p>부모 클래스에 정의된 변수 및 메서드를
자식 클래스에서 상속받아 사용하는 것이다</p>
<p>추상화</p>
<p>공통의 속성이나 기능을 묶어 이름을 붙이는 것이다
객체지향 관점에서 클래스를 정의하는 것이다</p>
<p>다형성</p>
<p>다양한 형태로 표현이 가능한 구조를 말한다
오버로딩, 오버라이딩을 예로 들 수 있다</p>
</div>
</details>


- 객체지향(oop)의 solid 라는 개념에 대해 설명해주세요.(+예시)
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>1) 단일 책임 원칙</p>
<p>한 클래스는 하나의 책임만 가져야한다</p>
<p>ex) 사람 클래스는 사람의 역할만 충실히 한다</p>
<p>2) 개방 폐쇄 원칙</p>
<p>확장에는 열려있고 변경에는 닫혀 있어야 한다/<p>
<p>ex) 기능을 더 추가는 할 수 있어도 바꾸는건 함부로 못한다</p>
<p>3) 리스코프 치환 원칙</p>
<p>상위 타입의 객체를 하위 타입의 객체로 치환해도</p>
<p>상위 타입을 사용하는 프로그램은 정상적으로 작동해야 한다</p>
<p>ex) 어떤 메서드에 Item 이라는 상위 타입으로 받고 있는데</p>
<p>apple 이라는 하위 타입으로 바뀌어 넘어와도 동작해야한다</p>
<p>4) 인터페이스 분리 원칙</p>
<p>인터페이스는 그 인터페이스를 사용하는</p>
<p>클라이언트를 기준으로 분리해야한다</p>
<p>ex) 3명의 클라이언트가 하나의 인터페이스를 상속받기보다</p>
<p>각 클라이언트 별로 인터페이스를 분리해야한다</p>
<p>5) 의존 역전 원칙</p>
<p>추상화에 의존해야 하고 구체화에 의존하면 안된다</p>
<p>ex) 자동차가 스노우 타이어(구체화)에 의존하는게 아니라</p>
<p>타이어(추상화)에 의존해야하는 것이다</p>
</div>
</details>



- 추상 클래스와 인터페이스 차이는?
<details>
  <summary>계현준</summary>
  <div markdown="1">
   <p>추상클래스(abstract class)</p>
    <p>1. 단일 상속을 지원합니다.</p>
    <p>2. 변수를 가질 수 있습니다.</p>
    <p>3. 하나 이상의 abstract 메소드가 존재해야 합니다.</p>
    <p>4. 자식 클래스에서 상속을 통해 abstract 메소드를 구현합니다. (extends)</p>
    <p>목적 : 관련성이 높은 클래스 간의 코드를 공유하고 확장하고 싶은 목적</p>
    <br/>
    <p>인터페이스(interface)</p>
    <p>1. 다중 상속을 지원합니다.</p>
    <p>2. 변수를 가질 수 없습니다. 상수는 가능합니다.</p>
    <p>3. 모든 메소드는 선언부만 존재합니다.</p>
    <p>4. 구현 클래스는 선언된 모든 메소드를 overriding 합니다.</p>
    <p>목적 : 관련성이 없는 클래스들의 논리적으로 같은 기능을 자신에 맞게 구현을 강제하는데 목적</p>
    <p>정리</p>
    <p>구조상 차이로 추상 클래스는 abstract 키워드가 붙고 추상 메서드뿐만 아니라 다른 변수, 메서드도 선언이 가능하고, 인터페이스는 추상 메서드와 상수만 선언 가능하다.
      (자바 8부터는 default 메서드 선언 가능)
      목적의 차이로 추상 클래스는 관련성이 높은 클래스 간의 코드 공유(재사용)와 확장을 목적으로 하고, 
      인터페이스는 관련성이 없는 클래스들의 같은 기능을 자신에 맞게 구현하는데 목적이 있다.
    </p>
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>추상 클래스는 단일 상속을 지원하고 일반 클래스와 별 다를것이 없지만 추상 메서드를 선언하여 상속을 통해 자식 클래스에서 완성하도록 유도합니다</p>
<p>그래서 이를 미완성 설계도라고 표현합니다</p>
<p>인터페이스는 다중 상속을 지원하고 추상클래스처럼 다른 클래스를 작성하는데 도움을 주는 목적을 가지고</p>
<p>이를 기본 설계도라고 표현합니다</p>
<p>차이로는 추상클래스는 is-a ~이다 관계이고 인터페이스는 has-a ~을 가진 의 관계를 가집니다</p>
<p>추상클래스 예로는 강아지는 동물이다 와 같이 단일 상속일때 사용하며</p>
<p>인터페이스 예로는 사각형은 점을 가지고있고 선을 가지고있다 와 같이 다중 상속일때 사용됩니다</p>
</div>
</details>


- 접근제어자에 대해서 아는대로 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>접근제한자는 말 그대로 접근을 제한하기 위해서 사용됩니다. 여기서 접근이란 클래스 및 인터페이스 그리고 이들이 가지고 있는 맴버의 접근을 말합니다.</p>
    <p>java에서 접근자의 종류는 public, protected, private, defualt 4가지 종류가 있습니다.</p>
    <p>Public 접근제한자 : 단어 뜻 그대로 외부 클래스가 자유롭게 사용할 수 있도록 합니다.</p>
    <p>Protected 접근제한자 : 같은 패키지 또는 자식 클래스에서 사용할 수 있도록 합니다.</p>
    <p>defualt 접근제한자: 같은 패키지에 소속된 클래스에서만 사용할 수 있도록 합니다.</p>
    <p>Private 접근제한자 : 단어 뜻 그대로 개인적인 것이라 외부에서 사용될 수 없도록 합니다.</p>
    <p>접근제한자를 명시해 주지 않으면 기본적으로 default 접근제한자가 사용됩니다.</p>
    <p>즉. public > protected > default > private 순으로 제한의 정도가 낮습니다.</p>

  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>접근 제어자는 클래스, 멤버변수, 메서드, 생성자 등에 대한 접근을 제한하는 역할을 합니다.</p>
<p>접근 제어자는 public, protected, default, private가 있습니다.</p>
<p>private는 해당 클래스에서만 접근이 가능하고, default는 해당 패키지까지, protected는 상속한 클래스까지 접근이 가능합니다.</p>
<p>public는 전체 영역에서 접근이 가능합니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>자바에서 정보 은닉을 위해 접근제어자 라는것을 제공하는데</p>
<p>클래스, 변수, 메서드, 생성자 등에 대한 외부접근을 제한하여 정보은닉을 구체화 할 수 있습니다</p>
<p>접근제어자에는 public, protected, default, private가 있습니다</p>
<p>public은 전체 영역에서 접근이 가능하고</p>
<p>protected는 같은 클래스와 상속한 자식 클래스까지 접근이 가능하고</p>
<p>default는 같은 패키지 까지만 가능하고</p>
<p>private는 같은 클래스에서만 접근이 가능합니다</p>
</div>
</details>

- 제네릭에 대해서 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>클래스나 메서드에서 사용할 내부 데이터 타입을 외부에서 지정하는 기법입니다.</p>
    그리고 제네릭은 잘못된 타입이 들어올 수 있는 것을 컴파일 단계에서 방지할 수 있고
    불필요한 타입 변환을 제거할 수 있다는 장점이 있습니다.
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>어떤 값이 하나의 참조 자료형이 아닌 여러 참조 자료형을 사용할 수 있도록 프로그래밍하는 것을 제네릭 프로그래밍이라고 합니다.</p>
<p>클래스 내부에서 지정하는 것이 아닌 외부에서 사용자에 의해 지정되는 것을 의미합니다.</p>
<p>특정 타입을 미리 지정해주는 것이 아닌 필요에 의해 지정할 수 있도록 하는 일반 타입입니다.</p>
<p>저희가 대표적으로 썼던 것이 컨트롤러 클래스에 "<T>" 를 쓰면 타입을 필요에 의해 지정하는 것을 말합니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

- String, StringBuilder, StringBuffer 에 대해서 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    - String
      - 새로운 값을 할당할 때마다 새로운 클래스에 대한 객체가 생성
      - String에 저장되는 문자열은 private final char[] 형태이므로 변경할 수 없다.
      - String + String + String..
      - 가비지 컬렉터가 호출되기 전까지 생성된 String 객체들은 Heap에 머물기 때문에 메모리 관리에서 치명적이다.
    - StringBuilder
      - 메모리에 append하는 방식으로 클래스에 대한 객체를 생성하지 않는다.
      - 비동기 처리
    - StringBuffer
      - 메모리에 append하는 방식으로 클래스에 대한 객체를 생성하지 않는다.
      - 동기 처리
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

- Error, Exception 차이에 대해서 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>오류(Error)는 시스템이 종료되어야 할 수준의 상황과 같이 수습할 수 없는 심각한 문제를 의미합니다. 개발자가 미리 예측하여 방지할 수 없습니다.</p>
    <p>예외(Exception)는 개발자가 구현한 로직에서 발생한 실수나 사용자의 영향에 의해 발생합니다. 오류와 달리 개발자가 미리 예측하여 방지할 수 있기에 상황에 맞는 예외처리(Exception Handle)를 해야합니다.</p>
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

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


- MSA 아키텍쳐에 대해서 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>








## 네트워크
- 브라우저에 google.com 을 치면 일어나는 일련의 일들을 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
  
<p>처음에 www.google.com을 브라우저 주소창에 입력하면,</p>
<ui>
<li>우리가 쓰는 브라우저가 URL을 Parsing(주소 해석)해서 HTTP Request Message를 만들고 os에 전송 요청을 합니다. </li>
<p>이 때, 우리의 컴퓨터는 도메인 이름을 이해하지 못하기 떄문에 Domain으로 요청이 아닌 DNS를 통해 ip 주소를 찾습니다.</p>
<li>브라우저는 캐싱된 DNS 기록을 체크합니다.</li>
<p>요청한 URL이 캐시에 없으면, ISP(nternet Service Provider)의 DNS 서버에서 다른 DNS 서버를 DNS Query를 통해 검색하여 IP 주소를 찾습니다.</p>
<li>ip 주소를 찾으면 브라우저가 서버와 TCP connection을 한다.</li>
<p>TCP/IP three-way handshake라는 프로세스를 통해서 클라이언트와 서버간 connection이 이뤄지게 되는 것입니다.</p>
<li>이제 Browser가 웹서버에 HTTP 요청을 합니다.</li>
<li>서버는 가지고 있는 웹서버에서 브라우저로부터 온 요청을 읽고 response를 생성합니다.</li>
<li>서버는 요청받은 웹페이지, 상태코드, 쿠키 등이 포함되어 있는 HTTP Response를 보냅니다.</li>
<li>브라우저가 HTML content를 보여주면 www.google.com 웹페이지를 보여주는 것입니다.</li>  

</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">
<p>1) 브라우저 검색창에 www.google.com  을 입력 후 엔터를 친다</p>
<p>2) 브라우저는 캐싱된 DNS 기록을 체크한다</p>
<p>3) 없으면 ISP에서 제공하는 DNS 서버에서 다른 DNS 서버들로 해당 DNS 정보를 찾으려 DNS query를 보낸다</p>
<p>4) 찾으면 브라우저와 서버가 TCP 연결을 한다</p>
<p>5) 연결 되었으면 브라우저가 서버에 HTTP 요청을 한다</p>
<p>6) 서버가 요청을 처리하고 response를 생성한다</p>
<p>7) 서버가 HTTP response를 보낸다</p>
<p>8) 브라우저가 HTML content를 보여준다</p>
</div>
</details>

## 기타
- 에자일 방식에 대해서 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
  

</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>







## 프로젝트
- 프로젝트에 대해 설명해 주세요
<details>
  <summary>계현준</summary>
  <div markdown="1">
    !!작성!!
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
<p>프로젝트 마운틴즈는 인증을 통해 등산을 추천해 주는 서비스입니다.</p>
<p>서비스 배포는 spring boot를 기반으로 CI/CD 환경으로 구성했습니다.</p>
<p>유저에게 각 산에 대한 정보를 제공해주고 카카오맵을 통해 산의 위치도 제공해줍니다.</p>
<p>유저가 해당 산의 위치에서 사진을 인증하면 인증포인트를 주어 뱃지를 주는 서비스도 제공하고 있습니다.</p>
<p>인증포인트를 통한 뱃지와 유저간의 랭킹 시스템같은 게임적인 요소를 제공하여 등산을 보다 즐겁게 이용할 수 있게 도와주는 서비스입니다.</p>
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>
  
- 프로젝트에서 본인이 맡은 역할은 무엇인지 설명해 주세요.
<details>
  <summary>계현준 !!!수정!!!</summary>
  <div markdown="1">
  (키워드만 얘기하고 자세한 내용은 꼬리물어 질문할 때 대답하기!!!)
     가장 최근 진행한 의류이커머스 프로젝트에서 제가 맡은 대표적인 역할은 '조회 성능 개선', '상품 주문시 동시성 문제 해결', 'Jmeter를 활용한 부하 및 성능테스트'였습니다. 
1000만건 이상의 대용량 데이터가 있는 이커머스의 특성 때문에 데이터를 조회하는데 1분 이상이 걸린다는 문제점이 있었습니다. 그래서 기존에 쿼리문을 projection을 이용해 DTO로 필요한 컬럼만 가져오도록 개선하고, cross join으로 나가던 쿼리문은 inner join의 사용으로 조건에 맞는 컬럼만 가져오게 하고, 앞에 쿼리문을 실행할 때 먼저 pk값으로만 필요한 값을 필터링하여 조회 후 이에 맞는 값을 불러오게 하는 방식으로 커버링인덱스를 사용하였습니다. 그러나 조회 성능 개선은 됬지만 저희가 목표로 하는 2조 이내 조회는 달성하지 못 하였습니다. 그래서 추가로 조회가 자주 일어나는 테이블의 반정규화를 진행하였고 pk와 '조회수' 컬럼을 복합인덱스로 사용하여 따로 order by 를 하지 않아도 조회순 또는 등록순 으로 정렬되게 하였고, 키워드 조회 시 성능 향상을 위해 기존 like문으로 조회하던 것을 full-text-search 라는 전문 조회 기능을 적용하였습니다. 그리고 마지막으로 빠른 메인페이지 로딩을 위하여 상위 100개의 상품을 레디스를 활용하여 캐싱처리를 하였습니다. 그래서 결과적으로 평균 500ms 라는 조회성능향상 결과를 얻어 낼수 있었고 약 12,000%의 성능향상을 이끌어 낼 수 있었습니다. 
 다음으로 3000건 정도의 상품주문 시 상품주문은 정상적으로 진행되지만 제고는 약 500건 정도밖에 줄지 않는 정합성이 깨지는 문제가 발생하였는데 이때 Pessimistic Lock을 도입하여 정합성이 깨지는 문제를 해결했던 경험이 있습니다.
 마지막으로 jmeter로 한번에 많은 조회와 주문 요청을 넣는 테스트를 하던 중 CPU에 병목 현상이 생긴다는 것을 발견했고 여러개의 레플리카 DB를 만들어 mainDB에는 주문 요청만 동작하게 진행하여 동일 상황에서 CPU의 안정화를 이끌어 낸 경험이 있습니다. 또한 '캐시 라이트 백' 전략으로 조회수 를 관리하고 있었는데 Jmeter로 10초간 1500건 주문 요청 시 에러가 나는 것을 확인했고 DB업데이트를 통해 해결할 수 있었지만 프리티어로 진행하는 특성상 에러를 최대한 줄이기 위해 최적의 커넥션 풀 사이즈를 찾아 내서 35%의 에러율을 5%까지 줄인 경험이 있습니다. 

  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>
  
- QueryDSL을 사용하셨는데 어떤 상황에서 쓰셨나요?
<details>
  <summary>계현준</summary>
  <div markdown="1">
  
  </div>
</details>
<details>
<summary>이동재 //다듬어서 수정</summary>
<div markdown="1">
<p>QueryDSL은 필터를 이용해 산을 검색하는 기능에 적용했습니다.</p>
<p>QueryDSL을 사용하면 동적으로 데이터 처리 문자열이 아닌 자바에 내장되어 있는 코드로 쿼리를 생성하여 더 쉽고 간결합니다.</p>
<p>형태도 SQL문과 비슷하여 가독성이 좋습니다.</p>
<p>기존에 JPA만을 가지고 구현을 하려했으나 필터 기능이 복잡한 조건을 동적 처리하는 기능이다 보니 JPA로는 코드가 너무 길고 복잡해지는 문자가 생겼습니다.</p>
<p>문자열을 통해서 쿼리를 만들게 되면 작성한 문자열 쿼리 중 띄어쓰기 혹은 알파벳의 오류가 있을 경우 이를 컴파일 타임에서 잡아주지 못합니다.</p>
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>



- 프로젝트 서비스 아키텍쳐 구성에 대해 설명해 주세요.
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>
  
- CORS 오류를 어떻게 해결했나요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

- 프로젝트에서 기술 외적인 문제가 있었나요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

- 프로젝트 기술적 문제(트러블슈팅)가 있었나요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>


- 프로젝트에서 성능을 개선한 경험이 있나요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>
  
- MYSQL(RDB)을 왜 사용하셨나요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>저희가 사용한 MYSQL은 RDB입니다.</p>
<p>저희 프로젝트 같은 경우 다양한 산들과 유저들의 인증 데이터가 중복이 배제되어야 하고 엔티티 간에 관계를 정의해야합니다.</p>
<p>또한 복잡한 조건을 주어 검색을 하는 기능들이 있기에 SQL을 사용해 데이터를 가져와 줄 RDB인 MYSQL을 사용했습니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

  
- RDB중에서도 MYSQL을 사용한 이유가 있나요? 혹시 다른 선택지는 있나요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>MYSQL은 일단 다른 RDB에 비해 빠르고 안정적이며 사용하기 쉬웠습니다..</p>
<p>또한, 고사양을 요구하지 않으며 무료입니다.</p>
<p>웹환경에 맞게 설계되어 있기 때문에 웹 서비스를 구현하는 저희 프로젝트에서는 MYSQL을 선택했습니다.</p>
<br>
<p>다른 RDB로는  Maria DB, MS-SQL 등이 있습니다.</p>
<p>일단 처음 RDB구현에 MYSQL을 사용한 이유는</p>
<p>가장 대중적인 DB이다 보니 많은 유저 경험과 레퍼런스가 있어 처음 구현과 오류 해결에 더 유리하다 판단되어 사용하게 되었습니다.</p>
<p>추후 RDB구현에 좀 더 미래 지향적인 RDB를 사용한다면 Maria DB도 사용해 보려고합니다.</p>
<p>Maria DB도 MySQL을 포크한 서비스라서 어떻게 보면 많은 유저 경험과 레퍼런스가 있습니다.</p>
<p>또한 오픈소스이기 떄문에 기업에 인수된 MySQL보다 정책적인 면에서 더 안정적이고 업데이트가 활발할거 같습니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

- REST full API에 대한 개념과 프로젝트에 어떻게 적용하셨는지 설명해주세요.
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">

- 
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">


</div>
</details>  
  
 ## 인성
- 개발자가 되기로 한 이유에 대해서 말씀해주실 수 있니요?
<details>
  <summary>계현준</summary>
  <div markdown="1">
    !!작성!!
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
  
<P>IT업계에서 일했던 저는 다양한 포지션이 함께 작업하는 프로젝트에서 개발자들을 만났습니다.</P>
<P>'IT의 꽃은 개발자'라는 말을 자주 들었던 저는 개발자들을 만나고서야 그 말을 이해했습니다.</P>
<P>제가 일했던 IT 환경은 정해진 답만 존재했고 그 답만을 위해 수동적이게 움직여야했던 환경이었습니다.</P>
<P>하지만 개발자들은 그들이 짜는 코드에 정답은 없고 누구든지 창의적인 방법을 다양하게 구현할 수 있었습니다.</P>
<P>누구든지 목표를 가지고 공부한다면 자신만의 정답으로 코드를 구현할 수 있다는 그 환경에 매력을 느꼈습니다.</P>
<P>코로나때 진행되고 지금 잠시 멈춘 더 큰 디지털화에는 그런 창의적인 개발자들이 많이 필요할것이라 생각하고 있습니다.</P>
<P>저는 다가올 더 큰 디지털화를 구축할 개발자가 되고 싶어서 도전하게 되었습니다.</P>
    
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

- 최근에 했던 개발공부가 있나요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
      
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

- 개발의 어떤점에 흥미를 가지고 있나요?
<details>
<summary>계현준</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">
      
</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>


  
 ## 데이터 베이스
- RDBMS, NoSQL 차이에 대해 설명해 주세요
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

RDB

<p>관계형 데이터베이스 RDB는 주로 SQL을 이용해 데이터를 조회하고 관리합니다.</p>
<p>행과 열로 나타내는 2차원 데이터로 표현하여 테이블 사이의 상호관련성을 가진 집합으로 구성됩니다.</p>
<p>테이블 사이의 관계는 외래키를 이용해 나타냅니다.</p>
<p>RDB는 초기에 테이블 사이의 의존성, 데이터 타입 등이 설계되므로 실제 작업 환경에서 변경이 어렵습니다.</p>
<p>RDB는 복잡한 쿼리와 JOIN 연산이 가능하다.</p>
<p>RDB는 다양한 집계 및 통계를 분석하는 데이터의 무결성과 일관성이 중요한 트랜잭션 업무에 적합합니다.</p>


NOSQL

<p>관계형이 아닌 데이터 모델을 총칭합니다.</p>
<p>NOSQL은 초기에 테이블 사이에 명시된 제약이나 규칙이 없으며 다양한 방식으로 데이터를 표현합니다.</p>
<p>즉, 행과 열로만 나타내는 RDB와 달리 도큐먼트 형태, 그래프 형태, 키-값 형태 등 유연하게 표현할 수 있습니다.</p>
<p>NoSQL은 구조화된 쿼리 언어가 없는 경우도 많고, 일반적으로 Join이 없다.</p>
<p>NOSQL은 자주 변경되는 데이터를 저장하거나 다양한 유형의 데이터를 처리하는데 적합합니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
RDBMS

- 관계형 데이터베이스입니다

- 예로 MySQL, Oracle, MSSQL, PostgreSQL이 있습니다

- 효율적, 안정적, 안전한 데이터 저장소입니다

- 대용량 데이터를 영구적으로 저장, 관리, 접근할 수 있습니다

- 테이블마다 스키마를 정의해야합니다

- SQL을 통해 요청을 처리합니다

- 성능을 높이려면 하드웨어를 높은 성능으로 교체해야 합니다

- 높은 성능의 하드웨어는 가격이 비싸 RDBMS의 성능을 높이거나 확장하는게 어렵습니다

NoSQL
- RDBMS의 확장성 문제를 해결하기 위해 나왔습니다

- 예로 MongoDB, Redis, hBase가 있습니다

- 비교적 저렴한 가격으로 성능을 높일 수 있습니다

- RDBMS처럼 여러 테이블을 사용하는게 아닌 큰 테이블 하나만을 사용합니다

- SQL 질의문을 사용하지 않습니다

- 구조 변경이 용이하고, 데이터 형식이 다양하며 바꾸기가 쉽습니다

- 정확성 보다 데이터 양이 중요해 빅데이터에 사용합니다

- 자주 변경되는 데이터를 저장하거나 다양한 유형의 데이터를 처리하는데 적합하다
</div>
</details>

- Redis, Memcached 의 차이에 대해 설명해주세요
<details>
  <summary>계현준</summary>
  <div markdown="1">
    !!추가하여 수정!!
    <p>Redis는 싱글스레드를 사용합니다.</p>
    <p>Memcached는 멀티스레드를 사용합니다.</p>
    <p>Memcached는 데이터베이스로드를 줄이고 웹 애플리케이션의 속도를 높이는데 유용하고, Redis는 확장 가능한 웹 애플리케이션을 구축하고 고급 데이터 구조가 필요할 때 사용할 수 있습니다.</p>
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>Memcached와 Redis 둘다 key-value 를 기반으로 둔 NoSQL 입니다</p>
<p>하지만 Memcached의 대부분의 기능을 Redis로도 커버가 가능하고
Redis는 list, hash, set 등 다양한 자료구조를 제공하여 데이터 조작에 편리성이 있습니다 이러한 이유로 Redis를 사용하였습니다</p>
</div>
</details>  
  
 
 - DB를 사용하는 이유를 간단하게 설명해주세요
 <details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>파일 시스템의 데이터 중복, 비일관성, 검색 등의 문제 를 해결하기 위해서 사용합니다.</p>
    <p>파일 시스템이 OS마다 다를 수 있기 때문에 OS에 종속적인 파일 시스템을 이용하는 것은 프로그램의 확장성을 해침<p>
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>파일 단위로 저장할 때 데이터 종속성 문제와 중복성, 데이터 무결성 문제 때문에</p>
<p>DB를 사용하여 무결성을 보장하고 프로그램으로 구현해야 했던 것들을
SQL 쿼리문으로 간단하게 수행이 가능해 지기 때문에 사용합니다</p>
</div>
</details>  
  
 
- 정규화에 대해 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
   중복을 최대한 줄여 데이터를 구조화하고, 불필요한 데이터를 제거해 데이터를 논리적으로 저장하는 것입니다.
   또한 데이터의 이상현상이 일어나지 않도록하기 위해  정규화 시킵니다!

  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>정규화는 일정한 규칙에 따라 테이블 간에 중복된 데이터를 허용하지 않는 것입니다.</p>
<p>DB를 정규화함으로써 데이터의 중복을 막을 수 있습니다.</p>
<p>데이터의 일관성과  DB의 저장 용량 또한 줄일 수 있는 효율성 및 확장성을 보장할 수 있습니다.</p>
<p>하지만 정규화를 하면 테이블 분해로 인해 많은 조인 연산이 발생하므로 응답 시간이 느려집니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>DB 테이블 간에 중복된 데이터를 허용하지 않아 무결성을 유지할 수 있게하는 처리를 말합니다</p>
<p>장점으로는 이상현상을 제거 할 수 있습니다</p>
<p>단점으로는 테이블 분해로 인해 조인 연산이 발생해 응답 시간이 느려질 수 있습니다</p>
</div>
</details>   
  
- 이상현상에 대해 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    릴레이션에서 일부 속성들의 종속으로 인해 데이터 중복이 발생하는 것입니다.
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>테이블내의 데이터들이 불필요하게 중복되어
테이블을 조작할 때 발생하는 데이터 불일치 현상입니다</p>
<p>이상현상에는 삽입이상, 삭제이상, 갱신이상이 있는데
삽입이상은 의도하지 않는 데이터가 같이 삽입되는 것이고</p>
<p>삭제이상은 의도와 다른 값들도 연쇄 삭제되는것을 뜻하고</p>
<p>갱신이상은 일부 튜플만 갱신되어 모순이 발생되는것을 뜻합니다</p>
</div>
</details>
  
- Redis의 작동원리 및 프로젝트에서 어떻게 사용했는지 설명해주세요.
 <details>
  <summary>계현준</summary>
  <div markdown="1">
    싱글 스레드를 사용하는 '인메모리 DB'로 key-value 형태로 데이터를 저장 하며 주로 캐시에 사용합니다.
    <p>저희 프로젝트에서는 1000만건의 상품데이터에서 상위 100개의 값을 찾아오면 로딩시간이 오래 걸리기 때문에 
    상위 100개의 상품데이터를 Redis를 사용하여 캐싱처리하여 메이페이지의 로딩시간을 단축 시키는 작업에 사용하였습니다.</p>
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>Redis는 DB에 있는 정보를 가져오는 것이 아니라 인메모리 방식의 캐시에 있는 정보를 가져오는 것입니다.</p>
<p>유저가 사용했던 정보들이 캐시에 들어있어 바로 가져와서 DB까지 가서 정보를 찾는 시간을 단축할 수 있습니다.</p>
<br>
<p>프로젝트 마운틴즈에서는 태그 조회할 때 Redis 캐싱처리를 적용했습니다.</p>
<p>저희가 미리 DB에 저장해 놓은 태그가 공통적이고 반복적으로 보여지게 될 정보입니다.</p>
<p>매번 DB에 접근하는 것을 redis라는 인메모리 방식의 캐시를 사용하면 사용자의 처리 속도를 더 높여줄 수 있을것 같아서 적용했습니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>먼저 저희 프로젝트에서는 클라이언트 들에게 산을 추천해주는 태그라는 기능이 있는데</p>
<p>이 태그안의 산들은 모든 유저에게 중복되고 반복적으로 보여주어야하는 목록입니다</p>
<p>이때 같은 값을 계속해서 DB에서 불러와야하니 성능저하가 발생할것이라 판단해
캐싱을 이용해서 처리하고자 Redis를 사용하여 처리했습니다</p>
<p>동작 방식으로는
먼저 A라는 클라이언트가 태그를 누르면 먼저 Redis에 와서 캐싱된 내용이 있는지 확인 후 없다면 DB에 접근해서 쿼리를 이용해서 값을 가져오게되고 그 값을 Redis에 저장하고
클라이언트에 보여주게 됩니다</p>
<p>두번째로 B라는 클라이언트가 태그를 누르면 Redis에 와서 캐싱된 내용이 있으니
바로 클라이언트에게 보여지게 됩니다</p>
<p>이를 JMeter를 통해 확인한 결과 30%정도의 성능 개선을 경험했습니다</p>
</div>
</details>    
  
- 모든 요소에 인덱스를 걸지 않는 이유에 대해 설명해주세요.
 <details>
  <summary>계현준</summary>
  <div markdown="1">
    <p>인덱스는 기본적으로 추가 공간을 요구하기 때문에 모든 요소에 인덱스를 걸었을 때 용량에 의한 이슈가 발생할 수 있고</p>
    <p>인덱스가 적용된 컬럼에 삽입, 삭제, 수정이 잦다면 인덱스 또한 수정해야 하기 때문에 성능이 낮아질 수 있다는 단점이 있기 때문에</p>
    <p>모든 요소에 인덱스를 걸지 않는다고 생각합니다.</p>
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>모든 요소에 인덱스를 걸면 데이터를 찾을 때는 빠를 수 있습니다.</p>
<p>하지만 다양한 단점이 있습니다.</p>
<p>데이터가 변경될 때마다 이 데이터를 갱신해야 합니다.</p>
<p>인덱싱 데이터도 별도로 관리해야 하므로 물리적 저장소와 메모리 사용량이 급증하게 됩니다.</p>
<p>특히 CRUD의 요소 중 R찾기를 제외하고 나머지 요소들의 성능이 극단적으로 저하됩니다.</p>  
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>인덱스를 항상 정렬된 상태로 유지해야 하기 때문에 추가, 수정, 삭제 와 같은 작업 수행시 추가작업이 필요해 집니다</p>
<p>그래서 데이터 검색이 빨라지는 대신 데이터에 한 추가, 수정, 삭제에 대한 연산 속도는 오히려 느려지게 되고</p>
<p>인덱스 관리를 위한 별도의 저장공간을 추가로 필요해 오히려 독이 될 수 있어 모든 요소에 인덱스를 걸지 않습니다</p>
</div>
</details>      


- 외래키의 개념에 대해서 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>
<details>
<summary>이동재</summary>
<div markdown="1">

</div>
</details>
<details>
<summary>조평연</summary>
<div markdown="1">

</div>
</details>

  
  
  
  
 ## Spring & JPA 
 - DI란 무엇인지 설명해주시고 어떤 장단점이 있는지 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>DI란 의존성 클래스 간 의존성을 클래스 외부에서 주입하는 것을 말합니다.</p>
<p>DI는 단일적인 클래스들 간에 결합이 되어있으면 변경 사항에 서로 영향을 많이 받는데 이런 문제점을 방지하기 위해 사용하는 개념입니다.</p>
<p>DI를 사용함으로 클래스 레벨에서는 의존관계가 고정되지 않도록 하고 런타임 시에 관계를 동적으로 주입하도록 해줍니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>DI는 의존성 주입으로 스프링에서 외부(컨테이너) 에서 객체를 생성 후 주입 시켜주는 방식입니다</p>
</div>
</details>

 
- JPA란 무엇이고 언제 사용하는지 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>JPA는 JAVA에서 ORM(Object-Relational Mapping) 기술 표준으로 사용되는 인터페이스입니다.</p>
<p>실제적으로 구현된것이 아닌 구현된 클래스와 매핑을 해주기 위해 사용되는 프레임워크입니다.</p>
<p>JPA를 사용하지 않는다면 DB의 데이터 CRUD를 하나하나 쿼리를 작성해서 코딩해야 합니다.</p>
<p>JPA를 사용함으로 각각의 해당 CRUD에 맞는 쿼리를 다시 작성할 필요가 없어 필드가 추가되거나 수정할 때 유지 보수와 생산성을 높일 수 있습니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>JPA는 자바 진영의 ORM 기술 표준으로 DB와 객체지향 개발을 연결해주어 두 분야의 개발이 독립적으로 이루어질 수 있게 해줍니다</p>
<p>이로 인해 쿼리를 직접 작성하지 않아도 되어 유지 보수와 생산성을 높일 수 있습니다</p>
<p>따라서 sql중심적인 개발에서 객체중심적인 개발을 할때 사용합니다</p>
</div>
</details>
 
 - ORM에 대해서 설명해주세요.
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>JAVA에서 클래스를 만들어서 실행하면 DB에 테이블이 자동으로 생성되게 하는 기법입니다.</p>
<p>ORM 프레임워크는 객체와 테이블을 매핑해 패러다임의 불일치를 개발자 대신 해결해줍니다.</p>
<p>객체는 객체대로 생성하고, 데이터베이스는 데이터베이스에 맞도록 설계를 가능하게 해줍니다.</p>
<p>OPM으로 인해 개발자는 이를 매핑하는 방법만 전달해주면 됩니다.</p>
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>객체와 관계형 데이터베이스의 데이터를 자동으로 매핑(연결)해주는 것을 말합니다</p>
<p>이를 이용해 패러다임 불일치를 개발자 대신 해결해줍니다</p>
</div>
</details>

 
 - 어노테이션에 대해서 설명해주세요.(+사용예시)
<details>
  <summary>계현준</summary>
  <div markdown="1">
    
  </div>
</details>

<details>
<summary>이동재</summary>
<div markdown="1">
<p>Annotation은 클래스와 메서드에 추가하여 각각 다양한 기능을 부여하는 역할을 합니다.</p>
<p>스프링의 mvc패턴을 구현할 때 대표적인 Annotation인 @Repository @Controller @Service 가 있습니다.</p>
<p>스프링에서 각각 클래스에 Repository, Controller, Service 역할을 명시해줍니다.</p>  
</div>
</details>

<details>
<summary>조평연</summary>
<div markdown="1">
<p>사전적 의미로 주석을 뜻합니다 즉 프로그램에게 추가적인 정보를 제공해주는 메타데이터라고 볼 수 있습니다</p>
<p>예를들어 컴파일러에게 문법상 에러를 체크 해도록 정보를 제공하고 특정 역할을 수행하게 지정할 수 도 있습니다</p>
<p>오버라이딩 할때 @Override하고 적어주어 컴파일 에러시 알 수 있는 예시가 있습니다</p>
</div>
</details> 
