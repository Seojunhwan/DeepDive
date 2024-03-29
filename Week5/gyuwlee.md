> 오늘 코로나 검사로 인해 불참하게 돼서 설명드리려던 내용을 부득이하게 다 해설에 적어두느라 텍스트가 많아졌습니다 🥲

<br/>

# CH25. 클래스

## 1) 메서드 오버라이딩
```js
class Animal {
  showName() {
    alert('animal');
  }

  constructor() {
    this.showName();
  }
}

class Rabbit extends Animal {
  showName() {
    alert('rabbit');
  }
}

new Animal(); // animal
new Rabbit(); // 결과를 예측해보세요!
```
<details>
<summary><strong>해설</strong></summary>

- `new Rabbit();` 의 실행 결과는 (당연히?) `rabbit` 입니다.
- 자식 클래스 `Rabbit`의 인스턴스가 초기화될 때, 암묵적으로 `super` 가 호출되어 부모 생성자 `constructor` 를 호출합니다. 
    - 자식 클래스에서 부모 생성자를 호출하면 오버라이딩한 메서드가 실행됩니다.
</details>

<br/>

## 2) 🌟 클래스 필드 오버라이딩
오버라이딩은 메서드뿐만 아니라 클래스 필드를 대상으로도 적용할 수 있습니다.
```js
class Animal {
  name = 'animal' // 위의 showName '메서드' 대신 name '필드' 사용

  constructor() {
    alert(this.name); // 위의 this.showName '메서드' 대신 this.name '필드' 사용
  }
}

class Rabbit extends Animal {
  name = 'rabbit';
}

new Animal(); // animal
new Rabbit(); // 결과를 예측해보고, 왜 그런지 이유를 생각해봅시다
```
<details>
<summary><strong>해설</strong></summary>

- `new Animal()` 과 `new Rabbit()` 을 실행할 때, 두 경우 모두 `Animal` 의 `alert` 함수가 실행되면서 alert 창에 `animal` 이 출력됩니다.
    - 단지 메서드를 필드로 바꿨을 뿐인데, 위의 메서드 오버라이딩 예시와 결과가 다릅니다.
- 즉 부모 생성자(`Animal` 안의 `constructor`)는 자식 클래스에서 오버라이딩한 값(`rabbit`)이 아니라, 여전히 부모 클래스 안의 필드 값(`animal`)을 사용합니다.
    - **상속을 받고 필드 값을 오버라이딩했는데 새로운 값 대신 부모 클래스 안에 있는 기존 필드 값을 사용합니다.** 어째서일까요?

<details>
<summary><strong>해설 2 : 필드 초기화 순서</strong></summary>

이유는 필드 초기화 순서 때문입니다. 클래스 필드는 다음과 같은 규칙에 따라 초기화 순서가 달라집니다.
- 아무것도 상속받지 않는 베이스 클래스는 생성자 실행 이전에 초기화됨
- **부모 클래스가 있는 경우엔 super() 실행 직후에 초기화**됨

위 예시에서 `Rabbit` 은 하위 클래스이고 `constructor()` 가 정의되어 있지 않습니다. 
- 따라서 `new Rabbit()` 을 실행하면 `super()` 가 호출되고 그 결과 부모 생성자가 실행됩니다. - 이때 필드 초기화 순서에 따라, 하위 클래스 `Rabbit` 의 필드는 `super()` 실행 후에 초기화됩니다. 
    - 위 예시에서 부모 생성자가 실행(`alert(this.name);`)되는 시점에 `Rabbit` 의 `name` 필드는 아직 존재하지 않습니다. 따라서 `Animal` 에 있는 필드가 사용된 것입니다.

즉, 자바스크립트는 오버라이딩시 필드와 메서드의 동작 방식이 미묘하게 다릅니다 ~!
</details>

</details>

<br/>

# CH26. ES6 함수의 추가 기능

## 1) 화살표 함수와 this 바인딩
- **화살표 함수**와 **일반 함수를 `.bind(this)` 를 사용해서 호출**하는 것 간의 차이가 있을까요?
<details>
<summary><strong>해설</strong></summary>

```js
func.bind(context)
```
- `func.bind(context)` 는 함수처럼 호출 가능한 '특수 객체(exotic object)'를 반환합니다. 
    - 이 객체를 호출하면 지정된 컨텍스트로 this가 고정된 함수가 반환됩니다.
- 화살표 함수는 아무것도 바인딩시키지 않습니다. 화살표 함수엔 아예 `this` 가 존재하지 않습니다.
    - 따라서 화살표 함수에서 `this` 를 사용하면 일반 변수 서칭과 마찬가지로 `this` 의 값을 **외부 렉시컬 환경**에서 찾습니다.
- 따라서 일반 함수를 원형으로 만들어 놓고 `.bind(this)` 를 활용하면, 변수를 선언하여 원하는 컨텍스트에 별도로 바인딩해서 사용할 수 있습니다.
    - ex) 생성자 함수로 기능하는 경우 각 인스턴스마다 다른 컨텍스트를 바인딩
- 하지만 화살표 함수는 애초에 컨텍스트가 있는 긴 코드보다는 자체 컨텍스트가 없는 짧은 코드를 담을 용도로 만들어졌습니다. 따라서 `this` 가 존재하지 않고, 생성자 함수 등으로 사용될 수도 없습니다.

이러한 차이점이 있으므로, 두 방식을 동일시해서는 안 되고 코드의 기능이나 재사용성 등을 고려하여 구분하여 사용해야 한다고 합니다 ~!
</details>

<br/>

# CH27. 배열
length 프로퍼티와 관련지어서 짧은 문제를 내려다가 27.8의 push, pop, shift, unshift를 미리 다루게 되었습니다 😂

## 1) 배열 앞과 배열 뒤
`push` 와 `pop` 은 빠르지만 `shift` 와 `unshift` 는 느립니다. 어째서일까요?
- `length` 프로퍼티의 조작과 (조금) 관련이 있습니다.

<details>
<summary><strong>해설</strong></summary>

위의 이야기는 즉 **배열 앞에 무언가를 해주는 메서드**가 **배열 끝에 무언가를 해주는 메서드**보다 느리다는 뜻입니다.

`shift` 연산은 아래 3가지 동작을 모두 수행해야 이뤄집니다:
- 인덱스가 `0` 인 요소를 제거합니다.
- 모든 요소를 왼쪽으로 이동시킵니다. 이때 `인덱스 1` 은 `0` , `2` 는 `1` 로 변합니다.
- **`length` 프로퍼티 값을 갱신**합니다.

따라서 시간복잡도는 `O(N)` 이 됩니다.

반면 `pop` 메서드로 요소를 끝에서 제거하려면 마지막 요소를 제거하고 `length` 프로퍼티의 값을 줄여주기만 하면 됩니다.

알고리즘 문제를 풀다 보면 큐 자료구조를 사용해야 하는 경우가 생기는데, 다른 언어는 라이브러리에 주로 <u>연결리스트로 구현된 큐</u>를 제공하지만 JS는 제공하지 않습니다. 
 - 기본적으로 큐 자료구조에서는 연결 리스트를 사용하여 첫 번째 원소에 접근하는 시간을 `O(1)` 로 해결할 수 있습니다.
 - 하지만 JS처럼 큐를 따로 제공하지 않아 배열과 shift 메서드를 이용한 경우에는 배열 전체를 한 번 순회하면서 위치 재조정을 하는 시간까지 추가로 필요하기 때문에 다른 언어에서보다 더 많은 시간이 소요됩니다.

따라서 시간복잡도가 고려되는 문제에서 큐를 사용한다면 연결리스트나 클래스로 직접 구현해서 사용하라고 합니다 ~!

참고:
- [연결리스트로 구현](https://algoroot.tistory.com/55)
- [클래스로 구현](https://velog.io/@longroadhome/%EC%9E%90%EB%A3%8C%EA%B5%AC%EC%A1%B0-JS%EB%A1%9C-%EA%B5%AC%ED%98%84%ED%95%98%EB%8A%94-.%ED%81%90-Queue)
</details>

<br/>

-------------------

<details>
<summary><strong>내용 정리(중)</strong></summary>

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
</details>

