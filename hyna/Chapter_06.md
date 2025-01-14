# Chapter 06

### 6-1 웹 문서에 디자인 입히기

#### 스타일을 사용하는 이유

**`스타일`이란??** : HTML 문서에서 자주 사용하는 글꼴, 색상 등 각 요소의 배치 방법과 같이 문서의 겉모습을 결정짓는 것을 가리킨다.

**그렇다면 왜 굳이 HTML로 스타일 정의를 하는 것이 아니라 `sytle`을 사용할까?**

1. `HTML`과 `CSS`로 나누어 전자로는 웹 사이트의 내용을 나열하고, 후자로는 웹 문서의 디자인을 구성한다는 아이디어가 웹 표준의 시작이다.
2. 위와 같이 구분되어 있으면 사이트의 내용을 수정할 때에도 디자인에 영향을 미치지 않아 편리하다.
3. 다양한 기기에 맞게 탄력적으로 바뀌는 문서를 만들 수 있다. 기존 `HTML` 문서는 각 기기에 맞게 각각 문서를 따로 만들어야했다. 그러나 `CSS`를 이용하게 된다면 각 기기에 맞게 `CSS`만 바꾸어주면 각각의 기기에서 같은 내용을 편하게 볼 수 있다.

\


> &#x20; **반응형 웹 디자인이란?** 웹 브라우저의 크기에 따라 화면 레이아웃을 자동으로 바꿔 주는 방법. 웹 문서를 따로 만드는 것이 아닌 하나의 웹 문서에서 작동하도록 만드는 것이 스타일의 영역이다. &#x20;

### 6-2 스타일과 스타일 시트

#### 스타일 형식 알아아보기

`CSS` 소스에서 한 줄이 하나의 스타일에 해당하며, 줄마다 형태가 비슷하다.

기본형

```css
선택자 { 속성1 : 속성값1; 속성2 : 속성값2 }
```

`선택자` : 스타일을 어느 태그에 적용할 것인지 알린다. 중괄호 사이에 스타일 정보를 넣는다. `스타일 규칙` : 속성과 값이 하나의 쌍으로 이루어진 것. 세미콜론 `;`으로 구분해서 스타일 규칙을 여러 개 지정할 수 있다.

ex.

```css
p {
	text-align : center;
	color : blue;
}
```

#### 스타일 규칙을 작성하는 방법

사용할 스타일이 여러 개일 경우 한 줄에 한 속성만 적는 것이 직관적이고 주석 달기도 편하지만, 소스가 길어지지 않도록 `{}` 사이에 스타일 규칙을 한 줄로 적기도 한다.

#### 스타일의 주석을 표기하는 방법

태그에서 주석을 사용한 것처럼 스타일에도 주석을 덧붙일 수 있다. 주석을 표기할 때는 `/*`와 `*/` 사이에 내용을 입력한다.

> &#x20; **CSS 소스 경량화** CSS 소스는 네트워크를 이용해 파일로 내려받기 때문에 되도록이면 파일 크기가 작은 것이 좋다. 그래서 `CSS`소스가 길면 주석이나 줄 바꿈, 공백 등을 제거하고 꼭 필요한 정보만 만들어 사용한다. 이것을 `CSS` 소스 경량화(minify)라고 한다. `css minify`나 `css compress`를 검색하면 관련된 다양한 툴을 찾을 수 있다. &#x20;

#### 스타일 시트 알아보기

스타일 규칙을 한눈에 확인하고, 필요할 때마다 수정하기 쉽도록 한군데 묶어놓은 것을 `스타일 시트`라고 한다. 스타일 시트는 크롬 웸 브라우저에 기본으로 만들어져 있는 `브라우저 기본 스타일`과 사이트 제작자가 만드는 `사용자 스타일`로 나눌 수 있다. `사용자 스타일`은 다시 `인라인 스타일`과 `내부 스타일 시트`, `외부 스타일 시트`로 나뉜다.

**브라우저 기본 스타일**

CSS를 사용하지 않은 웹 문서라 할지라도 웹 브라우저는 기본 스타일을 사용한다. 이것을 `브라우저 기본 스타일`이라 한다.

**간단한 스타일 정보를 적용하는 인라인 스타일**

간단한 스타일 정보라면 스타일 시트를 사용하지 않고 스타일을 적용할 대상에 직접 표시한다. 이런 방법을 `인라인 스타일`이라고 한다. 스타일을 적용하고 싶은 부분이 있다면 해당 태그에 `style` 속성을 사용해 `style="속성: 속성값;"`형태로 스타일을 바꿀 수 있다.

**스타일을 여러 곳에 적용할 때 쓰는 내부 스타일 시트**

웹 문서 안에서 사용할 스타일을 같은 문서 안에 정리한 것을 `내부 스타일 시트`라고 한다. 스타일 정보는 웹 문서를 브라우저 화면에 표시하기 전에 결정해야 하므로 모든 스타일 정보는 `<head>` 태그 안에서 정의하고 `<style>` 태그 사이에 작성한다.

**스타일 정보를 따로 저장해 놓은 외부 스타일 시트**

웹 사이트를 만들 때 하나의 웹 문서로 끝나는 경우는 거의 없고, 대부분은 디자인에 일관성이 있고록 같은 스타일을 여러 웹 문서에 사용한다. 그러나 그때마다 웹 문서를 똑같은 내부 스타일 시트로 만든다면 서버 공간은 물론 문서를 내려받는 시간까지 낭비할 것이다. 따라서 사이트를 제작할 때는 여러 웹 문서에서 사용할 스타일을 별도 파일로 저장해두고 필요할 때마다 가져와서 사용하는 것이 일반적이다. 이러한 스타일 정보를 `외부 스타일 시트`라 하고, `*.css`라는 파일 확장자를 사용한다. 외부 스타일 시트 파일에 스타일을 작성할 때는 `<style>`태그를 사용하지 않는다. 그리고 이렇게 만든 외부 스타일 시트는 웹 문서에 연결해야 스타일이 문서에 적용된다. 외부 스타일 시트를 연결할 때 사용하는 태그는 `<link>` 태그이다.

```css
/*기본형*/ <link rel="stylesheet" href="외부 스타일 시트 파일 경로">
```

### 6-3 CSS 기본 선택자 알아보기

#### 전체 요소에 스타일을 적용하는 전체 선택자

전체 선택자로는 `*`를 사용한다.

```css
/*기본형*/ * { 속성: 값; ... }
```

주로 웹 브라우저의 기본 스타일을 초기화할 때 자주 사용한다.

> &#x20; **태그와 요소의 차이점** 태그는 말 그대로 태그를 가리키는 반면, 요소는 태그를 적용한 것을 가리킨다. &#x20;

#### 특정 요소에 스타일을 적용하는 타입 선택자

`타입 선택자`는 특정 태그를 사용한 모든 요소에 스타일을 적용한다.

```css
/*기본형*/ 태그명 { 스타일 규칙 }
```

#### 특정 부분에 스타일을 적용하는 클래스 선택자

같은 태그라도 일부는 다른 스타일을 적용하고 싶을 때 사용한다. 클래스 이름을 사용해서 다른 선택자와 구별한다.

```css
/*기본형*/ .클래스명 { 스타일 규칙 }
```

요소 하나에 클래스 스타일을 2개 이상 적용할 수도 있다. 클래스를 여러 개 지정할 때는 스패이스로 구분한다.

```
/*예시*/
.class1 {color : blue}
.class2 {font-style : italic}
```

```html
<div class="class1 class2"></div>
```

#### 특정 부분에 스타일을 한 번만 적용할 수 있는 id 선택자

id 선택자도 클래스 선택자와 마찬가지로 웹 문서의 특정 부분을 선택해서 스타일을 지정할 때 사용한다. 마침표 대신 `#`기호를 사용한다. id 스타일을 웹 요소에 적용할 때는 `id="아이디"`처럼 사용한다.

```css
/*기본형*/ #아이디명 { 스타일 규칙 }
```

클래스 선택자와 id선택자의 가장 큰 차이점은 **클래스 선택자가 문서에서 여러 번 적용될 수 있는 반면, id 선택자는 문서에서 한 번만 적용될 수 있다는 점이다.** 그렇기에 주요 문서의 레이아웃과 관련된 스타일을 지정하거나, 웹 요소에 자바스크립트 프로그램을 사용하며 요소를 구별할 때 사용한다.

#### 같은 스타일 규칙을 사용하는 요소들을 묶어주는 그룹 선택자

여러 선택자에서 같은 스타일 규칙을 사용하는 경우가 있다. 이럴 때는 쉼표(,)로 구분해 여러 선택자를 나열한 후 스타일 규치글 한 번만 정의하면 된다.

```css
/*기본형*/ 선택자1, 선택자2 {스타일 규칙}
```

### 6-4 캐스케이딩 스타일 시트 알아보기

#### 캐스케이딩의 의미

CSS에서 C는 **캐스케이딩**의 줄임말이며, 스타일 시트에서는 우선순위가 위에서 아래로 적용된다는 의미로 사용된다. 그래서 **CSS에서는 웹 요소에 둘 이상의 스타일을 적용할 때 우선순위에 따라 적용할 스타일을 결정**한다. 케스케이딩은 스타일끼리 충돌하지 않도록 막아 주는 중요한 개념이며, 스타일이 충돌하지 않게 하기 위해서는 2가지 방법이 있다.

> &#x20;
>
> 1. **`스타일 우선순위`** : 스타일 규칙의 중요도와 적용 범위에 따라 우선순위가 결정되고, 그 우선순의에 따라 위에서 아래로 스타일을 적용한다.
> 2. **`스타일 상속`** : 태그의 포함 관계에 따라 부모 요소의 스타일을 자식 요소로, 위에서 아래로 전달한다. &#x20;

#### 스타일 우선순위

**스타일 우선순위**는 캐스케이딩에서 가장 중요하다. 우선순위는 다음 3가지 개념에 따라 지정된다.

**얼마나 중요한가?**

웹 브라우저가 내용을 표시할 때는 단순히 CSS 소스의 스타일만 적용되는 것이 아니다. 컴퓨터 사용자가 지정한 스타일과 웹 문서를 제작한 제작자의 스타일, 웹 브라우저가 기본으로 정해 놓은 스타일, 이렇게 3가지 스타일을 함께 사용한다. 우선순위는 아래와 같다

1. 사용자 스타일
2. 제작자 스타일
3. 브라우저 기본 스타일

**적용 범위는 어디까지인가?**

중요도가 같은 스타일이라면 스타일 적용 범위에 따라 우선순위가 정해진다. 즉, 정확히 필요한 요소에만 적용한 스타일일수록 우선순위가 높아진다. 단, 스타일 규칙에 `!important`를 붙이면 그 스타일은 다른 스타일보다 우선순귀가 높아진다. 우선순위는 아래와 같다.

1. !important
2. 인라인 스타일
3. id 스타일
4. 클래스 스타일
5. 타입 스타일

`!improtant` : 어떤 스타일보다 우선 적용하는 스타일이다. `인라인 스타일` : 태그 안에 `sytle`속성을 사용해 해당 태그에만 속성을 적용한다. `id 스타일` : 지정한 부분에만 적용되는 스타일이지만 한 문서에 한 번만 적용할 수 있다. `class 스타일` : 웹 문서에서 지정한 부분에만 적용되는 스타일로 한 문서에 여러 번 적용할 수 있다. `타입 스타일` : 웹 문서에서 사용한 특정 태그에 스타일을 똑같이 적용한다.

**소스 코드의 작성 순서는?**

스타일 시트에서 중요도와 적용 범위가 같다면 그다음은 스타일을 적용한 소스 순서로 우선순위가 정해진다. 나중에 작성한 스타일이 먼저 작성한 스타일을 덮어쓴다.

#### 스타일 상속

웹 문서에서 사용하는 여러 태그는 서로 포함 관계가 있다. 이때 포함하는 태그를 부모요소, 포함된 태그를 자식요소라고 한다. 스타일 시트에서는 자식 요소에서 별도로 스타일을 지정하지 않으면 부모요소의 스타일 속성들이 자식 요소로 상속된다. 이를 스타일 상속이라고 한다.
