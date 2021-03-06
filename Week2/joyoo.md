# Week 2

# 10. 객체 리터럴

- 객체란?
    
    다양한 타입의 값을 하나의 단위로 구성한 복합적인 자료구조.
    
    객체는 변경 가능한 값이다.
    
    객체는 프로퍼티와 메서드로 구성된 집합체이다.
    
    → 프로퍼티 : 객체의 상태를 나타내는 값
    
    → 메서드 : 프로퍼티를 참조하고 조작할 수 있는 동작
    
- 객체 리터럴에 의한 객체 생성
    
    객체 리터럴 : 객체를 생성하기 위한 표기법
    
    ```jsx
    var person = {
      name: 'Lee',
      sayHello: function() {
        console.log(`Hello! My name is ${this.name}.`);
      }
    };
    
    console.log(typeof person); // object
    console.log(person); // {name: "Lee", sayHello: f}
    ```
    
    객체 리터럴의 중괄호는 코드 블록을 의미하지 않는다. 객체 리터럴은 값으로 평가되는 표현식이기 때문에 객체 리터럴의 닫는 중괄호 뒤에는 세미콜론을 붙인다.
    
- 프로퍼티
    
    > 객체는 프로퍼티의 집합이며, 프로퍼티는 키와 값으로 구성된다.
    > 
    
    프로퍼티를 나열할 때는 쉼표로 구분한다.
    
    식별자 네이밍 규칙을 따르지 않는 이름에는 반드시 따옴표를 사용해야 한다.
    
    문자열 또는 문자열로 평가할 수 있는 표현식을 사용해 프로퍼티 키를 동적으로 생성할 수도 있다. 이 경우 프로퍼티 키로 사용할 표현식을 대괄호로 묶어야 한다.
    
    ```jsx
    var obj = {};
    var key = 'Hello';
    
    obj[key] = 'world';
    
    console.log(obj); // {hello: 'world'}
    ```
    
- 메서드
- 프로퍼티 접근
    1. 마침표 프로퍼티 접근 연산자(.)를 사용하는 마침표 표기법
    2. 대괄호 프로퍼티 접근 연산자([…])를 사용하는 대괄호 표기법
    
    ```jsx
    var person = {
      name: 'Lee'
    }
    
    console.log(person.name);
    
    console.log(person['name']);
    ```
    
    대괄호 연산자 내의 따옴표로 감싸지 않은 이름이 있을 경우 ReferenceError가 발생.
    
    객체에 존재하지 않는 프로퍼티에 접근하면 undefined를 반환.
    
- 프로퍼티 값 갱신
    
    이미 존재하는 프로퍼티에 값을 할당하면 프로퍼티 값이 갱신된다.
    
- 프로퍼티 동적 생성
    
    존재하지 않는 프로퍼티에 값을 할당하면 프로퍼티가 동적으로 생성되어 추가되고 프로퍼티 값이 할당된다.
    
- 프로퍼티 삭제
    
    delete 연산자는 객체의 프로퍼티를 삭제한다. 없는 프로퍼티를 delete 시도해도 오류가 발생하지 않는다.
    
- ES6에서 추가된 객체 리터럴의 확장 기능
    - 프로퍼티 축약 표현
    - 계산된 프로퍼티 이름
    - 메서드 축약 표현

# 11. 원시값과 객체의 비교

- 원시 값
    - 변경 불가능한 값
        
        원시 값은 읽기 전용 값으로서 변경할 수 없다.
        
        변수 값을 변경하기 위해 원시 값을 재할당하면 새로운 메모리 공간을 확보하고 재할당한 값을 저장한 후, 변수가 참조하던 메모리 공간의 주소를 변경한다.
        
    - 문자열과 불변성
        
        문자열 역시 원시 값이므로 값을 변경하는 것은 불가능하고, 재할당만이 가능하다.
        
        인덱스로 프로퍼티 값에 접근할 수 있고 length 프로퍼티를 갖는 유사 배열 객체이다.
        
    - 값에 의한 전달
        
        두 변수의 원시 값은 서로 다른 메모리 공간에 저장된 별개의 값이 되어 어느 한 쪽에서 재할당을 통해 값을 변경하더라도 서로 간섭할 수 없다.
        
- 객체
    - 변경 가능한 값
        
        원시 값을 할당한 변수를 참조하면 메모리에 저장되어 있는 원시 값에 접근하고, 객체를 할당한 변수를 참조하면 메모리에 저장되어 있는 참조 값으로 통해 실제 객체에 접근한다.
        
    - 참조에 의한 전달
        
        객체를 가리키는 변수를 다른 변수에 할당하면 원본의 참조 값이 복사되어 전달된다. 이를 참조에 의한 전달이라 한다.
        

# 12. 함수

- 함수란?
- 함수를 사용하는 이유
- 함수 리터럴
    
    자바스크립트의 함수는 객체 타입의 값이므로 변수에 할당할 수 있다.
    
- 함수 정의
    - 함수 선언문
        
        ```jsx
        function add(x, y)
        {
        	return x + y;
        }
        ```
        
    - 함수 표현식
        
        ```jsx
        var add = function(x, y)
        {
        	return x + y;
        }
        ```
        
    - 함수 생성 시점과 함수 호이스팅
        
        모든 선언문이 그렇듯 함수 선언문도 코드가 한 줄씩 술차적으로 실행되는 시점인 런타임 이전에 자바스크립트 엔진에 의해 먼저 실행된다.
        
        함수 선언문이 코드의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트 고유의 특징을 함수 호이스팅이라 한다.
        
        함수 표현식으로 함수를 정의하면 함수 호이스팅이 발생하는 것이 아니라 변수 호이스팅이 발생한다.
        
        함수 호이스팅은 함수를 호출하기 전에 반드시 함수를 선언해야 한다는 당연한 규칙을 무시하기 때문에 함수 선언문 대신 함수 표현식을 사용할 것을 권장한다.
        
    - Function 생성자 함수
    - 화살표 함수
        
        function 키워드 대신 화살표 => 를 사용해 좀 더 간략한 방법으로 함수를 선언할 수 있다.
        
        ```jsx
        const add = (x, y) => x + y;
        ```
        
- 함수 호출
    - 매개변수와 인수
        
        함수는 매개변수의 개수와 인수의 개수가 일치하는지 체크하지 않으며, 일치하지 않을 때 에러가 발생하지 않는다. 인수가 부족할 경우 undefined가 자동으로 할당되며, 인수가 초과할 경우 초과된 인수는 무시된다.
        
    - 인수 확인
        1. 자바스크립트 함수는 매개변수와 인수의 개수가 일치하는지 확인하지 않는다.
        2. 자바스크립트는 동적 타입 언어다. 따라서 자바스크립트 함수는 매개변수의 타입을 사전에 지정할 수 없다.
        
        → 함수를 정의할 때 적절한 인수가 전달되었는지 확인할 필요가 있다.
        
    - 매개변수의 최대 개수
        
        함수의 매개변수는 코드를 이해하는 데 방해되는 요소이므로 이상적인 매개변수 개수는 0개이며 적을수록 좋다.
        
        이상적인 함수는 한 가지 일만 해야 하며 가급적 작게 만들어야 한다.
        
        매개변수는 최대 3개 이상을 넘지 않는 것을 권장한다.
        
    - 반환문
        
        return 키워드 뒤에 반환값으로 사용할 표현식을 명시적으로 지정하지 않으면 undefined가 반환된다.
        
- 참조에 의한 전달과 외부 상태의 변경
    
    원시 값은 값에 의한 전달, 객체는 참조에 의한 전달 방식으로 동작한다.
    
    → 원시 값은 함수 외부 값이 바뀌지 않지만, 객체는 함수 외부 값이 변한다.
    
    의도치 않은 값의 변경은 추적하기 어렵다.
    
    → 객체를 불변 객체로 만들어 사용한다.
    
- 다양한 함수의 형태
    - 즉시 실행 함수
        
        함수 정의와 동시에 즉시 호출되는 함수. 단 한 번만 호출되며 다시 호출할 수 없다.
        
    - 재귀 함수
    - 중첩 함수
        
        함수 내부에 정의된 함수를 중첩 함수 또는 내부 함수라 한다. 그리고 중첩 함수를 포함하는 함수는 외부 함수라 부른다.
        
    - 콜백 함수
        
        함수의 변하지 않는 공통 로직은 미리 정의해두고, 경우에 따라 변경되는 로직은 추상화해서 함수 외부에서 함수 내부로 전달할 수 있다.
        
        함수의 매개변수를 통해 다른 함수의 내부로 전달되는 함수를 콜백 함수라고 하며, 매개변수를 통해 함수의 외부에서 콜백 함수를 전달받은 함수를 고차 함수라고 한다.
        
    - 순수 함수와 비순수 함수
        
        어떤 외부 상태에 의존하지도 않고 변경하지도 않는, 부수 효과가 없는 함수를 순수 함수라고 하고, 외부 상태에 의존하거나 외부 상태를 변경하는, 즉 부수 효과가 있는 함수를 비순수 함수라고 한다.
        

# 13. 스코프

- 스코프란?
    
    모든 식별자는 자신이 선언된 위치에 의해 다른 코드가 식별자 자신을 참조할 수 있는 유효 범위가 결정된다. 이를 스코프라 한다. 즉, 스코프는 식별자가 유효한 범위를 말한다.
    
    > “코드가 어디서 실행되며 주변에 어떤 코드가 있는지"를 렉시컬 환경이라고 한다.
    > 
- 스코프의 종류
    - 전역과 전역 스코프
        
        전역에 변수를 선언하면 전역 스코프를 갖는 전역 변수가 되며, 전역 변수는 어디서든지 참조할 수 있다.
        
    - 지역과 지역 스코프
        
        지역 변수는 자신의 지역 스코프와 하위 지역 스코프에서 유효하다.
        
- 스코프 체인
    
    스코프가 계층적으로 연결된 것을 스코프  체인이라 한다.
    
    변수를 참조할 때 자바스크립트 엔진은 스코프 체인을 통해 변수를 참조하는 코드의 스코프에서 시작하여 상위 스코프 방향으로 이동하며 선언된 변수를 검색한다.
    
    - 스코프 체인에 의한 변수 검색
    - 스코프 체인에 의한 함수 검색
- 함수 레벨 스코프
    
    C나 자바 등을 비롯한 대부분의 프로그래밍 언어는 함수 몸체만이 아니라 모든 코드 블록이 지역 스코프를 만드는데 이를 블록 레벨 스코프라 한다.
    
    하지만 var 키워드로 선언된 변수는 오로지 함수의 코드 블록만을 지역 스코프로 인정한다. 이러한 특성을 함수 레벨 스코프라 한다.
    
- 렉시컬 스코프
    1. 함수를 어디서 호출했는지에 따라 함수의 상위 스코프를 결정한다. → 동적 스코프
    2. 함수를 어디서 정의했는지에 따라 함수의 상위 스코프를 결정한다. → 정적 스코프, 렉시컬 스코프 ⇒ 자바스크립트의 작동방식

# 14. 전역 변수의 문제점

- 변수의 생명 주기
    - 지역 변수의 생명 주기
        
        지역 변수의 생명 주기는 함수의 생명 주기와 일치한다.
        
        호이스팅은 스코프를 단위로 동작한다. 
        
        ```jsx
        var x = 'global';
        
        function foo(){
        	console.log(x); // undefined
        	var x = 'local';
        }
        
        foo();
        console.log(x); // global
        ```
        
        지역 변수는 함수 전체에서 유효하다.
        
        호이스팅은 변수 선언이 스코프의 선두로 끌어 올려진 것처럼 동작하는 자바스크립트 고유의 특징을 말한다.
        
    - 전역 변수의 생명 주기
        
        var 키워드로 선언한 전역 변수의 생명 주기는 전역 객체의 생명 주기와 일치한다.
        
- 전역 변수의 문제점
    1. 암묵적 결합
    2. 긴 생명 주기
    3. 스코프 체인 상에서 종점에 존재
        
        전역 변수의 검색 속도가 가장 느리다.
        
    4. 네임스페이스 오염
        
        자바스크립트는 파일이 분리되어있다 하더라도 전역 스코프를 공유하기 때문에 다른 파일에서 동일한 이름으로 명명된 전역변수나 전역 함수가 같은 스코프 내에 존재할 경우 예상치 못한 결과를 가져올 수 있다.
        
- 전역 변수의 사용을 억제하는 방법
    - 즉시 실행 함수
    - 네임스페이스 객체
    - 모듈 패턴
    - ES6 모듈

# 15. let, const 키워드와 블록 레벨 스코프

- var 키워드로 선언한 변수의 문제점
    - 변수 중복 선언 허용
    - 함수 레벨 스코프
    - 변수 호이스팅
- let 키워드
    - 변수 중복 선언 금지
        
        ```jsx
        var foo = 123;
        
        var foo = 456; // -> 에러 아님
        
        let bar = 123;
        
        let bar = 456; // -> SyntaxError
        ```
        
    - 블록 레벨 스코프
        
        ```jsx
        let foo = 1; // 전역 변수
        
        {
        	let foo = 2; // 지역 변수
        	let bar = 3; // 지역 변수
        }
        
        console.log(foo); // 1
        console.log(bar); // ReferenceError
        ```
        
    - 변수 호이스팅
        
        ```jsx
        console.log(foo); // ReferenceError
        let foo;
        ```
        
        let 키워드로 선언한 변수는 “선언 단계"와 “초기화 단계"가 분리되어 진행된다.
        
        let 키워드로 선언한 변수는 변수 호이스팅이 발생하지 않는 것으로 보이지만 그렇지 않다.
        
    - 전역 객체와 let
        
        var 키워드로 선언한 전역 변수와 전역 함수, 그리고 선언하지 않은 변수에 값을 할당한 암묵적 전역은 전역 객체 window의 프로퍼티가 되나, let 키워드로 선언한 전역 변수는 전역 객체의 프로퍼티가 아니다.
        
- const 키워드
    - 선언과 초기화
        
        const 키워드로 선언한 변수는 반드시 선언과 동시에 초기화해야 한다.
        
        const 키워드로 선언한 변수는 블록 레벨 스코프를 가지며, 변수 호이스팅이 발생하지 않는 것처럼 동작한다.
        
    - 재할당 금지
        
        var 또는 let 키워드로 선언한 변수는 재할당이 자유로우나 const 키워드로 선언한 변수는 재할당이 금지된다.
        
    - 상수
        
        재할당이 금지된 변수를 상수라고 한다.
        
    - const 키워드와 객체
        
        const 키워드로 선언된 변수에 객체를 할당한 경우 값을 변경할 수 있다.
        
        → const 키워드는 재할당을 금지할 뿐 “불변"을 의미하지 않는다.
        
- var vs. let vs. const
    1. ES6를 사용한다면 var 키워드는 사용하지 않는다.
    2. 재할당이 필요한 경우 한정해 let을 사용한다. 
    3. 변경이 발생하지 않고 읽기 전용으로 사용하는 원시 값과 객체에는 const 키워드를 사용한다. const 키워드는 재할당을 금지하므로 var, let 키워드보다 안전하다.
    
    → 일단 const 키워드를 사용해 변수를 선언하고, 재할당이 필요한 경우 이후에 let으로 바꿔도 늦지 않다.
    

## 퀴즈

### 10장

다음 코드의 실행 결과는?

```jsx
var weather = {
  date: '20220727',
  weather : 'Sunny',
  getInfo1: () => {
    console.log(this.date + this.weather)
  },
  getInfo2: function () {
    console.log(this.date + this.weather)
  }
}

weather.getInfo1()
weather.getInfo2()
```

### 11장

다음 보기 중 옳지 않은 것은?

1. 원시 값은 값에 의한 전달로 복사가 된다.
2. 변수는 메모리 주소를 기억하고 있다.
3. 원시 값의 복사는 깊은 복사이며 객체의 복사는 얕은 복사이다.
4. 객체의 복사가 이루어질 경우 두 개의 식별자가 하나의 메모리 주소를 기억하며 이 주소에는 객체의 참조 값이 저장되어있다.
5. 값에 의한 전달과 참조에 의한 전달은 식별자가 기억하는 메모리 공간에 저장되어있는 값을 복사해서 전달한다는 면에서 동일하다.

### 12장

다음 보기 중 옳지 않은 것은?

1. 함수 리터럴은 함수 이름, 매개변수 목록, 함수 몸체로 이루어져 있다.
2. 함수 선언문은 함수 이름을 생략할 수 없다.
3. 그룹 연산자 안에서 함수 리터럴은 함수 선언문과 함수 리터럴 표현식 두 가지 방법으로 해석될 수 있다.
4. 함수 선언문으로 함수를 정의하면 함수 호이스팅, 함수 표현식으로 함수를 정의하면 변수 호이스팅이 발생한다.
5. 함수에 정의된 매개변수의 개수보다 더 많은 인자가 전달될 경우 초과된 인수는 무시된다.

### 13장

다음 코드의 실행 결과는?

```jsx
var x = 1;

function foo() {
  var x = 10;
  console.log('global function foo');
}

function bar() {
  function foo() {
    console.log('local function foo');
    console.log(x);
  }

  foo();
  for (var x = 0; x < 10; x++) {};
  console.log(x);
}

bar();
console.log(x);
```

### 14장

### 15장

다음 중 옳지 않은 것은?

1. var 키워드를 사용할 경우 변수 중복 선언이 허용되고, 변수 호이스팅이 일어난다.
2. var 키워드와 달리, let과 const 키워드는 블록 레벨 스코프를 따른다.
3. console.log 등으로 먼저 참조를 하고 뒤에 let, const로 선언할 경우 ReferenceError: ~ is not defined 에러가 발생한다.
4. const 키워드는 선언과 동시에 초기화해야 한다.
5. const 키워드로 할당된 원시 값은 변경할 수 없으나 const 키워드로 할당된 객체는 값을 변경할 수 있다.

정답

10장. 

NaN

20220727Sunny

→ 객체 내 화살표 함수에서 this는 전역 객체를 가리키며, 브라우저에서는 window, Node.js에서는 global 객체를 가리킨다.

11장. 4번. 두 개의 식별자는 각각 다른 메모리 주소를 기억하며, 하나의 객체의 참조 값을 저장하고 공유한다.

12장. 3번. 그룹연산자 내에서 함수 리터럴은 함수 리터럴 표현식으로만 해석된다.

13장. 
local function foo
undefined
10
1

15장. 3번. ReferenceError: Cannot access ~ before initialization 에러가 발생한다.