# 2 Week) 10장~15장

### ☑️ 문제

### 10장: 객체 리터럴

```jsx
다음 중 출력 결과가 제대로 나오지 않는 것은?

var person = {
	name: 'Kim'
};
```

```jsx
1. 
	var key = 'age';
	person[key] = 20;
	console.log(person.age); // 20

2. 
	person.name = 'Lee';
	console.log(person.name); //Lee

3.
	person.name = 'Choi';
	console.log(person.[name]); //Choi

4. 
	delete person.gender;
	console.log(person); //{name: 'Lee', age: 20}

5.
	let color = 'white';
	person = {color}
	console.log(person.color); // white
```

### **11장: 원시 값과 객체의 비교**

```jsx
다음 중 설명이 옳지 않은 것은?

1) 자바스크립트의 문자열은 원시타입으로 변경 불가능한 값이다.
2) 문자열은 유사배열객체이기 때문에 배열처럼 인덱스로 프로퍼티 값에 접근할 수 있다. 
그러나 값은 바꿀 수 없다.
3) 식별자는 메모리 주소에 붙인 이름으로, 메모리 주소를 통해 메모리 공간에 저장된 값에 접근한다.
4) 객체를 할당한 변수를 참조하면 메모리에 저장되어 있는 참조값을 통해 실제 객체에 접근한다.
5) 객체를 가리키는 변수를 다른 변수에 할당하면 참조값을 복사하여 전달하기 때문에 
원본과 사본의 메모리 주소는 같고 동일한 참조값을 갖는다. 
```

### **12장: 함수**

```jsx
다음 주 아래의 함수에 대한 설명을 옳지 않은 것은?

var div2 = function foo (x , y) {
	return  x / y;
};

-

1) 함수 리터럴로 생성한 함수 객체를 변수에 할당하는 함수 표현식 방식으로 함수를 정의했다.
2) console.log(foo(10, 2))의 결과는 5이다
3) 함수 리터럴의 함수 이름은 생략 가능하기 때문에 아래와 같은 함수도 가능하다.
		var div2 = function (x , y) {
			return  x / y;
		};
4) 함수 선언문의 함수 이름은 생략할 수 없기 때문에 다음과 같은 함수는 불가능하다
		function (x , y) {
			return  x / y;
		};
5) 위 함수를 화살표 함수로 표현하면 다음과 같이 표현할 수 있다.
		const div2 = (x , y) => x / y;
```

### **13장: 스코프**

```jsx
다음 중 설명이 옳지 않은 것은?

1) 스코프란 자바스크립트 엔진이 식별자를 검색할 때 사용하는 규칙이다.
2) var 키워드로 선언된 변수는 같은 스코프 내에서 중복 선언이 허용된다.
3) var 키워드는 함수 레벨 스코프만 인정하기 때문에 var 키워드로 선언된 변수는 코드 블록 내에서 선언되었을지라도 모두 전역변수다
4) const와 let은 블록 레벨 스코프를 지원하기 때문에 const와 let으로 선언된 변수는 코드 블록 내에서만 유효하다
5) 자바스크립트는 렉시컬 스코프를 따르므로 함수를 어디서 정의했는지에 따라 상위 스코프를 결정한다.
```

### **14장: 전역 변수의 문제점**

```jsx
다음 중 옳지 않은 것은?

1) 지역 변수의 생명 주기는 함수의 생명 주기와 일치한다. 

2) 
var x = 'first';

function foo() {
		console.log(x);
		var x = 'second';
		console.log(x);
}

foo(); // undefined second

위와 같은 현상이 일어나는 이유는 호이스팅 때문이다.

3) 전역 변수의 사용을 억제하는 방법으로는 즉시 실행 함수, 네임 스페이스 객체, 모듈 패턴이 있다.

4) ES6 모듈을 사용해도 전역 변수는 사용할 수 있다.

```

### **15장: let, const 키워드와 블록 레벨 스코프**

```jsx
다음 중 옳지 않은 것은?

1) 
console.log(a); //undefined
a = 'a';
console.log(a); // a
var a;

2) 
console.log(a); //ReferenceError
a = 'a';
console.log(a);
let a;

3)
let a = 'a'; //ReferenceError
{
	console.log(a); 
	let a = 'b';
}

4) const로 선언한 변수는 반드시 선언과 동시에 초기화 해야한다.
5) var, const, let로 선언한 변수는 객체 window의 프로퍼티가 된다.
```

---

### ☑️ 10장~15장 정리

- ☑️ **10장: 객체 리터럴**
    
    **10.1 객체란?**
    
    자바스크립트는 객체 기반의 프로그래밍 언어.
    
    원시 타입값 = 변경 불가능
    
    객체 타입값 = 변경 가능 (함수, 배열, 정규 표현식 등)
    
    객체란? 0개의 프로퍼티로 구성된 집합. 키와 값으로 구성
    
    * 프로퍼티 값이 함수일경우 메서드라 부름
    
    - 프로퍼티: 객체의 상태를 나타내는 값
    
    - 메서드: 프로퍼티(상태데이터)를 참조하고 조작할 수 있는 동작
    
    **10.2 객체 리터럴에 의한 객체 생성**
    
    객체 생성 방법: 객체 리터럴, object 생성자 함수, 생성자 함수, object.create 메서드, 클래스(ES6)
    
    - 일반적인 방법: 객체 리터럴
    
    ```c
    var person = {
    	name: 'Lee',
    	sayHello: function(){
    			~~~
    	}
    };
    ```
    
    → 객체 리터럴의 중괄호는 코드 블록을 의미하지 않는다. 고로 세미콜론을 붙여줘야함.
    
    → 객체를 생성한 이후에도 프로퍼티를 동적으로 추가할 수 있음!!
    
    **10.3 프로퍼티**
    
    프로퍼티 키: 빈문자열을 포함하는 모든 문자열 또는 심벌값 가능 → 프로퍼티값에 접근할 수 있는 이름으로서 식별자 역할을 함 (그렇지만 식별자 네이밍 규칙 따라야 하는 것은 아님. 규칙 안 따를 거면 반드시 따옴표 써야함. 근데 번거로우니까 그냥 규칙 따르자.)
    
    프로퍼티 값: 자바스크립트에서 사용할 수 있는 모든 값 가능
    
    - 문자열 또는 문자열로 평가할 수 있는 표현식을 통해 프로퍼티 키를 동적으로 생성할 수도 있다. 이 경우에는 프로퍼티 키로 사용할 표현식을 대괄호로 묶어야 한다.
    
    ```jsx
    var obj = {};
    var key = 'hello';
    obj[key] = 'world';
    //var obj = {[key]: 'world'};
    console.log(obj);  //{ hello : "world" }
    ```
    
    - 프로퍼티 키에 문자열이나 심벌 값 외의 값을 사용하면 암묵적 타입ㅂ ㅕㄴ환을 통해 문자열이 된다.
    - 이미 존재하는 프로퍼티 키를 중복 선언 시, 나중에 선언한 프로퍼티가 덮어쓰여진다. 에러가 발생하지 않는다는 점에 주의
    
    **10.4 메서드**
    
    프로퍼티 값이 함수일 경우 메서드라 부른다. ⇒ 메서드는 객체에 묶여있는 함수를 의미한다.
    
    **10.5 프로퍼티 접근**
    
    프로퍼티에 접근하는 방법은 2가지
    
    1) 마침표 프로퍼티 접근 연산자를 이용 .
    
    2) 대괄호 프로퍼티 접근 연산자를 이용 []
    
    - 대괄호 표기법을 사용하는 경우 대괄호안의 프로퍼티 키는 반드시 따옴표로 감산 문자열이어야 한다. 아님 자바스크립트 엔진은 식별자로 해석한다.
    
    ```jsx
    console.log(person['name']);
    ```
    
    - 객체에 존재하지 않는 프로퍼티에 접근하면 undefined를 반환한다. 오류가 발생하지 않는다.
    - 프로퍼티 키가 숫자로 이뤄진 문자열일 경우 따옴표 생략 가능
    
    **10.6 프로퍼티 값 갱신**
    
    이미 존재하는 프로퍼티에 값을 할당하면 프로퍼티 값이 갱신된다.
    
    **10.7 프로퍼티 동적 생성**
    
    존재하지 않는 프로퍼티에 값을 할당하면 프로퍼티가 동적으로 생성되어 추가되고 프로퍼티 값이 할당된다.
    
    **10.8 프로퍼티 삭제**
    
    delete 연산자는 객체의 프로퍼티를 삭제한다.
    
    존재하지 않는 프로퍼티를 삭제하면 에러 안뜨고 그냥 무시.
    
    ```jsx
    delete person.age;
    ```
    
    **10.9 ES6에서 추가된 객체 리터럴의 확장 기능**
    
    ____10.9.1 프로퍼티 축약 표현
    
    프로퍼티 값으로 변수를 사용하는 경우, 변수 이름과 프로퍼티 키가 동일한 이름일 때 프로퍼티 키를 생략할 수 있다. 프로퍼티 키는 변수 이름으로 자동 생성
    
    ```jsx
    let x = 1, y = 2;
    
    const obj = { x, y };
    console.log(obj); // { x : 1, y : 2 }
    ```
    
    ____10.9.2 계산된 프로퍼티 이름
    
    문자열 또는 문자열로 타입 변환할 수 있는 값으로 평가되는 표현식을 사용해 프로퍼티 키를 동적으로 생성할 수도 있다. → 프로퍼티 키로 사용할 표현식을 대괄호([])로 묶어야 한다. 이를 계산된 프로퍼티 이름이라 한다.
    
    ```jsx
    obj[prefix + '-' + ++i] = i;
    obj[prefix + '-' + ++i] = i;
    obj[prefix + '-' + ++i] = i;
    
    console.log(obj); // {prop-1: 1, prop-2: 2, prop-3: 3}
    ```
    
    이렇게도 가능!
    
    - ES6에서는 객체 리터럴 내부에서도 동적 생성 가능하다
    
    ```jsx
    const obj = {
    	[`${prefix}-${++i}`] : i;
    	[`${prefix}-${++i}`] : i;
    	[`${prefix}-${++i}`] : i;
    } // 이렇게도 가능!
    ```
    
    ____10.9.3 메서드 축약 표현
    
    ES6에서는 메서드를 정의할 때 function 키워드를 생략한 축약 표현 사용 가능! 
    
    **💡 문제**
    
    ```jsx
    [10장 객체 리터럴]
    
    다음 중 출력 결과가 제대로 나오지 않는 것은?
    
    var person = {
    	name: 'Kim'
    };
    ```
    
    ```jsx
    1. 
    	var key = 'age';
    	person[key] = 20;
    	console.log(person.age); // 20
    
    2. 
    	person.name = 'Lee';
    	console.log(person.name); //Lee
    
    3.
    	person.name = 'Choi';
    	console.log(person.[name]); //Choi
    
    4. 
    	delete person.gender;
    	console.log(person); //{name: 'Lee', age: 20}
    
    5.
    	let color = 'white';
    	person = {color}
    	console.log(person.color); // white
    ```
    
    **정답 (3)** 대괄호 표기법을 사용하는 경우 대괄호안의 프로퍼티 키는 반드시 따옴표로 감산 문자열이어야 한다. 아님 자바스크립트 엔진은 식별자로 해석한다.
    
- ☑️ **11장: 원시 값과 객체의 비교**
    
    **11.1 원시 값**
    
    **____11.1.1 변경 불가능한 값**
    
    - 원시 값은 변경 불가능한 값. 읽기 전용 값으로 변경 불가
    - 그렇다고 변수가 변경 불가능하다는 건 아님. 값이 변경 불가능할 뿐. 재할당으로 교체할 수 있어!
    - 상수는 재할당이 금지된 변수.
    
    → 원시값을 할당한 변수에 새로운 원시 값을 재할당하면, 새로운 메모리 공간을 확보하고 재할당한 원시 값을 저장한 후, 변수는 새롭게 재할당한 원시값을 가리킨다 (= 변수가 참조한 메모리 공간의 주소가 바뀜)
    
    ⇒ 값의 이러한 특성을 불변성이라고 함. 불변성을 갖는 원시 값을 할당한 변수는 재할당 이외에 변수 값을 변경할 수 있는 방법이 없다.
    
    **____11.1.2 문자열과 불변성**
    
    원시 값을 저장하려면 먼저 확보해야 하는 메모리 공간의 크기를 결정해야 한다. (문자열: 2바이트, 숫자 타입: 8바이트)
    
    - 원시 값인 문자열은 0개 이상의 문자로 이뤄진 집합을 말하며, 1개의 문자는 2바이트의 메모리 공간에 저장된다 → 문자열이 얼만큼 있냐에 따라 메모리 공간의 크기가 결정된다. 숫자는 무슨 숫자든 8바이트가 필요한 것에 비하면 말이다.
    - 자바스크립트의 문자열은 원시 타입이며, 변경 불가능하다.
    
    ```jsx
    var str = 'Hello';
    str = 'world'
    // 식별자 str은 문자열 'hello'를 가리키고 있다가 'world'를 가리키도록 변경된 것 뿐. 둘 다 메모리에 존재
    ```
    
    - 문자열의 한 문자를 변경해보자. 문자열은 **유사배열객체**면서 이터러블이므로 배열과 유사하게 각 문자에 접근할 수 있다. (유사배열객체: 배열처럼 인덱스로 프로퍼티 값에 접근할 수 있고 length 프로퍼티를 갖는 객체를 말함)
        
        ```jsx
        str[0] = 'S';
        ```
        
        → 변경안됨! 읽기전용값이라서
        
    
    **____11.1.3 값에 의한 전달**
    
    - **값에 의한 전달:** 변수에 원시 값을 갖는 변수를 할당하면 할당받는 변수에는 할당 되는 변수의 원시 값이 **복사되어** 전달된다. → 고로 원본 변수와 복사된 변수에 담긴 값은 다른 메모리 공간에 저장된 별개의 값이다. (서로 영향을 주지 않음)
    
    - 식별자는 메모리 주소에 붙인 이름. 메모리 주소를 통해 메모리 공간에 저장된 값에 접근함
    - “값에 의한 전달”도 사실은 값이 아니라 메모리 주소를 전달한다. 단, 전달된 메모리 주소를 통해 메모리 공간에 접근하면 값을 참조할 수 있다.
    - 어쨌든 서로 간섭 불가
    
    **11.2 객체**
    
    객체는 프로퍼티의 개수가 정해져 있지 않으며, 동적으로 추가되고 삭제할 수 있다.
    
    → 고로 사전에 메모리 공간의 크기를 정의할 수 없고, 관리하기도 복잡. 원시값과 다른 방식으로 동작하도록 설계되어있다.
    
    **____11.2.1 변경 가능한 값**
    
    - 객체는 변경 가능한 값이다.
    
    원시값을 할당한 변수는 원시값 자체를(메모리 주소를 통해) 값으로 갖는다.
    
    하지만 객체를 할당한 변수가 기억하는 메모리 주소를 통해 메모리 공간에 접근하면 **참조값**에 접근할 수 있다. **참조 값**은 생성된 객체가 저장된 **메모리 공간의 주소 그 자체다**.
    
    → 객체를 할당한 변수를 참조하면 메모리에 저장되어있는 참조값을 통해 실제 객체에 접근한다.
    
    - 원시값은 변경 불가능한 값이므로 변경하기 위해서는 재할당밖에 없다. 하지만 객체는 변경 가능! → 재할당 없이 프로퍼티를 동적으로 추가, 갱신, 삭제할 수 있다.
    
    - 그래서 부작용도 있음. 원시 값과는 다르게 여러 개의 식별자가 하나의 객체를 공유할 수 있다는 것.
    - 얕은 복사(한 단계만 복사)와 깊은 복사(중첩된 개체까지 복사)
    
    **____11.2.2 참조에 의한 전달**
    
    - **참조에 의한 전달**: 객체를 가리키는 변수를 다른 변수에 할당하면 원본의 참조값이 복사되어 전달된다.
    - 원본을 사본에 할당하면 원본의 참조값을 복사하여 copy에 저장한다. 이 때 원본과 사본의 메모리 주소는 다르지만 동일한 참조값을 갖는다. (동일한 객체를 가리키게 된다!) → 두개의 식별자가 하나의 객체를 공유하기 때문에, 서로 영향을 주고 받게 된다.
    
    💡 **문제** 
    
    ```jsx
    다음 중 설명이 옳지 않은 것은?
    
    1) 자바스크립트의 문자열은 원시타입으로 변경 불가능한 값이다.
    2) 문자열은 유사배열객체이기 때문에 배열처럼 인덱스로 프로퍼티 값에 접근할 수 있다. 그러나 값은 바꿀 수 없다.
    3) 식별자는 메모리 주소에 붙인 이름으로, 메모리 주소를 통해 메모리 공간에 저장된 값에 접근한다.
    4) 객체를 할당한 변수를 참조하면 메모리에 저장되어 있는 참조값을 통해 실제 객체에 접근한다.
    5) 객체를 가리키는 변수를 다른 변수에 할당하면 참조값을 복사하여 전달하기 때문에 원본과 사본의 메모리 주소는 같고 동일한 참조값을 갖는다. 
    ```
    
- ☑️ **12장: 함수**
    
    **12.1 함수란?**
    
    함수: 일련의 과정을 문으로 구현하고 코드 블록으로 감싸서 하나의 실행 단위로 정의한 것.
    
    - 매개변수: 함수 내부로 입력을 전달받는 변수
    - 인수: 입력
    - 반환값: 출력
    
    함수는 정의를 통해 생성한다. 그렇지만 정의만으로 함수가 실행되는 것은 아님. 값을 넣어서 함수의 실행을 명시적으로 지시해야. 이를 함수 호출이라 한다.
    
    **12.2 함수를 사용하는 이유**
    
    - 코드의 재사용이라는 측면에서 매우 유용.
    
    **12.3 함수 리터럴**
    
    - 함수는 객체 타입의 값. 함수도 함수 리터럴로 생성할 수 있다.
    
    ```jsx
    //변수에 함수 리터럴을 할당
    var f = **function** add (x, y) {
    		return x + y;
    };
    ```
    
    function이 함수 리터럴인건가…?
    
    리터럴은 값을 생성 하기 위한 표기법으로 함수 리터럴도 평가되어 값을 생성함 → **함수는 객체… 일반 객체는 호출할 수 없지만 함수는 호출할 수 있다.**
    
    **12.4 함수 정의**
    
    **정의된 함수**는 자바스크립트 엔진에 의해 평가되어 함수 객체가 된다. 함수를 정의하는 방법에는 4가지가 있다.
    
    - 함수선언문, 함수표현식, function 생성자 함수, 화살표 함수 (ES6)
    
    변수는 선언. 함수는 정의
    
    **____12.4.1 함수 선언문**
    
    ```jsx
    function add(x, y) {
    		return x + y;
    }
    ```
    
    함수 선언문은 함수 리터럴과 형태가 동일하다.
    
    **함수 리터럴은 함수 이름을 생략할 수 있지만 함수 선언문은 함수 이름을 생략할 수 없다.**
    
    **함수 선언문은 표현식이 아닌 문이다.**
    
    ```jsx
    var add = function add (x , y) {
    	return  x + y;
    };
    
    console.log(add(2, 5));
    ```
    
    표현식이 아닌 문은 변수에 할당할 수 없다. 그렇지만 함수 선언문이 변수에 할당되는 것처럼 보인다. 왜? → 자바스크립트 엔진이 코드의 문맥에 따라 동일한 함수 리터럴을 표현식이 아닌 문인 함수 선언문으로 해석하는 경우와 **표현식인 문인 함수 리터럴 표현식으로 해석하는 경우가 있기 때문이다.**
    
    함수 선언문으로 생성된 foo는 호출할 수 있으나 함수 리터럴 표현식으로 호출된 bar는 호출할 수 없다. why? 함수 리터럴에서 함수 이름은 함수 몸체 내에서만 참조할 수 있는 식별자라고 했다. 함수 몸체 외부에서는 함수 이름으로 함수를 참조할 수 없으므로 함수 몸체 외부에서는 함수 이름으로 함수를 호출할 수 없다는 의미. 
    
    근데 foo는 왜 돼? foo도 함수 몸체 내부에서만 유효한 식별자인 함수 잖아 → foo는 자바스크립트 엔진이 암묵적으로 생성한 식별자임! 
    
    **자바스크립트 엔진은 생성된 함수를 호출하기 위해 함수 이름과 동일한 이름의 식별자를 암묵적으로 생성하고, 거기에 함수 객체를 할당한다. /** 함수 이름과 변수이름이 일치하므로 함수 이름으로 호출되는 듯하지만 사실은 식별자로 호출된 것이다.
    
    **____12.4.2 함수 표현식**
    
    자바스크립트의 함수는 객체 타입의 값이다. 값의 성질을 갖는 객체를 일급 객체라고 하고 자바스크립트 함수는 일급 객체다. → 함수를 값처럼 자유롭게 사용할 수 있다.
    
    함수 리터럴로 생성한 함수 객체를 변수에 할당할 수 있다. 이러한 함수 정의방식을 함수 표현식이라고 한다.
    
    ```jsx
    var add = function foo (x , y) {
    	return  x + y;
    };
    
    console.log(add(2, 5));
    ```
    
    함수 리터럴의 함수 이름은 생략 가능. → 익명함수라고 부른다.
    
    함수를 호출할 때는 함수 이름이 아니라 함수 객체를 가리키는 식별자를 사용해야 한다. → `foo`가 아닌 `add`로 호출해야!
    
    **____12.4.3 함수 생성 시점과 함수 호이스팅**
    
    - 함수 선언문으로 정의한 함수는 함수 선언문 이전에 호출 가능. 그러나 함수 표현식으로 정의한 함수는 함수 표현식 이전에 호출 불가능
    
    why? 함수 선언문으로 정의한 함수와 표현식으로 정의한 함수의 생성 시점이 다르기 때문이다.
    
    → **함수 선언문은 런타임 이전에 먼저 실행된다**. 그리고 함수 이름고 동일한 이름의 식별자를 암묵적으로 생성하고, 생성된 함수 객체를 할당한다. (함수 표현식은 아님) ⇒ 이처럼 함수 선언문이 코드의 선두로 끌어올려진 것처럼 동작하는 자바스크립트 고유의 특징을 **함수 호이스팅**이라고 한다.
    
    - **함수 호이스팅 vs 변수 호이스팅**
    
    var 키워드로 선언된 변수는 undefined로 초기화되고, 함수 선언문을 통해 암묵적으로 생성된 식별자는 함수 객체로 초기화된다.
    
    변수 할당문의 값은 할당문이 실행되는 시점, 즉 런타임에 평가 되므로 함수 표현식의 함수 리터럴도 할당문이 실행되는 시점에 평가가 되어 함수 객체가 된다.
    
    → 따라서 함수 표현식으로 함수를 정의하면 함수 호이스팅이 발생하는 것이 아니라 변수 호이스팅이 발생한다. → ??? (165페이지 다시 읽기)
    
    함수 표현식 이전에 함수를 참조하면 undefined로 평가된다. 함수 표현식으로 정의한 함수는 함수 표현식 이후에 참조 또는 호출해야 한다.
    
    함수 호이스팅은 함수를 호출하기 전에 함수를 선언해야 한다는 당연한 규칙을 무시한다. → **고로 함수 선언문 대신 함수 표현식을 사용할 것을 권장한다!**
    
     
    
    **____12.4.4 Function 생성자 함수**
    
    빌트인 함수인 function 생성자 함수에 매개변수 목록과 함수 몸체를 문자열로 전달하면서 new 연산자와 함께 호출하면 함수 객체를 생성해서 반환한다. 사실 new 연산자 없이 호출해도 결과는 동일하다.
    
    ```jsx
    var add = new Funtion ('x', 'y', 'return x + y');
    console.log(add(2,5)); //7
    ```
    
    **Function 생성자 함수로 함수를 생성하는 방식은 일반적이지 않으며 바람직하지도 않다.** Function 생성자 함수로 생성한 함수는 클로저를 생성하지 않는 등, 함수 선언문이나 함수 표현식으로 생성한 함수와 다르게 동작한다.
    
    지금은 함수 선언문이나 함수 표현식으로 생성한 함수와 function 생성자 함수로 생성한 함수가 동일하게 동작하지 않는다는 데 주목하자.
    
    **____12.4.5 화살표 함수**
    function 키워드 대신 화살표를 사용해 좀 더 간략한 방법으로 함수를 선언할 수 있다. 화살표 함수는 항상 익명 함수로 정의한다.
    
    ```jsx
    const add = (x , y) => x + y;
    console.log(add(2,5)); // 7
    ```
    
    **12.5 함수 호출**
    
    함수는 함수를 가리키는 식별자와 한 쌍의 소괄호인 함수 호출 연산자로 호출한다.
    
    **____12.5.1 매개변수와 인수**
    
    ```jsx
    //함수 선언문
    function add(x, y) {
    		return x + y;
    }
    
    //함수 호출
    //인수 1과 2가 매개변수 x, y에 순서대로 할당되고 함수 몸체의 문들이 실행된다
    var result = add (1, 2);
    ```
    
    함수가 호출되면 함수 몸체 내에서 암묵적으로 매개변수가 생성되고 일반 변수와 마찬가지로 undefined로 초기화된 후 인수가 순서대로 할당된다. 매개변수 ← 인수
    
    매개변수는 함수 몸체 내부에서만 참조할 수 있다.
    
    함수는 매개변수의 개수와 인수의 개수가 일치하는지 체크하지 않는다 → 인수가 부족하더라도 오류가 안남
    
    매개변수보다 인수가 더 많은 경우 초과된 인수는 무시된다. 모든 인수는 암묵적으로 arguments 객체의 프로퍼티로 보관된다.
    
    **____12.5.2 인수 확인**
    
    함수를 정의할 때 적절한 인수가 전달되었는지 확인해야.
    
    그건 직접 확인해야함. 
    
    ```jsx
    function add (x, y)
    {
    		if (typeof x !== 'number' || typeof y !== 'number')
    				throw new TypeError ('인수는 모두 숫자값이어야 합니다.');
    		return x + y;
    }
    ```
    
    - 단축평가를 사용해 매개변수에 기본값을 할당
    
    ```jsx
    function add(a,b,c) {
    		a = a || 0;
    		b = b || 0;
    		c = c || 0;
    		return a + b + c;
    }
    ```
    
    - ES6에서 도입된 매개변수 기본값을 사용하면 함수 내에서 수행하던 인수체크 및 초기화를 간소화할 수 있다. 매개변수 기본값은 매개변수에 인수를 전달하지 않았을 경우와 undefined를 전달한 경우에만 유효하다.
    
    ```jsx
    function add (a=0, b=0, c=0)
    {
    	return a + b + c;
    }
    conosole.log(add(1+2+3)); //6
    conosole.log(add()); // 0
    ```
    
    **____12.5.3 매개변수의 최대 개수**
    
    함수의 매개변수는 코드를 이해하는데 방해되는 요소이므로 이상적인 매개변수 개수는 0개다. 적을수록 좋음
    
    이상적인 함수는 한 가지 일만 해야 하며 가급적 작게 만들어야 한다. (3개 이하를 권장)
    
    그 이상은 하나의 매개변수를 선언하고 객체를 인수로 적달하는 것이 유리하다.
    
    ```jsx
    $.ajax({
    	method: 'POST',
    	url: '/user',
    	data: { id: 1, name: 'Lee' },
    	cache: false
    });
    ```
    
    프로퍼티 키만 정확하면 매개변수 순서 신경쓰지 않음. 하지만 주의할 것은 함수 외부에서 함수 내부로 전달한 객체를 함수 내부에서 변경하면 함수 외부의 객체가 변경되는 **부수 효과**가 발생한다는 것이다.
    
    **____12.5.4 반환문 (return)**
    
    함수는 return 키워드와 표현식(반환값)으로 이뤄진 반환문을 사용해 실행 결과를 함수 외부로 반환할 수 있다.
    
    반환문의 두가지 역할
    
    1) 반환문은 함수의 실행을 중단하고 함수 몸체를 빠져나감
    
    2) return 키워드 뒤에 오는 표현식을 평가해 반환한다.
    
    표현식이 없으면 undefined 반환됨 `return ;`
    
    리턴 생략해도 undefined 반환됨
    
    **12.6 참조에 의한 전달과 외부 상태의 변경**
    
    원시 값을 전달받으면 값 자체가 복사되어 매개변수에 전달되기 때문에 원본은 훼손안됨.
    
    하지만 객체 타입 인수는 참조값이 복사되어 매개변수에 전달되기 때문에 함수 몸체에서 참조 값을 통해 객체를 변경할 경우 원본이 훼손된다.
    
    → 그렇기 때문에 객체는 언제든지 변할 수 있기때문에 객체의 변경을 추적하는 게 어려울 수도 있다. 
    
    이러한 문제의 해결방법 중 하나는 객체를 불변 객체로 만들어 사용하는 것이다. **객체의 복사본을 새롭게 생성하는 비용은 들지만 객체를 마치 원시값 처럼 변경 불가능한 값으로 동작하게 만드는 것이다.**
    
    → 객체의 상태 변경이 필요할 때에는 깊은 복사를 통해 새로운 객체를 생성하고 재할당을 통해 교체한다. 
    
    외부 상태를 변경하지 않고 외부 상태에 의존하지도 않는 함수를 순수 함수라 한다.
    
    **12.7 다양한 함수의 형태**
    
    **____12.7.1 즉시 실행 함수**
    
    - 함수 정의와 동시에 즉시 호출되는 함수
    - 단 한번만 호출되며 다시 호출할 수 없다.
    
    ```c
    //익명 즉시 실행 함수
    (function () {
    	var a = 3;
    	var b = 5;
    	return a * b;
    }**()**);
    ```
    
    - 즉시 실행 함수는 함수 이름이 없는 익명 함수를 사용하는 것이 일반적. 물론 기명 함수도 가능
        
        그룹 연산자 (…) 내의 기명 함수는 함수 선언문이 아니라 함수 리터럴로 평가 되며 함수 이름은 함수 몸체에서만 참조할 수 있는 식별자이므로 즉시 실행 함수를 다시 호출할 수는 없다.
        
    - 즉시 실행 함수는 반드시 그룹 연산자로 감싸야 한다.
        
        ```c
        function () {
        	...
        }();
        ```
        
        **함수 선언문은 함수 이름을 생략할 수 없다.**
        
        ```c
        function foo() {
        	...
        }();
        ```
        
        그렇지만 이름 붙여준다고 오류가 안나는 거 아님. 에러 생김. 왜냐면 함수 코드 블록 뒤에 자동으로 ;이 추가되기 때문. 그 뒤의 ()는 함수 호출이 아닌 그룹 연산자로 해석됨
        
        ```c
        console.log(typeof (function f(){})); //function
        console.log(typeof (function (){})); //function
        ```
        
        → 따라서 그룹 연산자로 묶은 이유 ⇒ 함수 리터럴을 평가해서 함수 객체를 생성하기 위해서. 
        
        함수 리터럴을 평가해서 함수 객체를 생성할 수 있다면 그룹 연산자 이외의 연산자 (! + 등)를 사용해도 됨
        
        - 즉시 실행 함수도 일반 함처럼 값을 반환할 수도 있고 인수를 전달할 수도 있다.
        
    
    **____12.7.2 재귀 함수**
    
    ```c
    function factorial(n) {
    	if (n <= 1) return 1;
    	return n * factorial(n - 1);
    }
    
    ```
    
    ```c
    var factorial = function foo(n) {
    	if (n <= 1) return 1;
    	return n * factorial(n - 1);
    }
    
    conosole.log(factorial(5));
    ```
    
    외부에서 함수를 호출할 때는 반드시 함수를 가리키는 식별자로 해야한다.
    
    - 탈출 조건을 만들어야 한다.
    - 대부분의 재귀함수는 for문이나 while문으로 구현 가능하다
    
    **____12.7.3 중첩 함수**
    
    중첩 함수 또는 내부 함수: 함수 내부에 정의된 함수
    
    외부 함수: 중첩 함수를 포함하는 함수
    
    **____12.7.4 콜백 함수**
    
    반복하는 건 변하지 않은데 반복하면서 하는 일이 다른 두 함수의 경우, 둘을 합성하자
    
    **→ 함수의 변하지 않는 공통 로직은 미리 정의해두고 경우에 따라 변경되는 로직은 추상화해서 함수 외부에서 함수 내부로 전달하자!**
    
    ```jsx
    function repeat(n, f){
    	for (var i = 0; i < n; i++){
    		f(i);
    	}
    }
    
    var logAll = function (i) {
    	console.log(i);
    };
    
    //반복 호출할 함수를 인수로 전달한다
    repeat(5, logAll); // 0 1 2 3 4
    ```
    
    - 이처럼 함수의 매개변수를 통해 다른 함수의 내부로 전달되는 함수를 **콜백 함수**라고 한다. (여기선 logAll?)
    - 매개 변수를 통해 함수의 외부에서 콜백 함수를 전달받은 함수를 **고차함수**라고 한다. (여기선 repeat?)
    
    → 중첩 함수와 비슷하지만, 콜백 함수는 함수 외부에서 고차 함수 내부로 주입하기 때문에 자유롭게 교체할 수 있다는 장점이 있다.
    
    콜백 함수가 고차 함수 내부에만 호출된다면 콜백 함수를 익명 함수 리터럴로 정의하면서 곧바로 고차 함수에 전달하는 것이 일반적이다.
    
    ```jsx
    repeat(5, function(i) {
    	if (i % 2) console.log(i);
    }; // 1 3
    ```
    
    ```jsx
    var logOdds = function (i) {
    	if (i % 2) console.log(i);
    };
    
    repeat(5, logOdds); // 1 3
    ```
    
    **____12.7.5 순수 함수와 비순수 함수**
    
    순수함수: 최소 하나 이상의 인수를 전달 받는다. 외부 상태를 변경하지 않는다
    
    비순수함수: 인수를 전달받지 않고 함수 내부에서 외부 상태를 직접 참조한다. 외부 상태에 따라 반환값이 달라진다. 외부 상태를 변경한다. → 추적하기 어렵다.
    
    **💡 문제**
    
    ```jsx
    다음 주 아래의 함수에 대한 설명을 옳지 않은 것은?
    
    var div2 = function foo (x , y) {
    	return  x / y;
    };
    
    -
    
    1) 함수 리터럴로 생성한 함수 객체를 변수에 할당하는 함수 표현식 방식으로 함수를 정의했다.
    2) console.log(foo(10, 2))의 결과는 5이다
    3) 함수 리터럴의 함수 이름은 생략 가능하기 때문에 아래와 같은 함수도 가능하다.
    		var div2 = function (x , y) {
    			return  x / y;
    		};
    4) 함수 선언문의 함수 이름은 생략할 수 없기 때문에 다음과 같은 함수는 불가능하다
    		function (x , y) {
    			return  x / y;
    		};
    5) 위 함수를 화살표 함수로 표현하면 다음과 같이 표현할 수 있다.
    		const div2 = (x , y) => x / y;
    ```
    
    **정답(2)** 함수를 호출할 때는 함수 이름이 아니라 함수 객체를 가리키는 식별자를 사용해야 한다. → `foo`가 아닌 `div2`로 호출해야!
    
- ☑️ **13장: 스코프**
    
    **13.1 스코프란?**
    
    - 스코프: 모든 식별자(변수 이름, 함수 이름, 클래스 이름 등)는 자신이 선언된 위치에 의해 다른 코드가 식별자 자신을 참조할 수 있는 유효 범위가 결정된다.
    - 스코프란 자바스크립트 엔진이 식별자를 검색할 때 사용하는 규칙.
    - var 키워드로 선언된 변수는 같은 스코프 내에서 중복 선언이 허용된다. (let이나 const는 아님)
    
    **13.2 스코프의 종류**
    
    **____13.2.1 전역과 전역 스코프**
    
    전역 변수: 어디서든지 참조할 수 있다. (전역이란 코드의 가장 바깥 영역)
    
    **____13.2.2 지역과 지역 스코프**
    
    지역 변수: 자신의 지역 스코프와 하위 지역 스코프에서 유효 (지역이란 함수 몸체 내부)
    
    **13.3 스코프 체인**
    
    함수는 중첩될 수 있으므로 함수의 지역 스코프도 중첩될 수 있다.
    
    → 스코프가 함수의 중첩에 의해 계층적 구조를 갖는다는 것을 의미한다.
    
    스코프가 계층적으로 연결된 것을 스코프 체인이라고 한다.
    
    → 변수를 참조할 때 자바스크립트 엔진은 스코프 체인을 통해 변수를 참조하는 코드의 스코프에서 시작하여 상위 스코프 방향으로 이동하며 선언된 변수를 검색한다.
    
    **____13.3.1 스코프 체인에 의한 변수 검색**
    
    상위 스코프에서 유효한 변수는 하위 스코프에서 자유롭게 참조할 수 있지만 하위 스코프에서 유효한 변수를 상위 스코프에서 참조할 수 없다.
    
    **____13.3.2 스코프 체인에 의한 함수 검색**
    
    스코프: “식별자를 검색하는 규칙”
    
    **13.4 함수 레벨 스코프**
    
    코드 블록이 아닌 **함수에 의해서만** 지역 스코프가 생성된다.
    
    c나 자바 등 대부분 프로그래밍 언어는 함수 몸체 뿐만 아니라 모든 코드 블록(if, for, while 등)은 지역 스코프를 만든다. → **블록 레벨 스코프**라고 부른다.
    
    var 키워드로 선언된 변수는 오로지 함수의 코드블록 (함수 몸체)만을 지역 스코프로 인정한다. → **함수 레벨 스코프**라 부른다.
    
    - var 키워드로 선언된 변수는 함수 레벨 스코프만 인정하기 때문에 함수 밖에서 var 키워드로 선언된 변수는 코드 블록 내에서 선언되었다 할지라도 모두 전역 변수다.
    - 블록 레벨 스코프에서는 for문에서 선언된 i 변수가 for문 안에서만 유효함
    
    하지만 var 키워드로 선언된 변수는 블록 레벨 스코프 인정 안하기 때문에 i 변수는 전역 변수가 된다. const와 let은 블록레벨 스코프 지원함!
    
    **13.5 렉시컬 스코프**
    
    동적스코프: 함수를 정의하는 시점에는 함수가 어디서 호출될지 알수 없으니 호출되는 시점에 동적으로 상위 스코프 정함
    
    렉시컬 스코프 or 정적 스코프: 함수 정의가 평가되는 시점에 상위 스코프가 정적으로 결정
    
    **→ 자바스크립트는 렉시컬 스코프를 따르므로 함수를 어디서 호출했는지가 아니라 함수를 어디서 정의했는지에 따라 상위 스코프를 결정한다.**
    
    ```jsx
    var x = 1;
    
    function foo() {
    	var x = 10;
    	**bar ();**
    }
    
    function bar() {
    	console.log(x);
    }
    
    **foo(); //1**
    **bar(); //1**
    ```
    
    💡**문제**
    
    ```jsx
    다음 중 설명이 옳지 않은 것은?
    
    1) 스코프란 자바스크립트 엔진이 식별자를 검색할 때 사용하는 규칙이다.
    2) var 키워드로 선언된 변수는 같은 스코프 내에서 중복 선언이 허용된다.
    3) var 키워드는 함수 레벨 스코프만 인정하기 때문에 var 키워드로 선언된 변수는 코드 블록 내에서 선언되었을지라도 모두 전역변수다
    4) const와 let은 블록 레벨 스코프를 지원하기 때문에 const와 let으로 선언된 변수는 코드 블록 내에서만 유효하다
    5) 자바스크립트는 렉시컬 스코프를 따르므로 함수를 어디서 호출했는지에 따라 상위 스코프를 결정한다.
    ```
    
- ☑️ **14장: 전역 변수의 문제점**
    
    **14.1 변수의 생명 주기**
    
    **____14.1.1 지역 변수의 생명 주기**
    
    함수 내부에서 선언된 지역 변수는 함수가 호출되면 생성되고 함수가 종료하면 소멸한다.
    
    지역 변수의 생명 주기는 함수의 생명 주기와 일치한다.
    
    **변수의 생명 주기**: 메모리 공간이 확보된 시점부터 메모리 공간이 해제되어 가용 메모리 풀에 반환되는 시점까지다. → 누군가가 스코프를 참조하고 있으면 스코프는 소멸하지 않고 생존하게 된다. 일반적으로 함수가 종료되면 함수가 생성한 스코프 소멸한다. 하지만 누군가가 스코프를 참조하고 있다면 스코프는 해제되지 않고 생존하게 된다.
    
    ```jsx
    var x = 'global';
    
    function foo() {
    		console.log(x);
    		var x = 'local';
    }
    
    foo(); //undefined
    console.log(x); //global
    ```
    
    foo 함수 내부에서 선언된 지역 변수 x는 (1)의 시점에 이미 선언되었고 undefined로 초기화되어있다.
    
    호이스팅은 스코프를 단위로 동작한다. 전역 변수의 호이스팅은 전역 변수의 선언이 전역 스코프의 선두로 끌어올려진 것처럼 동작한다. 지역 변수의 호이스팅은 지역 변수의 선언이 지역 스코프의 선두로 끌어올려진 것처럼 동작한다.
    
    **즉, 호이스팅은 변수 선언이 스코프의 선두로 끌어올려진 것처럼 동작하는 자바스크립트 고유의 특징을 말한다.**
    
    **____14.1.2 전역 변수의 생명 주기**
    
    var 키워드로 선언한 지역 변수는 전역 객체의 프로퍼티가 된다 (= 전역 변수의 생명 주기가 전역 객체의 생명 주기와 일치한다)
    
    *전역 객체는 코드가 실행되기 이전 단계에 자바스크립트 엔진에 의해 어떤 객체보다도 먼저 생성되는 특수한 객체다. 전역 객체는 표준 빌트인 객체와 환경에 따른 호스트 객체, 그리고 var 키워드로 선언한 전역 변수와 전역 함수를 프로퍼티로 갖는다.
    
    **14.2 전역 변수의 문제점**
    
    - 암묵적 결합: 모든 코드가 전역 변수를 참고하고 변경할 수 있음.
    - 긴 생명 주기
    - 스코프 체인 상에서 종점에 존재  (전역 변수가 가장 마지막에 검색됨)
    - 네임 스페이스 오염
    
    **14.3 전역 변수의 사용을 억제하는 방법**
    
    무분별한 전역 변수 남발은 금지
    
    **____14.3.1 즉시 실행 함수**
    
    - 함수 정의와 동시에 호출되는 즉시 실행함수는 단한번만 호출된다. 모든 코드를 즉시 실행감수로 감싸면 모든 변수는 실행 즉시 실행함수의 지역 변수가 된다.
    
    ```jsx
    **(**function (){
    	var foo = 10;
    	//...
    }**())**;
    ```
    
    **____14.3.2 네임스페이스 객체**
    
    ```jsx
    var MYAPP = {};
    
    MYAPP.name = 'Lee';
    
    console.log(MYAPP.name); //Lee
    ```
    
    - 전역에 네임스페이스 역할을 담당할 객체를 생성하고 전역 변수처럼 사용하고 싶은 변수를 프로퍼티로 추가하는 방법
    - 네임스페이스 객체에 또다른 네임스페이스 객체를 프로퍼티로 추가하기 가능
    
    → 네임 스페이스 객체 자체가 전역 변수에 할당되므로 그다지 유용해보이지 않는다…?
    
    **____14.3.3 모듈 패턴**
    
    모듈 패턴은 클래스를 모방해서 관련이 있는 변수와 함수를 모아 즉시 실행 함수로 감싸 하나의 모듈을 만든다. 모듈 패턴은 자바스크립트의 강력한 기능인 클로저를 기반으로 동작한다. 모듈 패턴의 특징은 전역 변수의 억제는 물론 캡슐화 까지 구현할 수 있다는 것이다.
    
    클로저라는 기능을 통해 전역 변수를 억제할 수 있다?
    
    캡슐화는 객체의 상태를 나타내는 프로퍼티와 프로퍼티를 참조하고 조작할 수 있는 동작인 메서드를 하나로 묶는 것을 말한다. 대부분의 객체 지향 프로그래밍 언어는 클래스를 구성하는 멤버에 대해 public, private, protected 등의 접근 제한자를 사용해 공개 범위를 한정할 수 있다.
    
    → 하지만 자바스크립트는 저런 접근 제한자를 제ㅔ공하지 않는다. 모듈 패턴은 전역 네임 스페이스의 오염을 막는 기능은 물론 한정적이기는 하지만 정보 은닉을 구현하기 위해 사용된다.
    
    ```jsx
    var Counter = (function () {
    	//private 변수
    	var num = 0;
    
    	//외부로 공개할 데이터나 메서드를 프로퍼티로 추가한 객체를 반환한다.
    	return {
    		increase() {
    			return ++num;
    		},
    		decrease() {
    			return --num;
    		}
    }());
    
    //private 변수는 외부로 노출되지 않음
    //Counter.num은 안나옴, Counter.increase... 이런건 나옴
    ```
    
    **____14.3.4 ES6 모듈**
    
    ES6 모듈을 사용하면 더는 전역 변수 사용 못한다. 얘네는 파일 자체의 독자적인 모듈 스코프를 제공한다. → 따라서 모듈 내에서 var 키워드로 선언한 변수는 더는 전역 변수가 아니며 window 객체의 프로퍼티도 아니다.
    
    script 태그에 type=”module” 어트리뷰트를 추가하면 로드된 자바스크립트 파일은 모듈로서 동작한다. 모듈의 파일 확장자는 mjs를 권장
    
    ```jsx
    <script type="module" src="lib.mjs"></script>
    <script type="module" src="app.mjs"></script>
    ```
    
    💡 **문제**
    
    ```jsx
    다음 중 옳지 않은 것은?
    
    1) 지역 변수의 생명 주기는 함수의 생명 주기와 일치한다. 
    
    2) 
    var x = 'first';
    
    function foo() {
    		console.log(x);
    		var x = 'second';
    		console.log(x);
    }
    
    foo(); // undefined second
    
    위와 같은 현상이 일어나는 이유는 호이스팅 때문이다.
    
    3) 전역 변수의 사용을 억제하는 방법으로는 즉시 실행 함수, 네임 스페이스 객체, 모듈 패턴이 있다.
    
    4) ES6 모듈을 사용해도 전역 변수는 사용할 수 있다.
    
    ```
    
- ☑️ **15장: let, const 키워드와 블록 레벨 스코프**
    
    **15.1 var 키워드로 선언한 변수의 문제점**
    
    **____15.1.1 변수 중복 선언 허용**
    
    var 키워드로 선언한 변수는 중복 선언이 가능
    
    초기화문이 있는 변수 선언문은 자바스크립트 엔진에 의해 var 키워드가 없는 것처럼 동작한다.
    
    **____15.1.2 함수 레벨 스코프**
    
    var 키워드로 선언한 변수는 오로지 함수의 코드 블록만을 지역 스코프로 인정한다. 따라서 함수 외부에서 var 키워드로 선어한 변수는 코드 블록 내에서 선언해도 모두 전역 변수가 된다.
    
    **____15.1.3 변수 호이스팅**
    
    var 키워드로 변수를 선언하면 변수 호이스팅에 의해 변수 선언문이 스코프의 선두로 끌어올려진 것처럼 동작한다.
    
    ```jsx
    console.log (foo); //undefined
    
    foo = 123;
    
    console.log(foo); // 123
    
    var foo;
    ```
    
    그치만 선언문 이전에 변수 참조하는 이런 짓은 가급적 하지말자…
    
    **15.2 let 키워드**
    
    **____15.2.1 변수 중복 선언 금지**
    
    let 키워드로 변수 중복으로 선언하면 문법 에러 생김
    
    **____15.2.2 블록 레벨 스코프**
    
    코드블록 내에 선언된 foo 변수와 bar 변수는 지역 변수다.
    
    **____15.2.3 변수 호이스팅**
    
    let 키워드로 선언한 변수는 변수 호이스팅이 발생하지 않는 것처럼 보임. 
    
    var 키워드로 선언한 변수는 런타임 이전에 자바스크립트 엔진에 의해 암묵적으로 “선언단계”와 “초기화 단계”가 한번에 진행된다.
    
    하지만 let 키워드로 선언한 변수는 “선언단계”와 “초기화단계”가 분리되어 진행한다. 즉, 선언은 런타임 전에 하지만 초기화는 변수 선언문을 만났을 때 초기화가 되기 때문에 초기화 이전의 **일시적 사각지대**에서 변수는 참조할 수 없다. 
    
    ```jsx
    console.log(foo); // error
    let foo; // 초기화
    console.log(foo); //undefined
    foo = 1;
    console.log(foo); // 1
    ```
    
    ```jsx
    let foo = 1; // 전역변수
    {
    	console.log(foo); // error
    	let foo = 2; // 지역변수
    }
    ```
    
    let 키워드로 선언한 변수의 경우 변수 호이스팅이 발생하지 않는다면 위 예제는 foo의 값을 출력해야 한다. 하지만 let 키워드로 선언한 변수도 여전히 호이스팅이 발생하기 때문에 참조 에러 생김(???
    
    자바스크립트는 모든 선언을 호이스팅한다. 하지만 es6에서 도입된 let, const, class를 사용한 선언문은 호이스팅이 발생하지 않는 것처럼 동작한다.
    
    **____15.2.4 전역 객체와 let**
    
    var 키워드로 선언한 전역 변수와 전역 함수, 그리고 선언하지 않은 변수에 값을 할당한 암묵적 전역은 전역 객체 window의 프로퍼티가 된다. 
    
    ```jsx
    var x = 1; //전역변수
    y = 2 // 암묵적 전역
    
    console.log(window.x) // 1
    console.log(x) // 1
    ```
    
    let 키워드로 선언한 전역 변수는 전역 객체의 프로퍼티가 아니므로 window.x와 같이 접근 불가
    
    **15.3 const 키워드**
    
    **____15.3.1 선언과 초기화**
    
    const로 선언한 변수는 **반드시 선언과 동시에 초기화 해야한다**.
    
    블록 레벨 스코프 가지고, 변수 호이스팅이 발생하지 않는 것처럼 동작
    
    **____15.3.2 재할당 금지**
    
    **____15.3.3 상수**
    
    상수는 재할당이 금지된 변수. 일반적으로 상수의 이름은 대문자로 선언. 여러 단어로 이뤄져있을 경우 언더스코어(_)로 구분.
    
    **____15.3.4 const 키워드와 객체**
    
    const에 원시값을 할당한 경우 값을 변경 불가능하지만, const 키워드로 선언된 변수에 **객체를 할당한 경우 값을 변경할 수 있다.**
    
    ```jsx
    const person = {
    	name: 'Lee'
    };
    
    person.name = 'Kim';
    console.log(person); // {name: "Kim"}
    ```
    
    const 키워드는 재할당을 금지할 뿐 불변을 의미하는 것은 아니다!
    
    **15.4 var vs. let vs. const**
    
    es6에선 var를 쓰지말자
    
    재할당이 필요한 경우에만 let을 활용
    
    const 키워드를 기본적으로 사용하자
    
    💡 문제
    
    ```jsx
    다음 중 옳지 않은 것은?
    
    1) 
    console.log(a); //undefined
    a = 'a';
    console.log(a); // a
    var a;
    
    2) 
    console.log(a); //ReferenceError
    a = 'a';
    console.log(a);
    let a;
    
    3)
    let a = 'a'; //ReferenceError
    {
    	console.log(a); 
    	let a = 'b';
    }
    
    4) const로 선언한 변수는 반드시 선언과 동시에 초기화 해야한다.
    5) var, const, let로 선언한 변수는 객체 window의 프로퍼티가 된다.
    ```
    

---

- Json.parse(Json.stringify());
- Scope가 생기면 리턴 써줘야. 객체를 리턴하려면 ({}) 이렇게
- 명시가 안되어있으므로 전역변수가 됨 (지역스코프에 있어도) (b = 0)
- 모듈에서의 전역변수…?
- const에 값을 추가 빼는 건 됨.