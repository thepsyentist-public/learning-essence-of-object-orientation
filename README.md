# The Essence of Object-Orientation 객체지향의 사실과 오해

저자: 조영호
상태: Reading
유형: Book

# 1장. 협력하는 객체들의 공동체

객체지향은 클래스를 지향하는 것이 아닌, 객체를 지향하는 것이다.

클래스의 구조와 매서드가 아니라, 객체의 역할, 책임, 협력에 집중하라.

- 객체지향이란 시스템을 상호작용하는 자율적인 객체들의 공통체로 바라보고 객체를 이용해 시스템을 분할하는 방법이다.
- 자율적인 객체란 상태와 행위를 함께 지니며 스스로 자기 자신을 책임지는 객체를 의미한다.
- 객체는 시스템의 행위를 구현하기 위해 다른 객체와 협력한다. 각 객체는 협력 내에서 정해진 역할을 수행하며 역할은 관련된 책임의 집합이다.
- 객체는 다른 객체와 협력하기 위해 메시지를 전송하고, 메시지를 수신한 객체는 메시지를 처리하는 데 적합한 메서드를 자율적으로 선택한다.

---

# 2장. 이상한 나라의 객체

객체의 다양한 특성을 효과적으로 설명하기 위해서는 객체를 상태(state), 행동(behavior), 식별자(identity)를 지닌 실체로 보는 것이 가장 효과적이다.

이 책에서는 객체를 다음과 같이 정의하기로 한다.

> 객체란 식별 가능한 개체 또는 사물이다. 객체는 자동차처럼 만질 수 있는 구체적인 사물일 수도 있고, 시간처럼 추상적인 개념일 수도 있다. 객체는 구별 가능한 식별자, 특징적인 행동, 변경 가능한 상태를 가진다. 소프트웨어 안에서 객체는 저장된 상태와 실행 가능한 코드를 통해 구현된다.
> 

이 책에서는 객체의 상태를 다음과 같이 정의하기로 한다.

> 상태는 특정 시점에 객체가 가지고 있는 정보의 집합으로 객체의 구조적 특징을 표현한다. 객체의 상태는 객체에 존재하는 정적인 프로퍼티와 동적인 프로퍼티 값으로 구성된다. 객체의 프로퍼티는 단순한 값과 다른 객체를 참조하는 링크로 구분할 수 있다.
> 

객체는 자율적인 존재다. 객체지향의 세계에서 객체는 다른 객체의 상태에 직접적으로 접근할 수도, 상태를 변경할 수도 없다.

객체의 행동은 객체의 상태를 변경시키지만 행동의 결과는 객체의 상태에 의존적이다. 음료를 마신 후의 앨리스의 키(상태)는 음료를 마시기 전의(행동) 앨리스의 키보다 작아져야 한다. 이것은 음료를 마시는 행동의 결과가 앨리스의 키(상태)에 의존한다는 것을 의미한다.

- 객체의 행동은 상태에 영향을 받는다
- 객체의 행동은 상태를 변경시킨다

이것은 상태라는 개념을 이용해 행동을 다음의 두 가지 관점에서 서술할 수 있다.

- 상호작용이 현재의 상태에 어떤 방식으로 의존하는가
- 상호작용이 어떻게 현재의 상태를 변경시키는가

### **캡슐화 Encapsulation**

객체는 상태를 캡슐 안에 감춰둔 채 외부로 노출하지 않는다. 객체가 외부에 노출하는 것은 행동뿐이며, 외부에서 객체에 접근할 수 있는 유일한 방법 역시 행동뿐이다. 상태를 외부에 노출시키지 않고 행동을 경계로 캡슐화하는 것은 결과적으로 객체의 자율성을 높인다. 자율적인 객체는 스스로 판단하고 스스로 결정하기 때문에 객체의 자율성이 높아질수록 객체의 지능도 높아진다. 협력에 참여하는 객체들의 지능이 높아질수록 협력은 유연하고 간결해진다. 결론적으로 상태를 잘 정의된 행동 집합 뒤로 캡슐화하는 것은 객체의 자율성을 높이고 협력을 단순하고 유연하게 만든다. 이것이 상태를 캡슐화해야 하는 이유다.

### **식별자 Identity**

> 식별자란 어떤 객체를 다른 객체와 구분하는 데 사용하는 객체의 프로퍼티다. 값은 식별자를 가지지 않기 때문에 상태를 이용한 동등성 검사를 통해 두 인스턴스를 비교해야 한다. 객체는 상태가 변경될 수 있기 때문에 식별자를 이용한 동일성 검사를 통해 두 인스턴스를 비교할 수 있다.
> 

객체의 상태를 조회하는 작업 - query

객체의 상태를 변경하는 작업 - command

### 행동이 상태를 결정한다

사람들이 객체지향에 쉽게 빠지는 함정은 상태를 중심으로 객체를 바라보는 것이다.

초보자들은 먼저 객체에 필요한 상태가 무엇인지를 결정하고 그 상태에 필요한 행동을 결정한다. 애플리케이션 안에 살아갈 앨리스 객체를 설계할 때 초보자들은 앨리스 객체에게 필요한 상태가 무엇인지를 찾고 키와 위치를 앨리스에 추가한다. 그러고 나서야 키와 위치를 변경하거나 조회할 수 있는 행동이 무엇인지를 고민한다.

상태를 먼저 결정하고 행동을 나중에 결정하는 방법은 설계에 나쁜 영향을 끼친다.

1. 상태를 먼저 결정할 경우 캡슐화가 저해된다. 상태에 초점을 맞출 경우 상태가 개체 내부로 깔끔하게 캡슐화되지 못하고 공용 인터페이스에 그대로 노출되버릴 확률이 높아진다.
2. 객체를 협력자가 아닌 고립된 섬으로 만든다. 객체가 필요한 이유는 애플리케이션 문맥 내에서 다른 객체와 협력하기 위해서다. 불행하게도 상태를 먼저 고려하는 방식은 협력이라는 문맥에서 멀리 벗어난 채 객체를 설계하게 함으로써 자연스럽게 협력에 적합하지 못한 객체를 창조하게 된다.
3. 객체의 재사용성이 저하된다. 객체의 재사용성은 다양한 협력에 참여할 수 있는 능력에서 나온다. 상태에 초점을 맞춘 객체는 다양한 협력에 참여하기 어렵기 때문에 재사용성이 저하될 수밖에 없다.

책임-주도 설계 (Responsibility-Driven Design, RDD)

협력 안에서 객체의 행동은 결국 객체가 협력에 참여하면서 완수해야 하는 책임을 의미한다.

---

# 3장. 타입과 추상화

3장 시작부터는 추상화를 강조한다.

**추상화**

어떤 양상, 세부 사항, 구조를 좀 더 명확하게 이해하기 위해 특정 절차나 물체를 의도적으로 생략하거나 감춤으로써 복잡도를 극복하는 방법이다.

복잡성을 다루기 위해 추상화는 두 차원에서 이뤄진다.

- 첫 번째 차원은 구체적인 사물들 간의 공통점은 취하고 차이점은 버리는 일반화를 통해 단순하게 만드는 것이다.
- 두 번째 차원은 중요한 부분을 강조하기 위해 불필요한 세부 사항을 제거함으로써 단순하게 만드는 것이다.

모든 경우에 추상화의 목적은 복잡성을 이해하기 쉬운 수준으로 단순화하는 것이라는 점을 기억하라.

객체란 특정한 개념을 적용할 수 있는 구체적인 사물을 의미한다. 개념이 객체에 적용됐을 때 객체를 개념의 인스턴스라고 한다.

앨리스가 수많은 군상들을 단지 트럼프일 뿐이라고 일축했던 것처럼 주변의 복잡한 객체들은 단지 몇 가지 개념의 인스턴스일 뿐이다.

일반적으로 객체의 분류 장치로서 개념을 이야기할 때는 아래의 세 가지 관점을 함께 언급한다.

- 심볼(symbol): 개념을 가리키는 간략한 이름이나 명칭
    - 트럼프
- 내연(intension): 개념의 완전한 정의를 나타내며 내연의 의미를 이용해 객체가 개념에 속하는지 여부를 확인할 수 있다.
    - 몸이 납작하고 두 손과 두 발은 네모 귀퉁이에 달려 있는 등장인물
- 외연(extension): 개념에 속하는 모든 객체의 집합(set)
    - 정원사, 병사, 신하,…,하트왕과 하트 여왕

## 분류 classification

분류란 특정한 객체를 특정한 개념의 객체 집합에 포함시키거나 포함시키지 않는 작업을 의미한다.

분류는 객체지향의 가장 중요한 개념 중 하나이다. 어떤 객체를 어떤 개념으로 분류할지가 객체지향의 품질을 결정한다. 

객체를 적절한 개념에 따라 분류하지 못한 애플리케이션은 유지보수가 어렵고 변화에 쉽게 대처하지 못한다. 더 중요한 것은 적절한 분류 체계는 애플리케이션을 다루는 개발자의 머릿속에 객체를 쉽게 찾고 조작할 수 있는 정신적인 지도를 제공한다는 것이다.

타입은 추상화다. 타입을 이용하면 객체의 동적인 특성을 추상화할 수 있다.

객체지향 프로그래밍 언어에서 정적인 모델 (static model)은 클래스를 이용해 구현된다. 따라서 ‘타입을 구현’하는 가장 보편적인 방법은 클래스를 이용하는 것이다. 클래스와 타입은 동일한 것이 아니다. 타입은 객체를 분류하기 위해 사용하는 개념이다. 반면 클래스는 단지 타입을 구현할 수 있는 여러 구현 메커니즘 중 하나일 뿐이다.

클래스는 타입의 구현 외에도 코드를 재사용하는 용도로도 사용되기 때문에 클래스와 타입을 동일시하는 것은 안된다. 클래스 ≠ 타입

---

# 4장. 역할, 책임, 협력

객체지향에 갓 입문한 사람들의 가장 흔한 실수는 협력이라는 문맥을 고려하지 않은 채 객체가 가져야 할 상태와 행동부터 고민하기 시작한다는 것이다.

훌륭한 객체지향 설계자 → 객체들 간의 요청, 응답 속에서 창발하는 협력에 초점을 맞춰 애플리케이션 설계 → 협력이 자리를 잡으면 저절로 객체의 행동이 드러나고, 뒤이어 적절한 객체의 상태가 결정된다.

책임은 객체의 외부에 제공해 줄 수 있는 정보와 외부에 제공해줄 수 있는 서비스의 목록이다. 따라서 책임은 객체의 공용 인터페이스(public interface)를 구성한다. 공용 인터페이스의 개념은 객체지향의 중요한 원리 중 하나인 캡슐화로 이어진다.

객체지향 설계는 협력에 참여하기 위해 어떤 객체가 어떤 책임을 수행해야 하고 어떤 객체로부터 메시지를 수신할 것인지를 결정하는 것으로부터 시작된다. 어떤 클래스가 필요하고 어떤 메서드를 포함해야 하는지를 결정하는 것은 책임과 메시지에 대한 대략적인 윤곽을 잡은 후에 시작해도 늦지 않다.

### 역할

역할의 개념을 사용하면 유사한 협력을 추상화해서 인지 과부화를 줄일 수 있다. 또한 다양한 객체들이 협력에 참여할 수 있기 때문에 협력이 좀 더 유연해지며 다양한 객체들이 동일한 협력에 참여할 수 있기 때문에 재사용성이 높아진다. 역할은 객체지향 설계의 단순성(simplicity), 유연성(flexibility), 재사용성(reusability)을 뒷받침하는 핵심 개념이다.

역할의 가장 큰 가치는 하나의 협력 안에 여러 종류의 객체가 참여할 수 있게 함으로써 협력을 추상화할 수 있다는 것이다.

### 대체 가능성

역할은 협력 안에서 구체적인 객체로 대체될 수 있는 추상적인 협력자다. 따라서 본질적으로 역할은 다른 객체에 의해 대체 가능함을 의미한다. 역할의 대체 가능성은 행위 호환성을 의미하고, 행위 호환성은 동일한 책임의 수행을 의미한다.

### 협력을 따라 흐르는 객체의 책임

어떤 책임은 왕에게, 어떤 책임은 하얀 토끼에게, 어떤 책임은 모자 장수에게 할당하면서 책임을 각 객체에게 할당해 나간다. 그리고 이렇게 할단된 책임은 왕과 하얀 토끼, 모자 장수라는 객체들이 외부에 제공하게 될 행동을 정의하게 된다. 이제 행동이 결정됐으니 각 객체가 필요로 하는 데이터를 정의할 수 있다. 그리고 이렇게 데이터와 행동이 결정된 후에야 왕과 하얀 토끼, 모자 장수를 구현하는 클래스를 개발할 수 있을 것이다.

협력이라는 실행 문맥 안에서 책임을 분배해야 한다. 각 객체가 가져야 하는 상태와 행위에 대해 고민하기 전에 그 객체가 참여할 문맥인 협력을 정의하라.

## 객체지향 설계 기법

### 책임-주도 설계 (Responsibility-Driven Design)

객체의 책임을 중심으로 시스템을 구축하는 설계 방법.

시스템의 기능은 더 작은 규모의 책임으로 분할되고 각 책임은 책임을 수행할 적절한 객체에게 할당된다. 객체가 책임을 수행하는 도중에 스스로 처리할 수 없는 정보나 기능이 필요한 경우 적절한 객체를 찾아 필요한 작업을 요청한다. 요청된 작업을 수행하는 일은 이제 작업을 위임받은 객체의 책임으로 변환된다.

이처럼 책임-주도 설계에서는 시스템의 책임을 객체의 책임으로 변환하고, 각 객체가 책임을 수행하는 중에 필요한 정보나 서비스를 제공해줄 협력자를 찾아 해당 협력자에게 책임을 할당하는 순차적인 방식으로 객체들의 협력 공동체를 구축한다. 책임-주도 설계는 개별적인 객체의 상태가 아니라 객체의 책임과 상호작용에 집중한다. 

- 시스템이 사용자에게 제공해야 하는 기능인 시스템 책임을 파악한다.
- 시스템 책임을 더 작은 책임으로 분할한다.
- 분할된 책임을 수행할 수 있는 적절한 객체 또는 역할을 찾아 책임을 할당한다.
- 객체가 책임을 수행하는 중에 다른 객체의 도움이 필요한 경우 이를 책임질 적절한 객체 또는 역할을 찾는다.
- 해당 객체 또는 역할에게 책임을 할당함으로써 두 객체가 협력하게 한다.

역할, 책임, 협력은 유연하고 견고한 객체지향 시스템을 만드는 데 필요한 가장 중요한 재료다. 그 외의 장치는 단지 역할, 책임, 협력을 보완하고 애플리케이션의 복잡도를 줄이기 위해 필요한 보조 재료일 뿐이다. 역할, 책임, 협력에 집중하라.

### 디자인 패턴 (Design Pattern)

앨리스터 코오번에 따르면 효과적으로 일하는 사람들의 한 가지 특징은 아무것도 없는 상태에서 작업을 시작하지 않고 이전의 훌륭한 결과물을 모방하고 약간의 수정을 거쳐 원하는 결과물을 만들어 낸다는 것이다.

패턴은 특정한 상황에서 설계를 돕기 위해 모방하고 수정할 수 있는 과거의 설계 경험이다.

일반적으로 디자인 패턴은 반복적으로 발생하는 문제와 그 문제에 대한 해법의 쌍으로 정의된다. 패턴은 해결하려고 하는 문제가 무엇인지를 명확하게 서술하고, 패턴을 적용할 수 있는 상황과 적용할 수 없는 상황을 함께 설명한다. 패턴은 반복해서 일어나는 특정한 상황에서 어떤 설계가 왜(why) 더 효과적인지에 대한 이유를 설명한다.

디자인 패턴과 관련된 가장 유명한 패턴 책은 GOF의 “디자인 패턴”으로, 23개의 디자인 패턴들을 상세하게 정리해 놓았다.

### 테스트-주도 개발(Test-Driven Development)

애자일 방법론의 한 종류인 XP의 기본 프랙티스로 소개되면서 주목받기 시작한 설계 기법이다. 테스트-주도 개발의 기본 흐름은 실패하는 테스트를 작성하고, 테스트를 통과하는 가장 간단한 코드를 작성한 후 (이 시간 동안에는 중복이 있어도 무방하다). 리팩터링을 통해 중복을 제거하는 것이다. ‘작동하는 깔끔한 코드 (clean code that works)’를 얻을 수 있다.

테스트-주도 개발은 테스트를 작성하는 것이 아니라 책임을 수행할 객체 또는 클라이언트가 기대하는 객체의 역할이 메시지를 수신할 때 어떤 결과를 반환하고 그 과정에서 어떤 객체와 협력할 것인지에 대한 기대를 코드의 형태로 작성하는 것이다.

책임-주도 설계의 기본 개념과 다양한 원칙과 프랙티스, 패턴을 종합적으로 이해하고 좋은 설계에 대한 감각과 경험을 길러야만 적용할 수 있는 설계 기법이다. 역할, 책임, 협력에 집중하고 객체지향의 원칙을 적용하려는 깊이 있는 고민과 노력을 통해서만 테스트-주도 개발의 혜택을 누릴 수 있다.

---

# 5장. 책임과 메시지

> 의도는 “메시징”이다. 훌륭하고 성장 가능한 시스템을 만들기 위한 핵심은 모듈 내부의 속성과 행동이 어떤가보다는 모듈이 어떻게 커뮤니케이션하는가에 달려있다. -앨런 케이[Kay 1998]
> 

객체가 다른 객체에게 접근할 수 있는 유일한 방법은 요청을 전송하는 것뿐이다. 그리고 이 요청을 우리는 메시지라고 부른다.

## 메시지와 메서드

### 메시지

메시지 전송은 수신자. 메시지 이름, 인자(argument)의 조합이다. 

```dart
모자장수.증언하라(어제, 왕국)
```

> 여기서는 C++, 자바, C# 등의 언어에서 사용되는 메시지 전송 문법을 사용했지만 실제로 메시지 전송 문법은 언어에 따라 달라질 수 있다. 예를 들어, 스몰토크에서는 ‘모자장수 증언하라:어제 어디서:왕국’ 과 같은 문법을 이용하며, 루비의 경우 인자들이 모호하지 않다면 ‘모자장수.증언하라 어제, 왕국’ 과 같은 문법을 사용할 수 있다. 중요한 것은 메시지 전송 문법이 아니라 메시지 전송을 구성하는 요소다. 메시지 전송이 수신자, 메시지 이름, 인자의 조합으로 구성된다는 것을 기억하는 것이 중요하다.
> 

### 메서드 Method

메시지를 처리하기 위해 내부적으로 선택하는 방법을 메서드라고 한다.

객체지향 프로그래밍 언어에서 메서드는 클래스 안에 포함된 함수 또는 프로시저를 통해 구현된다.

메시지를 수신한 객체가 실행시간에 메서드를 선택할 수 있다는 사실은 다른 프로그래밍 언어와 객체지향 프로그래밍 언어를 구분짓는 핵심적인 특징 중 하나다.

### 다형성 polymorphism

다형성이란 서로 다른 유형의 객체가 동일한 메시지에 대해 서로 다르게 반응하는 것을 의미한다. - 서로 다른 타입에 속하는 객체들이 동일한 메시지를 수신할 경우 서로 다른 메서드를 이용해 메시지를 처리할 수 있는 메커니즘을 가리킨다.

다형성은 객체들의 대체 가능성을 이용해 설계를 유연하고 재사용 가능하게 만든다. 다형성을 사용하면 송신자가 수신자의 종류를 모르더라고 메시지를 전송할 수 있다. 즉, 다형성은 수신자의 종류를 캡슐화한다.

다형성을 사용하면 메시지를 이해할 수 있는 어떤 객체와도 협력할 수 있는 유연하고 확장 가능한 구조를 만들 수 있다. 

### 유연하고 확장 가능하고 재사용성이 높은 협력의 의미

> 객체-지향 시스템은 협력하는 객체들의 연결망(web)이다. 시스템은 객체를 생성하고 상호 간에 메시지를 송신할 수 있게 이들을 끼워 맞춤으로써 구축된다. 시스템의 행위는 객체들의 조합으로 창발되는 속성이다. 이것은 객체의 조합을 변경함으로써 시스템의 행위를 변경할 수 있게 한다. 객체의 조합을 관리하기 위해 작성하는 코드는 객체 연결망이 어떻게 행동할 것인지에 대한 선언적인 정의다. 객체가 어떻게 할것인지보다는 무엇을 할 것인지에 초점을 맞추기 때문에 시스템의 행위를 변경하기가 쉽다.
> 

## 메시지를 따라라

### 객체지향의 핵심. 메시지

클래스는 단지 동적인 객체들의 특성과 행위를 정적인 텍스트로 표현하기 위해 사용할 수 있는 추상화 도구일 뿐이다. 중요한건, 클래스가 아니라 객체다. 클래스를 정의하는 것이 먼저가 아니라 객체들의 속성과 행위를 식별하는 것이 먼저다. 클래스는 객체의 속성과 행위를 담는 틀일 뿐이다. 심지어는 클래스를 사용하지 않고도 객체의 속성과 행위를 표현할 수도 있다.

클래스를 중심에 두는 설계는 유연하지 못하고 확장하기 어렵다. 객체지향 패러다임으로의 전환은 시스템을 정적인 클래스들의 집합이 아니라 메시지를 주고 받는 동적인 객체들의 집합으로 바라보는 것에서 시작된다.

진정한 객체지향 패러다임으로의 도약은 개별적인 객체가 아니라 메시지를 주고 받는 객체들 사이의 커뮤니케이션에 초점을 맞출 때 일어난다.

객체가 메시지를 선택 X 메시지가 객체를 선택하게 해야한다. 메시지가 객체를 선택하게 만들려면 메시지를 중심으로 협력을 설계해야 한다.

책임-주도 설계의 핵심은 어떤 행위가 필요한지를 먼저 결정한 후에 이 행위를 수행할 객체를 결정하는 것이다. 이 과정을 흔히 what/who 사이클[Budd 2001] 이라고 한다. 이 사이클 용어가 의미하는 것은 객체 사이의 협력 관계를 설계하기 위해서는 먼저 ‘어떤 행위(what)’를 수행할 것인지를 결정한 후에 ‘누가(who)’ 그 행위를 수행할 것인지를 결정해야 한다는 것이다.

책임-주도 설계는 객체가 아니라 객체들이 주고받는 메시지에 초점을 맞추게 함으로써 객체지향의 장점을 극대화한다. 메시지를 결정하기 전까지는 객체에 관해 고민하지 말아야 한다. 일단 메시지가 결정된 후에야 이 메시지를 처리할 객체를 선택한다.

메시지를 결정하는 시점에서는 어떤 객체가 메시지를 수신할 것인지를 알 수 없기 때문에 당연히 메시지 송신자는 메시지를 수신할 객체의 내부 상태를 볼 수 없다. 따라서 메시지 중심의 설계는 메시지 수신자의 캡슐화를 증진시킨다. 또한 송신자가 수신자의 내부 상태를 미리 알 수 없기 때문에 송신자와 수신자가 느슨하게 결합된다.

## 객체 인터페이스

### 인터페이스

일반적으로, 인터페이스란 어떤 두 사물이 마주치는 경계 지점에서 서로 상호작용할 수 있게 이어주는 방법이나 장치를 의미한다.

일반적으로 인터페이스는 다음과 같은 세 가지 특징을 지닌다.

1. 인터페이스의 사용법을 익히기만 하면 내부 구조나 동작 방식을 몰라도 쉽게 대상을 조작하거나 의사를 전달할 수 있다.
2. 인터페이스 자체는 변경하지 않고 단순히 내부 구성이나 작동 방식만을 변경하는 것은 인터페이스 사용자에게 어떤 영향도 미치지 않는다
3. 대상이 변경되더라도 동일한 인터페이스를 제공하기만 하면 아무런 문제 없이 상호작용 할 수 있다.

인터페이스만 유지된다면 객체의 내부 구조나 작동 방식을 변경하거나 다른 객체로 대체한다고 하더라도 인터페이스 사용자에게 영향을 미치지 않는다.

### 메시지가 인터페이스를 결정한다

객체가 다른 객체와 상호작용할 수 있는 유일한 방법은 ‘메시지 전송’.

따라서 객체의 인터페이스 → 객체가 수신할 수 있는 메시지의 목록으로 구성되며 객체가 어떤 메시지를 수신할 수 있는지가 객체가 제공하는 인터페이스의 모양을 빚는다.

## 인터페이스와 구현의 분리

### 객체 관점에서 생각하는 방법

맷 와이스펠드(Matt Weisfeld)는 객체지향적인 사고 방식을 이해하기 위해서는 다음의 세 가지 원칙이 중요하다고 주장한다. 이것들은 모두 객체의 인터페이스에 관련된 것이다.

- 좀 더 추상적인 인터페이스
    - 왕이 모자 장수에게 ‘목격했던 장면을 떠올려라’, ‘떠오르는 기억을 시간 순서대로 재구성하라’, ‘말로 간결하게 표현하라’와 같은 지나치게 상세한 수준의 메시지를 보내는 것은 객체의 자율성을 저해한다.
    - 대신 ‘증언하라’ 라는 좀 더 추상적인 수준의 메시지를 수신할 수 있는 인터페이스를 제공하면 수신자의 자율성을 보장할 수 있다. 따라서 구체적인 인터페이스 (X) 추상적인 인터페이스 (O)
- 최소 인터페이스 minimal interface
    - 외부에서 사용할 필요가 없는 인터페이스는 최대한 노출 금지
    - 인터페이스를 최소로 유지하면 객체의 내부 동작에 대해 가능한 한 적은 정보만 외부에 노출할 수 있다. 따라서 객체의 내부를 수정하더라도 외부에 미치는 영향을 최소화할 수 있다.
- 인터페이스와 구현 간에 차이가 있다는 점을 인식

### 구현

객체지향의 세계에서 내부 구조와 작동 방식을 가리키는 고유의 용어는 구현 (implementation) 이다. 객체를 구성하지만 공용 인터페이스에 포함되지 않는 모든 것이 구현에 포함된다.

### 인터페이스와 구현의 분리 원칙

객체 설계의 핵심은 객체를 두 개의 분리된 요소로 분할해 설계하는 것이다. 그것은 바로 외부에 공개되는 인터페이스와 내부에 감춰지는 구현이다.

책임이 자율적일수록 적절하게 ‘추상화’되며, ‘응집도’가 높아지고, ‘결합도’가 낮아지며, ‘캡슐화’가 증진되고, ‘인터페이스와 구현이 명확하게 분리’되며, 설계의 ‘유연성’과 ‘재사용성’이 향상된다. 처음에는 이런 용어들이 낯설고 이해하기도 어렵겠지만 이런 특성들이 모여 객체지향을 다른 패러다임보다 우월하게 만든다는 사실을 이해하는 것이 매우 중요하다.

객체지향의 강력함을 누리기 위한 출발점은 책임을 자율적으로 만드는 것이다. 그리고 이것은 여러분이 선택하는 메시지에 따라 달라진다.

---

# 6장. 객체 지도

소프트웨어 분야에서 예외가 없는 유일한 규칙은 요구사항이 항상 변경된다는 것이다. 개발자의 삶이 고단하면서 흥미로운 이유는 요구사항이 예측 불가능하게 변경되기 때문이다. 훌륭한 설계자는 사용자가 만족할 수 있는 훌륭한 기능을 제공하는 동시에 내일 변경될지도 모르는 요구사항도 수용할 수 있는 코드를 창조해야 하기 때문이다.

미래에 대비하는 가장 좋은 방법은 변경을 예측하는 것이 아니라 변경을 수용할 수 있는 선택의 여지를 설계에 마련해 놓는 것이다. 훌륭한 설계자는 미래에 구체적으로 어떤 변경이 발생할 것인지를 예측하는 것 X 단지 언젠가는 변경이 발생할 것이며 아직까지는 그것이 무엇인지 모른다는 사실을 겸허하게 받아들인다.

좋은 설계는 나중에라도 변경할 수 있는 여지를 남겨 놓는 설계다. 설계를 하는 목적은 나중에 설계하는 것을 허용하는 것이며, 설계의 일차적인 목표는 변경에 소요되는 비용을 낮추는 것이다.

이것이 객체를 기반으로 책임과 역할을 식별하고, 메시지를 기반으로 객체들의 협력 관계를 구축하는 이유다. 

## 두 가지 재료: 기능과 구조

기능은 사용자가 자신의 목표를 달성하기 위해 사용할 수 있는 시스템의 서비스다.

구조는 시스템의 기능을 구현하기 위한 기반으로, 기능 변경을 수용할 수 있도록 안정적이어야 한다.

- 구조는 사용자나 이해 관계자들이 도메인(domain)에 관해 생각하는 개념과 개념들 간의 관계로 표현한다.
- 기능은 사용자의 목표를 만족시키기 위해 책임을 수행하는 시스템의 행위로 표현한다.

유스케이스 모델링 - 기능을 수집하고 표현하기 위한 기법

도메인 모델링 - 구조를 수집하고 표현하기 위한 기법

## 안정적인 재료: 구조

### 도메인 모델

모든 소프트웨어는 사용자의 필요성을 충족시키기 위해 존재. 사용자는 자신이 관심을 가지고 있는 특정한 분야의 문제를 해결하기 위해 사용. 이처럼 사용자가 프로그램을 사용하는 대상 분야를 **도메인**이라고 한다.

도메인 모델 → 사용자가 프로그램을 사용하는 대상 영역에 관한 지식을 선택적으로 단순화하고 의식적으로 구조화한 형태다.

도메인 모델은 이해관계자들이 바라보는 멘탈 모델 (Mental Model) 이다. 멘탈 모델이란 사람들이 자기 자신, 다른 사람, 환경, 자신이 상호작용하는 사물들에 대해 갖는 모형이다. 사람들은 세상에 존재하는 현상을 이해하고 현상에 반응하기 위해 자신의 마음 속에 멘탈 모델을 구축한다.

도널드 노먼(Donald Norman)은 제품을 설계할 때 제품에 관한 모든 것이 사용자들이 제품에 대해 가지고 있는 멘탈 모델과 정확하게 일치해야 한다고 주장한다.

최종 제품은 사용자의 관점을 반영해야 한다.

최종 코드는 사용자가 도메인을 바라보는 관점을 반영해야 한다. 이것은 곧 애플리케이션이 도메인 모델을 기반으로 설계돼야 한다는 것을 의미한다. 도메인 모델이란 사용자들이 도메인을 바라보는 관점이며, 설계자가 시스템의 구조를 바라보는 관점인 동시에 소프트웨어 안에 구현된 코드의 모습 그 자체이기 때문이다.

## 불안정한 재료: 기능

### 유스케이스 Use Case

사용자의 목표를 달성하기 위해 사용자와 시스템 간에 이뤄지는 상호작용의 흐름을 텍스트로 정리한 것.

### 유스케이스의 특성

1. 유스케이스는 사용자와 시스템 간의 상호작용을 보여주는 ‘텍스트’다.
2. 유스케이스는 하나의 시나리오가 아니라 여러 시나리오들의 집합이다.
3. 유스케이스는 당순한 피처(feature) 목록과 다르다.
    1. 피처는 시스템이 수행하야 하는 기능의 목록을 단순하게 나열한 것이다. 예제로, 피처는 ‘시스템은 정기예금 정보를 보여준다’와 ‘시스템은 당일이나 현재 일자의 이자를 계산한다’이다. 피처의 단점은 이 두 피처를 서로 연관이 없는 독립적인 기능으로 보이게끔 만든다는 점이다. 두 피처를 ‘중도 해지 이자액을 계산한다’라는 유스케이스로 묶고 사용자와의 상호작용 흐름 속에서 두 피처를 포함하는 이야기를 제공함으로써 시스템의 기능에 대해 의사소통할 수 있는 문맥을 얻을 수 있다.
    2. 유스케이스의 강점은 유스케이스가 단순히 기능을 나열하는 것이 아니라 이야기를 통해 연관된 기능들을 함께 묶을 수 있다는 점이다.
4. 유스케이스는 사용자 인터페이스와 관련된 세부 정보를 포함하지 말아야 한다.
    1. 유스케이스는 자주 변경되는 사용자 인터페이스 요소는 배제하고 사용자 관점에서 시스템의 행위에 초점을 맞춘다. 이처럼 사용자 인터페이스를 베재한 유스케이스 형식을 essential use case 본질적인 유스케이스라고 한다.
5. 유스케이스는 내부 설계와 관련된 정보를 포함하지 않는다.
    1. 유스케이스의 목적은 연관된 시스템의 기능을 이야기 형식으로 모으는 것이지, 내부 설계를 설명하는 것이 아니다.
    2. 유스케이스에서 객체 설계로의 전환은 공학적인 규칙과 원칙을 기반으로 한 변환 작업이 아니라 경험과 상식과 의사소통을 기반으로 한 창조 작업이다.

### 유스케이스는 설계 기법도, 객체지향 기법도 아니다

유스케이스가 단지 사용자가 바라보는 시스템의 외부 관점만을 표현한다는 점에 주목하라.

## 재료 합치기: 기능과 구조의 통합

### 도메인 모델, 유스케이스, 그리고 책임-주도 설계

1. 협력의 출발을 장식하는 첫 번째 메시지는 시스템의 기능을 시스템의 책임으로 바꾼 후 얻어진다.
2. 시스템에 할당된 커다란 책임은 이제 시스템 안의 작은 규모의 객체들이 수행해야 하는 더 작은 규모의 책임으로 세분화된다.
3. 어떤 객체를 선택할 것인가? → 도메인 모델
    1. 도메인 모델에 포함된 개념을 은유하는 소프트웨어 객체를 선택해야 한다.
4. 협력을 완성하는 데 필요한 메시지를 식별하면서 객체들에게 책임을 한당해 나간다.
5. 마지막으로 협력에 참여하는 객체를 구현하기 위해 클래스를 추가하고 속상과 함께 메서드를 구현하면 시스템의 기능이 완성된 것이다.

객체 설계는 가끔 다음과 같이 표현되기도 한다.

> 요구사항들을 식별하고 도메인 모델을 생성한 후, 소프트웨어 클래스에 매서드들을 추가하고, 요구사항을 충족시키기 위해 객체들 간의 메시지 전송을 정의하라.
> 

책임-주도 설계는 유스케이스로부터 첫 번째 메시지와 사용자가 달성하려는 목표를, 도메인 모델로부터 기능을 수용할 수 있는 안정적인 구조를 제공받아 실제로 동작하는 객체들의 협력 공동체를 창조한다.

### 기능 변경을 흡수하는 안정적인 구조

도메인 모델을 기반으로 객체 구조를 설계하는 이유는 도메인 모델이 안정적이기 때문이다.

도메인 모델이 안정적인 이유: 도메인 모델을 구성하는 요소

- 도메인 모델을 구성하는 개념은 비즈니스가 없어지거나 완전히 개편되지 않는 한 안정적으로 유지된다.
    - 정기예금 도메인에서 정기예금, 계좌, 이자율, 이자란 개념은 정기예금이란 금융상품이 없어지거나 완전히 개편되지 않는 한 안정적으로 유지되는 개념이다.
- 도메인 모델을 구성하는 개념 간의 관계는 비즈니스 규칙을 기반으로 하기 때문에 비즈니스 정책이 크게 변경되지 않는 한 안정적으로 유지된다.
    - 계좌와 이자간의 0..1관계는 핵심적인 비즈니스 규칙이 변경되지 않는 한 동일하게 유지된다. (이자는 정기예금이 만기되거나 중도 해지하는 경우에 한해서 단 한번만 지급된다)

비즈니스 정책이나 규칙이 크게 변경되지 않는 한 시스템의 기능이 변경되더라도 객체 간의 관계는 일정하게 유지된다. 기능적인 요구사항이 변경될 경우 책임과 객체 간의 대응 관계만 수정될 뿐이다. 이는 변경에 대한 파급효과를 최소화하고 요구사항 변경에 유연하게 대응할 수 있는 시스템을 구축할 수 있게 한다.

### 연결완전성, 가역성 reversibility

객체지향의 가장 큰 장점은 도메인을 모델링하기 위한 기법과 도메인을 프로그래밍하기 위해 사용하는 기법이 동일하다는 점이다. 따라서 도메인 모델링에서 사용한 **객체**와 **개념**을 프로그래밍 설계에서의 **객체**와 **클래스**로 매끄럽게 변환할 수 있다.

---

# 7장. 함께 모으기

마틴파울러는 객체지향 설계 안에 존재하는 세 가지 상호 연관된 관전에 관해 설명한다.

- 개념 관점 Conceptual Perspective
    - 에서 설계는 도메인 안에 존재하는 개념과 개념들 사이의 관계를 표현한다.
    - 도메인이란 사용자들이 관심을 가지고 있는 특정 분야나 주제를 말하며 소프트웨어는 도메인에 존재하는 문제를 해결하기 위해 개발된다.
    - 이 관점은 사용자가 도메인을 바라보는 관점을 반영한다.
    - 따라서 실제 도메인의 규칙과 제약을 최대한 유사하게 반영하는 것이 핵심이다.
- 명세 관점 Specification Perspective
    - 사용자의 영역인 도메인을 벗어나 개발자의 영역인 소프트웨어로 초점이 옮겨진다.
    - 도메인의 개념이 아니라 실제로 소프트웨어 안에서 살아 숨쉬는 객체들의 책임에 초점을 맞추게 된다.
    - 즉, 객체의 인터페이스를 바라보게 된다.
    - 안타깝게도 대부분의 객체지향 언어가 인터페이스와 구현을 클래스 안으로 섞어 버리기 때문에 많은 설계자들이 인터페이스와 구현을 분리하는 것이 얼마나 중요한지를 잊어버리곤 한다.
    - 객체지향 설계 분야의 오래된 격언: “구현이 아니라 인터페이스에 대해 프로그래밍하라.”
- 구현 관점 Implementation Perspective
    - 객체들이 책임을 수행하는 데 필요한 동작하는 코드를 작성하는 것이다.
    - 따라서 프로그래머는 객체의 책임을 ‘어떻게’ 수행할 것인가에 초점을 맞추며 인터페이스를 구현하는 데 필요한 속성과 메서드를 클래스에 추가한다.

1. 첫 번째 목표는 도메인 모델에서 시작해서 최종 코드까지의 구현 과정을 간략하게나마 설명.
2. 두 번째 목표는 구현 클래스를 개념 관점, 명세 관점, 구현 관점에서 바라본다는 것이 무엇을 의미하는지 설명.

## 커피 전문점 도메인

---

### 커피 전문점이라는 세상

커피 전문점 안에는 메뉴판이 존재한다.

- 메뉴판
    - 아메리카노         1500원
    - 카푸치노            2000원
    - 카라멜 마키아또 2500원
    - 에스프레소         2500원

객체지향의 관점에서 메뉴판은 하나의 객체.

메뉴판은 네 개의 메뉴 항목으로 구성 → 메뉴 항목들 역시 객체로 볼 수 있다.

따라서, 메뉴판은 네 개의 메뉴 항목 객체들을 포함하는 객체라고 볼 수 있다.

손님은 메뉴판을 보고 바리스타에게 주문한다.

객체의 관점에서 보면 손님, 바리스타 역시 객체들이다.

종합해 보면 객체지향의 관점에서 커피 전문점이라는 도메인은 손님 객체, 메뉴 항목 객체, 메뉴판 객체, 바리스타 객체, 커피 객체로 구성된 작은 세상이다.

![Untitled](https://github.com/thepsyentist-public/learning-essence-of-object-orientation/assets/137966751/1a81251c-0fc6-4111-8841-58db2b80892f)


상태와 무관하게 동일하게 행동할 수 있는 객체들은 동일한 타입의 인스턴스로 분류할 수 있다.

손님 객체는 ‘손님 타입’의 인스턴스로 볼 수 있다. 바리스타 객체는 ‘바리스타 타입’ 인스턴스로 볼 수 있다. 아메리카노 커피, 에스프레소 커피, 카푸치노 커피는 모두 ‘커피 타입’의 인스턴스로 볼 수 있다. 메뉴판 객체는 ‘메뉴판 타입’의 인스턴스다. 메뉴판 객체는 아메리카노, 에스프레소, 카푸치노라는 네 개의 메뉴 항목 객체를 포함할 수 있다. 네 개의 메뉴 항목 객체 역시 모두 동일한 ‘메뉴 항목 타입’의 인스턴스로 모델링할 수 있다.

![이처럼 소프트웨어가 대상으로 하는 영역인 도메인을 단순화해서 표현한 모델을 도메인 모델이라고 한다.](https://github.com/thepsyentist-public/learning-essence-of-object-orientation/assets/137966751/4db543b8-3669-40a0-a894-dfa9e38e2020)

이처럼 소프트웨어가 대상으로 하는 영역인 도메인을 단순화해서 표현한 모델을 도메인 모델이라고 한다.

마름모는 포함(containment) 관계 또는 합성(composition) 관계를 나타내는 것으로, 메뉴 항목이 메뉴판에 포함된다는 사실을 표현한다. 메뉴 항목 좌측 아래의 숫자는 메뉴판에 포함되는 메뉴 항목의 개수를 의미한다.

한 타입의 인스턴스가 다른 타입의 인스턴스를 포함하지는 않지만 서로 알고 있어야 할 경우 이를 연관(association) 관계라고 한다. 손님-메뉴판, 손님-바리스타, 바리스타-커피.

## 설계하고 구현하기

---

### 커피를 주문하기 위한 협력 찾기

- 메시지를 먼저 선택하고
- 그 후에 메시지를 수신하기에 적절한 객체를 선택해야 한다는 것을 의미한다.
- 메시지를 수신할 객체는 메시지를 처리할 책임을 맡게 되고 객체가 수신하는 메시지는 객체가 외부에 제공하는 공용 인터페이스에 포함된다.

![메시지 위에 붙은 화살표는 메시지에 담아 전달될 부가적인 정보인 인자를 의미한다. 이 경우 ‘아메리카노를 주문하라’ 메시지는 나중에 ‘커피를 주문하라(아메리카노)’와 같이 인자를 포함하는 형식으로 구현될 것이다.](https://github.com/thepsyentist-public/learning-essence-of-object-orientation/assets/137966751/3d0878ae-3d61-4bd3-8d42-80f4bc642d9e)

메시지 위에 붙은 화살표는 메시지에 담아 전달될 부가적인 정보인 인자를 의미한다. 이 경우 ‘아메리카노를 주문하라’ 메시지는 나중에 ‘커피를 주문하라(아메리카노)’와 같이 인자를 포함하는 형식으로 구현될 것이다.

### 인터페이스 정리하기

객체가 수신한 메시지가 객체의 인터페이스를 결정한다. 객체가 어떤 메시지를 수신할 수 있다는 것은 그 객체의 인터페이스 안에 메시지에 해당하는 오퍼레이션이 존재한다는 것을 의미한다.

객체들을 포괄하는 타입을 정의한 후 식별된 오퍼레이션을 타입의 인터페이스에 추가해야 한다.

객체의 타입을 구현하는 일반적인 방법은 클래스를 이용하는 것이다. 인터페이스에 포함된 오퍼레이션 역시 외부에서 접근 가능하도록 공용(public)으로 선언돼 있어야 한다.

```java
class Customer {
	public void order(String menuName) {}
}

class MenuItem {
}

class Menu {
    public MenuItem choose(String name) {}
}

class Barista {
    public Coffee makeCoffee(MenuItem menuItem) {}
}

class Coffee {
    public Coffee(MenuItem menuItem) {}
}
```

### 구현하기

클래스의 인터페이스를 식별했으므로, 이제 오퍼레이션을 수행하는 방법을 메서드로 구현하자.

```java
class Customer {
    public void order(String menuName, Menu menu, Barista barista) {
        MenuItem menuItem = menu.choose(menuName);
        Coffee coffee = barista.makeCoffee(menuItem);
        ...
    }
}
```

`Customer` 객체는 어떤 방법으로든 자신과 협력하는 `Menu` 객체와 `Barista` 객체에 대한 참조를 알고 있어야 한다. 객체 참조를 얻는 다양한 방법이 있지만 여기서는 `Customer`의 `order()` 메서드의 인자로 `Menu`와 `Barista` 객체를 전달받는 방법으로 해결한다.

```java
class Menu {
    private List<MenuItem> items;

    public Menu(List<MenuItem> items) {
        this.items = items;
    }

    public MenuItem choose(String name) {
        for(MenuItem each : items) {
            if (each.getName().equals(name)) {
                return each;
            }
        }
				return null;
    }
}
```

`MenuItem`의 목록을 `Menu`의 속성으로 포함 시킨 결정 역시 클래스를 구현하는 도중에 내려졌다는 사실에 주목하라. 객체의 속성은 객체의 내부 구현에 속하기 때문에 캡슐화돼야 한다. 객체의 속성이 캡슐화된다는 이야기는 인터페이스에는 객체의 내부 속성에 대한 어떤 힌트도 제공돼서는 안 된다는 것을 의미한다. 이를 위한 가장 휼륭한 방법은 인터페이스를 정하는 단계에서는 객체가 어떤 속성을 가지는지, 또 그 속성이 어떤 자료 구조로 구현됐는지를 고려하지 않는 것이다. 객체에게 책임을 할당하고 인터페이스를 결정할 때는 가급적 객체 내부의 구현에 대한 어떤 가정도 하지 말아야 한다. 객체가 어떤 책임을 수행해야 하는지를 결정한 후에야 책임을 수행하는 데 필요한 객체의 속성을 결정하라. 이것이 객체의 구현 세부 사항을 객체의 공용 인터페이스에 노출시키지 않고 인터페이스와 구현을 깔끔하게 분리할 수 있는 기본적인 방법이다.

```java
class Barista {
    public Coffee makeCoffee(MenuItem menuItem) {
        Coffee coffee = new Coffee(menuItem);
        return coffee;
    }
}

class Coffee {
    private String name;
    private int price;

    public Coffee(MenuItem menuItem) {
        this.name = menuItem.getName();
        this.price = menuItem.cost();
    }
}

class MenuItem {
    private String name;
    private int price;

    public MenuItem(String name, int price) {
        this.name = name;
        this.price = price;
    }

    public int cost() {
        return price;
    }

    public String getName() {
        return name;
    }
}
```

![Untitled 3](https://github.com/thepsyentist-public/learning-essence-of-object-orientation/assets/137966751/dfa3d581-40ae-4d18-8a69-3f3d8cfd7dec)


`MenuItem`의 인터페이스를 구성하는 오퍼레이션들을 `MenuItem` 을 구현하는 단계에 와서야 식별했다는 점을 눈여겨보기 바란다. 인터페이스를 통해 실제로 상호작용을 해보지 않은 채 인터페이스의 모습을 정확하게 예측하는 것은 불가능에 가깝다. 

설계를 간단히 끝내고 최대한 빨리 구현에 돌입하라. 머릿속에 객체의 협력 구조가 번뜩인다면 그대로 코드를 구현하기 시작하라. 설계가 제대로 그려지지 않는다면 고민하지 말고 실제로 코드를 작성해가면서 협력의 전체적인 밑그림을 그려보라. 테스트-주도 설계로 코드를 구현하는 사람들이 하는 작업이 바로 이것이다. 그들은 테스트 코드를 작성해 가면서 협력을 설계한다.

## 코드와 세 가지 관점

---

### 코드는 세 가지 관점을 모두 제공해야 한다

- 개념 관점
    - 도메인을 구성하는 중요한 개념과 관계를 반영한다
    - 소프트웨어 클래스가 도메인 개념의 특성을 최대한 수용하면 변경을 관리하기 쉽고 유지보수성을 향상시킬 수 있다.
        - 예를 들어, 커피를 제조하는 과정을 변경해야 한다면? `Barista` 클래스
- 명세 관점
    - 클래스의 인터페이스를 바라본다.
        - 클래스의 publuc 메서드는 다른 클래스가 협력할 수 있는 공용 인터페이스를 드러낸다. 공용 인터페이스는 외부의 객체가 해당 객체에 접근할 수 있는 유일한 부분이다.
        - 인터페이스를 수정하면 해당 객체와 협력하는 모든 객체에게 영향을 미친다.
        - 객체의 인터페이스는 수정하기 어렵다.
        - 변화에 안정적인 인터페이스를 만들기 위해서는 인터페이스를 통해 구현과 관련된 세부 사항이 드러나지 않게 해야 한다.
- 구현 관점
    - 클래스의 내부 구현을 바라본다.
    - 클래스의 메서드와 속성은 구현에 속하며, 공용 인터페이스의 일부가 아니다.
    - 메서드의 구현과 속성의 변경은 원칙적으로 외부의 객체에게 영향을 미쳐서는 안 된다.
        - 메서드와 속성은 철저하게 내부로 캡술화 한다.

### 도메인 개념을 참조하는 이유

도메인 개념 안에서 적절한 객체를 선택하는 것은 도메인에 대한 지식을 기반으로 코드의 구조와 의미를 쉽게 유추할 수 있게 한다. 이것은 시스템의 유지보수성에 큰 영향을 미친다.

소프트웨어는 항상 변한다. 설계는 변경을 위해 존재한다. 여러 개의 클래스로 기능을 분할하고 클래스 안에서 인터페이스와 구현을 분리하는 이유는 변경이 발생했을 때 코드를 좀 더 수월하게 수정하길 간절히 원하기 때문이다. 소프트웨어 클래스가 도메인 개념을 따르면 변화에 쉽게 대응할 수 있다.

### 인터페이스와 구현을 분리하라

클래스를 봤을 때 클래스를 명세 관점과 구현 관점으로 나눠볼 수 있어야 한다. 캡슐화를 위반해서 구현을 인터페이스 밖으로 노출해서도 안 되고, 인터페이스와 구현을 명확하게 분리하지 않고 흐릿하게 섞어놓아서도 안된다.
