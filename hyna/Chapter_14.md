# Chapter 14. 자바스크립트 기본 문법

## 14-1 변수 알아보기

### 변수란

### 변수 선언의 규칙

### 변수 선언하기

자바스크립트에서 변수 선언은 다음과 같이 var이라는 예약어 뒤에 변수 이름을 적으면 된다.

```js
/* 기본형 */
var	변수명
```
## 14-2 자료형 이해하기

### 자료형이란

자바스크립트의 자료형은 숫자, 문자열, 논리형과 같은 **기본 유형**과 배열, 객체를 다루는 **복합 유형** 그리고 `undefined`, `null`과 같은 **특수 유형**이 있다. 자바스크립트의 자료형은 다음과 같이 정리할 수 있다. 
![image](https://user-images.githubusercontent.com/91731260/191683742-2be99880-f1d5-4d35-8dfd-0ce054658578.png)

### 숫자형

#### 정수

#### 실수

정밀한 계산 잘 안됨. 이진수로 저장하기 때문.

### 문자열

큰 따옴표 안에 다른 문자열을 넣기 위해서는 작은 따옴표를 활용한다.

### 논리형

**논리형**은 불린<sup>boolean</sup> 유형이라고도 하며, 참이나 거짓의 값을 표현하는 자료형이다. 어떤 조건을 확인해서 그 조건이 맞으면 true, 맞지 않으면 false의 결괏값을 나타낸다. 주로 프로그램에서 조건을 확인할 때 논리형 데이터를 사용한다.

### undefined 유형과 null 유형

undefined는 자료형이 정의되지 않앗을 때의 데이터 상태를 나타낸다. 자바스크립트에서는 변수를 선언할 때 자료형을 미리 지정하지 않고 값을 할당할 때 결정한다. 그래서 변수 선언만하고 초기화되지 않은 자료형을 undefined라고 한다. 즉, undefined는 단순히 '변수에 값이 할당되지 않았다'는 의미이다.
반면에 null은 '데이터의 값이 유효하지 않은 상태'를 나타낸다. undefined와 비슷해 보이지만 구별해야 한다. 

### 배열

데이터 값을 쉼표로 구분해서 대괄호로 묶으면 배열을 선언할 수 있는데, 대괄호 안에 앖을 입력하지 않으면 빈 배열이 만들어진다. 빈 배열도 배열을 선언한 것이다. 

```js
/* 기본형 */
배열명["값1", "값2", ......]
배열명[ ]
```

## 14-3 연산자 알아보기

### 산술 연산자

### 할당 연산자

### 연결 연산자

**연결 연산자**는 둘 이상의 문자열을 합쳐서 하나의 문자열로 만드는 연산자이다. 연산자 기호로 사칙연산의 더하기 연산자와 똑같은 '+' 기호를 사용한다. 

```js
/* example */
document.write (birthyear + "년에 태어난 사람의 나이는 " + age + "세입니다.");
```

### 비교 연산자

![image](https://user-images.githubusercontent.com/91731260/191689124-cad09cf1-44d8-40b8-acf1-0076036a99f6.png)

#### 문자열의 비교

### 논리 연산자

## 14-4 조건문 알아보기

### if문과 if~else 문 알아보기

프롬프트 창에서 [취소] 버튼을 누르면 변수에는 null이 저장된다.

### 조건 연산자로 조건 체크하기

만약 조건이 하나이고 true일 때와 false일 때 실행할 명령이 각각 하나뿐이라면 if~else 문 대신에 조건 연산자를 사용하는 것이 간단하다. 조건 연산자는 '?'와 ':' 기호로 이루어집니다.

```js
/* 기본형 */
(조건) ? true일 때 실행할 명령  : false일 때 실행할 명령
/* example */
(userNumber % 3 === 0) ? alert("3의 배수입니다.") : alert("3의 배수가 아닙니다.");
```

### 논리 연산자로 조건 체크하기

#### OR 연산자

#### AND 연산자

#### NOT 연산자

### switch 문

> **prompt()** 문과 **parseInt()** 함수
> prompt() 문을 사용해 입력받은 값은 기본적으로 문자열로 저장된다. 문자열값이라도 산술 연산에 사용할 경우 자동으로 숫자형으로 변환된다. 이렇게 데이터 유형이 자동으로 변환되기 때문에 예상하지 못한 곳에사 다르게 변환될 수도 있다. 따라서 prompt()로 입력받은 값을 처음부터 숫자로 바꿔 주는 것이 안전하다. 이때 parseInt()함수를 사용한다. 이 함수는 괄호 안의 값을 정수로 변환한다.

## 14-5 반복문 알아보기

### 반복문은 왜 필요한가?

### for 문 사용하기

### 중첩된 for 문 사용하기

### while 문과 do~while 문 사용하기

### break 문과 continue 문 사용하기

#### 건너뛰는 continue 문


