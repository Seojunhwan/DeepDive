# CH25. 클래스
## 1) 프로토타입과 클래스
- 자바스크립트는 프로토타입 기반 객체지향 언어다.
- 프로토타입과 클래스는 각기 다른 객체 생성 메커니즘을 구성한다.
- 클래스는 값으로 사용할 수 있는 일급 객체다.
- 클래스도 프로토타입을 통해 상속 관계를 구현한다.

## 2) 클래스 정의
- 클래스에는 0개 이상의 **메서드**만 정의할 수 있다.

## 클래스의 인스턴스 생성 과정

## 클래스의 프로퍼티
### 클래스 필드
- constructor 내부가 아닌 몸체에서 클래스 필드를 정의할 때에는 this를 쓰지 않아도 된다
- 클래스 필드를 참조할 때에는 반드시 this를 붙여서 해줘야 한다.

### 클래스 메서드
- 프로토타입 메서드
- 정적 메서드

### static private 필드
- 왜 필요한지..?
