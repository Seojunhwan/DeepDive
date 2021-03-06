# Ch4. λ³μ

<br/>

## π λ³μ(variable)

νλμ κ°μ μ μ₯νκΈ° μν΄ νλ³΄ν λ©λͺ¨λ¦¬ κ³΅κ° μμ²΄ λλ κ·Έ λ©λͺ¨λ¦¬ κ³΅κ°μ μλ³νκΈ° μν΄ λΆμΈ μ΄λ¦ β κ°μ μμΉλ₯Ό κ°λ¦¬ν€λ μμ§μ μΈ μ΄λ¦    
<br/>
<br/>


## πΒ var, let, const

### var

- λ³μλ₯Ό μ¬ μ μΈν΄λ μλ¬κ° λ°μνμ§ μλλ€.

```jsx
var name = 'hello'
console.log(name) // hello

var name = 'javascript'
console.log(name) // javascript
```
<br/>

### let

- λ³μλ₯Ό μ¬ μ μΈνλ©΄ μλ¬ λ©μΈμ§κ° λμ¨λ€.

```jsx
let name = 'hello'
console.log(name) // hello

let name = 'javascript'
console.log(name) 
// Uncaught SyntaxError: Identifier 'name' has already been declared
```

<br/>

### const

- λ³μ μ¬μ μΈ, μ¬ν λΉ λͺ¨λ λΆκ°λ₯νλ€.

```jsx
const name = 'hello'
console.log(name) // hello

const name = 'javascript'
console.log(name) 
// Uncaught SyntaxError: Identifier 'name' has already been declared

name = 'react'
console.log(name) 
// Uncaught TypeError: Assignment to constant variable.
```

- λ°λμ μ μΈκ³Ό μ΄κΈ°νκ° λμμ μ§νλμ΄μΌ νλ€.

```jsx
const name; 
// output: Uncaught SyntaxError: Missing initializer in const declaration
const name = 'javascript';
```

<br/>
<br/>

## πΒ ****μ€μ½ν (Scope)****

μ€μ½νλ μ ν¨ν μ°Έμ‘° λ²μλ₯Ό λ»νλ©°, κΈ°μ‘΄μ λ°©λ²μΈ var λ‘ μ μΈν λ³μμ let λλ const λ‘ μ μΈν λ³μμ μ€μ½νλ λ€λ¦.

<br/>

### ****1. var : ν¨μ λ λ²¨ μ€μ½ν (function-level scope)****

```jsx
function func() {
	if (true) {
    	var a = 5;
        console.log(a); // 5
    }
    console.log(a); // 5
}

func(); // 5
console.log(a); // ReferenceError: a is not defined
```

ν¨μ λ΄μμ μ μΈλ λ³μλ ν¨μ λ΄μμλ§ μ ν¨νλ©° ν¨μ μΈλΆμμλ μ°Έμ‘°ν  μ μμ. μ¦, ν¨μ λ΄λΆμμ μ μΈν λ³μλ μ§μ­ λ³μμ΄κ³  ν¨μ μΈλΆμμ μ μΈν λ³μλ λͺ¨λ μ μ­ λ³μλ‘ μ·¨κΈλ¨.

<br/>
<br/>

### ****2. let, const : λΈλ‘ λ λ²¨ μ€μ½ν (block-level scope)****

```jsx
function func() {
	if (true) {
    	let a = 5;
        console.log(a); // 5
    }
    console.log(a); // ReferenceError: a is not defined
}

console.log(a); // ReferenceError: a is not defined
```

ν¨μ, ifλ¬Έ, forλ¬Έ, whileλ¬Έ, try/catchλ¬Έ λ±μ λͺ¨λ  μ½λ λΈλ‘ ({...}) λ΄λΆμμ μ μΈλ λ³μλ μ½λ λΈλ‘ λ΄μμλ§ μ ν¨νλ©° μ½λ λΈλ‘ μΈλΆμμλ μ°Έμ‘°ν  μ μμ. μ¦, μ½λ λΈλ‘ λ΄λΆμμ μ μΈν λ³μλ μ§μ­ λ³μλ‘ μ·¨κΈλ¨.

<br/>
<br/>

πΒ  μ°Έκ³ 

[https://velog.io/@bathingape/JavaScript-var-let-const-μ°¨μ΄μ ](https://velog.io/@bathingape/JavaScript-var-let-const-%EC%B0%A8%EC%9D%B4%EC%A0%90)

[https://80000coding.oopy.io/e17. 1710-536f-43f2-823b-663389f5fbfa](https://80000coding.oopy.io/e1721710-536f-43f2-823b-663389f5fbfa)

<br/>
<br/>

## π‘Β μ°μ΅λ¬Έμ 

**1. μλ μ½λ μ€νμμ μΆλ ₯λλ κ°κ³Ό κ·Έ κ°μ΄ μΆλ ₯λλ μ΄μ λ?**

```jsx
console.log(score);
var score;
```

<br/>


**2. μλ μλ³μ μ΄λ¦λ€ μ€ μ¬μ©ν  μ μλ μλ³μ μ΄λ¦μ?**

```
var person;
var first_name;
var this;
var FIRSTNAME;
var 42seoul;
var #sjo;
```

<br/>

**3. μλ λ μ½λμ μ€νκ²°κ³Όλ? (var, letμ μ°¨μ΄)**

```jsx
function func() {
	if (true) {
    	var a = 5;
    }
    console.log(a); 
}

func(); 
```

```jsx
function func() {
	if (true) {
    	let a = 5;
    }
    console.log(a);
}

func(); 
```

<br/>

# Ch5. ννμκ³Ό λ¬Έ

<br/>

**π‘ κ°,Β λ¦¬ν°λ΄, ννμ, λ¬Έμ μ€λͺνμμ€.**

<br/>

# Ch6. λ°μ΄ν° νμ

<br/>

**π‘ undefinedμ nullμ μ°¨μ΄λ λ¬΄μμΈκ°? undefined μ undeclaredμ μ°¨μ΄λ λ¬΄μμΈκ°?**

<br/>

# Ch7. μ°μ°μ

<br/>

**π‘Β μλ μ½λ μ€ν μ κ²°κ³Όκ°μ μμν΄λ³΄μΈμ.**

```jsx
var x = 1;

console.log(x++); 

console.log(++x);

console.log(x--);

var y = true;

console.log(+y);

console.log(y);

console.log(NaN === NaN);
```
<br/>

# Ch8. μ μ΄λ¬Έ

<br/>

**π‘Β 1λΆν° 100κΉμ§ 100λ² λ°λ³΅λλ λ°λ³΅λ¬Έμ΄ μμ΅λλ€. 3μ λ°°μμΌ λλΒ fizz, 5μ λ°°μμΌ λλΒ buzz, 3κ³Ό 5μ κ³΅λ°°μμΌ λλΒ fizzbuzzκ° μΆλ ₯λλ μ½λλ₯Ό μμ±ν΄λ³΄μΈμ. (for loop, while loop μ΄μ©)**

<br/>

# Ch9. νμ λ³νκ³Ό λ¨μΆ νκ°

<br/>

**π‘Β λͺμμ  νμλ³ν, μλ¬΅μ  νμλ³ν λ κ°μ§λ₯Ό μ΄μ©νμ¬ var x = 10; μ λ¬Έμμ΄ ννλ‘ λ³νν΄ λ³΄μμ€.**

<br/>

**π‘Β μ΅μλ μ²΄μ΄λ μ°μ°μμ null λ³ν© μ°μ°μμ λν΄ μ€λͺνμμ€.**


