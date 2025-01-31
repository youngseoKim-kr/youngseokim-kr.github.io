---
layout: single
title: "JavaScript[변수, 함수, 조건문, 연산자]"
categories: JavaScript
toc: true
author_profile: false
sidebar:
    nav: "docs"
# 검색 불가
# serch: false 

---







## 변수



변수를 선언하는 이유? 

변수를 어떤 방법으로 사용할지 컴퓨터에게 알려주는 과정으로 
서로 다른 변수의 타입이 있기 때문에 다른 특징들을 컴퓨터에게 알려줘야 한다.

let a=300;

let -> 변경가능

const -> 변경 불가 

| 기본 타입 | 참조 타입 |
| :-------: | :-------: |
|  Number   |  Object   |
|  String   |   Array   |
|  Boolean  | Function  |
| Undefined |           |
|   Null    |           |

Number = + , - , /(몫) , %(나머지) , * 
string = '문자열'
boolean = true, false

Undefined 와 Null의 차이
변수를 선언하고 Null이라는 값을 주어지면 Null인 상태이고
변수에 아무 값도 주어지지 않으면 undefined 이다.

![image-20220122135037895](../images/image-20220122135037895.png)

```javascript
//문자열 길이 구하기
const mystring = 'Hello! kys!!';
console.log(mystring.length) //12
console.log('Hello! kys!!'.length)
```



## 함수

재사용이 가능하고, 함수를 가독성 있게 정의하면 어떤 기능인지 함수를 보고도 유추가 가능하며, 함수 유지 보수가 쉽게 가능합니다.

Input -> 기능수행 -> output

정의 -> 호출

함수의 정의와 호출의 차이점

**함수**를 **정의**하는 것은 **함수**를 실행하는 것이 아닙니다. **함수**를 **정의**하는 것은 간단히 **함수의** 이름을 지어주고, **함수**가 **호출**될 때 무엇을 할지 지정해 주는 것입니다. 사실 **함수**를 **호출**하는 것은 나타나있는 매개변수를 가지고 지정된 행위를 수행하는 것이다.

```javascript
function sayHello(name){
  return 'hello, '+ name +'!';
}
let name = sayHello('kys');
console.log(name)  //hello, kys!
```

sayHello라는 함수를 만들고 parameter 값으로 argument 값인 kys를 넣어주고 sayhello 함수에서 return 값 (hello, keys!)를 name 변수에 넣어주고 그 name 변수를 console.log 로 찍어준다.



## 조건문

if(조건){} -> 조건이 참일 경우 {}안에 코드를 실행

else{} -> else 단독으로 사용하지 못하고 if문이 참이 아닐 경우 else문을 실행

```javascript
function selectItems(car){
  if(car==="yellow"){
    return "mycar";
  }
  else if(car=="black"){
    return "mom";
  }
  else if(car=="blue"){
    return "dad";
  }
  else {
    return "Nope!";
  }
}
selectItems("yellow");  //-> mycar
selectItems("black");  //->mom
selectItems("blue");  //->dad
selectItems("red");  //->Nope!
```

차 색을 selectItems라는 함수에 넣어주면 색에 따라서 결과 값이 반환된다.
각 색마다 주인들이 있고 yellow, black,blue 세가지 색 전부 아니면 우리 가족이 소유한 차가 아니다.

```javascript
let a=5;
//if ,else if 
if(a>4){
  console.log("a");
}
else if(1<a && a<6){
  console.log("b");
}
else {
  console.log("c");
}
//a만 출력된다.
//if, if 
if(a>4){
  console.log("a");
}
if(1<a && a<6){
  console.log("b");
}
//a,b 둘다 출력
```

if문을 여러개 사용할 때 와 else, else, else if, if를 이용하여 조건문을 활용하는 방법

### 삼항연산자

```javascript
let a= true;
let b = false;
console.log(b ? "1" : "2");
//b가 참이면 1이 출력되고 b가 거짓이면 2가 출력된다.
```



### 논리연산자

|     연산자     | 사용법            | 설명                                    |
| :------------: | ----------------- | --------------------------------------- |
| 논리연산자 AND | Ex1 && Ex2        | 두개의 `조건이 모두` 참인 값이여야 true |
| 논리연산자 OR  | Ex1  \|\|    Ex2. | 두개의 `조건중 하나라도` 참이면 true    |



### Truthy , Falsy

`Falsy` : False, 0, -0, On, "", null, undefined, NaN 등

`Truthy` : true, {}, [], 42, "0", "false", -42 ... 이외 다른 것들
