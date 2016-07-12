Javascript 기초
====
게임 프로그래밍과 연관이 있을 정도 수준의 자바스크립트에 대해서 설명합니다.

배열 다루기
----
`[]`를 사용해 배열을 만들 수 있습니다.
```js
var ary = [1, 2, 3, 4];
```
`length`는 배열의 크기를 가져옵니다.
```js
console.log(ary.length); // 4
```
`push`는 이미 만들어진 배열의 __끝__에 값을 추가합니다.
```js
ary.push(5);

console.log(ary); // [1, 2, 3, 4, 5]
```
만약 값을 제거하고싶다면 `pop`을 사용합니다.<br>
`pop`은 배열의 가장 __끝__에서 원소를 하나 제거합니다.
```js
ary.pop();

console.log(ary); // [1, 2, 3, 4]
```
가장 끝에 위치한 값이 아닌, 처음이나 중간에 위치한 값을 지우고싶다면 `splice`를 사용합니다.<br>
`splice`는 지정된 위치부터 __n__개의 원소를 삭제합니다.
```js
ary.splice(0, 2);

console.log(ary); // [3, 4]
```

랜덤
----
`Math.random()` 메소드는 __0~1__사이의 무작위 값을 생성합니다.
```js
// 무작위 값이 출력됩니다.
// 예를들어 0.123123, 0.5523 같은...
console.log(Math.random());
```
`x ~ y` 사이의 랜덤값을 생성하고 싶으면 아래와 같이 함수를 작성합니다.
```js
// x이상 y미만의 랜덤값을 반환합니다.
function rand(x, y) {
  return Math.floor(Math.random() * (y-x)) + x;
}

console.log(rand(0, 10)); // 0 ~ 9 사이의 숫자
```
<br>
