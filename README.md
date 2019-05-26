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

## 1) calc()
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

## 1-1) Vendor prefix : cross browsing
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
