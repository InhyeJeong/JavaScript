# JavaScript-Study
* JavaScript study
* Code Review study

# 1. Promise()

* 동기적 호출 : 순서대로 실행
* 비동기적 호출 : 코드읽을 때 순서를 헷갈릴 수 있음
* promise는 then()으로 콜백을 연결한다. then()은 promise(resolve, reject)를 return함.
* 연결된 다음 then() 콜백함수가 실행되었다는 것은 앞의 리턴된 프로미스가 resolve가 되었다는 뜻!
* **비동기적 프로세스를 동기적 프로세스로 변환시킨다.**
---------------------
* 동기적 및 비동기적 호출 : https://www.youtube.com/watch?v=j0Viy3v97gY
* Promise() : https://www.youtube.com/watch?v=CA5EDD4Hjz4

# 2. 가변영역 고정영역 함께 사용하는 레이아웃

<p align="center">
<img src="./image/1.PNG" width="1000" >	
</p>

## 1) calc() : https://developer.mozilla.org/ko/docs/Web/CSS/calc
* 가변영역에 calc() 적용

```css
.main {
  width: calc(100% - 300px);
}
```

* 가로배치

```css
.main, .side {
  float: left;
}
```

## 1-1) Vendor prefix : Cross Browsing
* chrome : -webkit-
* firefox : -moz-
* opera : -o-
* IE : -ms-

## 2) table-layout
* 부모 영역

```css
.wrapper {
  display: table;
  width: 100%
}
```

* 자식 영역

```css
.main, .side {
  display: table-cell
}
```

## 3) flex-box
* 부모영역

```css
.wrapper {
  display: flex;
}
```
---------------------
* 가변영역 고정영역 함께 사용하는 레이아웃(calc, flex, display) : https://www.youtube.com/watch?v=RthnACwgqr8

# 3. Object Type

* 자바스크립트의 객체 개념은 생성 방법이나 상속 방식 등에서 C++이나 자바와 같은 기존 객체지향 언어에서의 객체 개념과는 약간 다르다. 자바에서는 클래스를 정의하고, 클래스의 인스턴스를 생성하는 과정에서 객체가 만들어진다. 이에 비해 자바스크립트에서는 **클래스라는 개념이 없고, 객체 리터럴이나 생성자 함수** 등 **별도의 생성 방식**이 존재한다.

## 1) Object() 생성자 함수

```javascript
//  Object()사용하여 빈 객체 생성
var foo = new Object();

//  foo 객체 프로퍼티 생성
foo.name = 'name'
foo.age = 30
foo.gender = 'male'

console.log(type of foo) // object
console.log(foo)  //  { name: 'name', age: 30, gender: 'male' }
```

## 2) 객체 리터럴 방식

* 리터럴이란 객체를 생성하는 표기법

```javascript
//  객체 리터럴 방식으로 빈 객체 생성
var foo = {
  name: 'name',
  age: 30,
  gender: 'male'
}

//  foo 객체 프로퍼티 생성
foo.name = 'name'
foo.age = 30
foo.gender = 'male'

console.log(type of foo) // object
console.log(foo)  //  { name: 'name', age: 30, gender: 'male' }
```

## 2) 생성자 함수 이용

* 함수도 객체다.
* 자바스크립트에서는 함수를 **일급 객체(First Class)** 라고 부른다.

```javascript
//  함수 선언 방식으로 add() 함수 정의
function add(x, y) {
  return x + y
}

//  add() 함수 객체에 result, status 프로퍼티 추가
add.result = add(3,2)
add.status = 'ok'

console.log(add.result) //  5
console.log(add.status)  // 'ok'
```

# 4. Function

## 1) arguments 객체

* 매개변수 개수가 정확하게 정해지지 않은 함수를 구현하거나, 전달된 인자의 개수에 따라 서로 다른 처리를 해줘야 하는 함수에 유용

```javascript
function sum() {
  var result = 0
  
  for (var i = 0; i < arguments.length; i++){
    result += arguments[i]
  }
  return result
}

console.log(sum(1, 2, 3)) //  6
console.log(sum(1, 2, 3, 4, 5, 6, 7, 8, 9, 10)) //  45
```


