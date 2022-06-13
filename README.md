# Vanilla Challenge

Vanilla challenge start 22.06.06.

## 22.06.07. #2.1 ~ #2.6

- Number type data -> 2, 2.2 ... but in detail 2 = integer, 2.2 = float

- String type data -> "me", "1", "true" ..

- Var can not distinguish variable's roles. So created const(can't changed variable's value) and let(can changed variable's value)

- Boolean type data -> true, false

- null, undefined, Nan ... are not of any type

- Array -> arr = [1, "apple", true, 3.14] => datalist in a 'one' variable

- arr[0] = 1, arr[2] = true

- arr.push("me") => arr = [1, "apple", true, 3.14, "me"]

- Object -> obj = {name:"SJ", age:25, isfat:true} => save data with property

- obj.gender = male -> {name:"SJ", age:25, isfat:true, gender:male}

- obj.name or obj["name"] -> "SJ"

## 22.06.08. #2.7 ~ #2.8

### function이란?

- function은 하나의 코드 덩어리를 사용할 때 쓴다.

```javascript
function hey() {
  alert("hello!");
  console.log("nice to meet you");
}

hey();
```

- 위처럼 function을 만들어 준 후 function의 이름인 hey()만 입력해서 실행하면 funcion안에 alert와 console.log 코드들이 작동한다.

![1](https://user-images.githubusercontent.com/103993019/172543558-8ab10ad3-eeff-42d2-b83a-819beb087046.PNG)

- 또한 변수를 지정해주면 변수에 따른 여러 결과물들을 출력하는 덩어리를 만들어 줄 수 있다.

```javascript
function hello(a, b) {
  console.log("hello " + a + "i'm " + b);
}

hello("SJ", "JS");
hello("MJ", "JM");
```

- 위와 같이 코드를 입력후 실행하면 변수에 따른 console.log가 출력된다.

![2](https://user-images.githubusercontent.com/103993019/172543564-eac4299e-ce9a-43b5-a657-9d45d731d610.PNG)

### function을 object에 넣어 쓰기

- function은 object에 넣어 object의 요소를 뽑아 쓰는 것으로 기능을 할 수 있다.

```javascript
const obj = {
  name: "SJ",
  hello: function (a, b) {
    console.log(a + b);
  },
};

console.log(obj.name);
obj.hello(2, 4);
```

![3](https://user-images.githubusercontent.com/103993019/172543567-42b9610f-218b-4449-ab01-c19d45a57108.PNG)

## #2.9 ~ #2.12

### function의 사용공식 - fuction과 retrun

- function기능의 통용된 사용법은 return을 포함한 함수식을 통해 나온 값을 활용하는 것이다.
- calculator라는 object 안에 각각 add함수와 min함수를 적용한 경우다.

```javascript
let number = 100;

const calculator = {
  add: function (a) {
    number = number + a;
    return "The anwser is " + number;
  },
  min: function (a) {
    number = number - a;
    return "The anwser is " + number;
  },
};

console.log("I have solved it! " + calculator.add(50));
```

![1](https://user-images.githubusercontent.com/103993019/172554591-cc0f085c-eb9c-4564-afed-eda3d05d299a.PNG)

```javascript
let number = 100;

const calculator = {
  add: function (a) {
    number = number + a;
    return "The anwser is " + number;
  },
  min: function (a) {
    number = number - a;
    return "The anwser is " + number;
  },
};

console.log("I have solved it! " + calculator.min(50));
```

![2](https://user-images.githubusercontent.com/103993019/172554599-b32cfe76-b7df-40aa-b4d6-b66a290cc031.PNG)

### 출력된 function값을 연달아 사용 할 경우

- 추가로 함수를 연달아 두번 출력 할 경우 add에서 쓰고 출력한 number 값이 사라지지 않기 때문에 add에서 계산 된 number가 그대로 min에 쓰이게 된다.

```javascript
let number = 100;

const calculator = {
  add: function (a) {
    number = number + a;
    return "The anwser is " + number;
  },
  min: function (a) {
    number = number - a;
    return "The anwser is " + number;
  },
};

console.log("I have solved it! " + calculator.add(50));
console.log("I have solved it! " + calculator.min(50));
```

![3](https://user-images.githubusercontent.com/103993019/172554601-ff7868a8-ca3b-4466-9aa8-c01dc3117bd3.PNG)

## #2.13

### prompt란?

- prompt를 사용하면 사용자가 직접 입력한 값을 코딩에 써먹을 수 있다.

```javascript
const age = prompt("How old are you?");

console.log(age);
```

![1](https://user-images.githubusercontent.com/103993019/172561270-4ec23bb9-354f-461a-ae2a-05afe41337a5.PNG)
![2](https://user-images.githubusercontent.com/103993019/172561274-178e2f6e-710c-4bca-b3ea-9f0b96d4332f.PNG)

### prompt의 특징과 typeoff

- prompt의 입력된 값들은 전부 string(문자)으로 인식하게 된다. 데이터의 타입을 확인인하는 방법은 typeoff를 앞에 붙히면 된다.

```javascript
const age = prompt("How old are you?");

console.log(typeof age);
```

![3](https://user-images.githubusercontent.com/103993019/172561282-cf18a7b0-6e77-4b0c-8117-fc9c966b57c7.PNG)
![4](https://user-images.githubusercontent.com/103993019/172561259-7a0adb07-fb7c-4e3d-b03d-db653a3e9a3e.PNG)

### 문자열을 숫자열(자연수)로! parseInt()

- palseInt내장함수를 이용하면 데이터를 integer(자연수)의 형태로 변환한 수 있다. "감자"처럼 애초에 숫자조차 없는 데이터는 typeof 없이 parseInt과정에서 NaN(숫자아님)으로 출력된다. 참고로 NaN은 Number이다.

```javascript
const age = prompt("How old are you?");

console.log(typeof parseInt(age));
```

![5](https://user-images.githubusercontent.com/103993019/172561261-16e6dee2-6002-47b6-8fd3-ddbb3c30a462.PNG)
![6](https://user-images.githubusercontent.com/103993019/172561264-13f4fe74-7616-42f9-ade8-11783c8540c2.PNG)

```javascript
const age = prompt("How old are you?");

console.log(parseInt(age));
```

![7](https://user-images.githubusercontent.com/103993019/172561267-c3ddaf15-ea17-4fe5-a7eb-4592d2b74201.PNG)
![8](https://user-images.githubusercontent.com/103993019/172561269-2e557c05-7db1-4fe0-ac4e-fb1bd26eb33f.PNG)

## #2.14 ~ 2.16

### 내장함수 isNaN()

- isNaN 내장함수는 입력된 데이터가 string이면 true를 아니면 false를 반환한다.
  "1", "감자"처럼 묶인 경우에는 전부 string으로 인식하지 않고 따옴표를 벗겨낸 데이터 값을 확인한다.

```javascript
console.log(isNaN(123));
console.log(isNaN("123"));
console.log(isNaN("감자"));
```

![1](https://user-images.githubusercontent.com/103993019/172572672-5eb26de1-7de9-44e3-918a-fbaf30c82117.PNG)

### 조건문 if() elseif() else

- if(){~~~~} 에서 ()안의 값이 true일 경우 {}안에 코드가 실행된다.
  if()가 true가 아닐경우 코드를 실행하지 않거나 else{~~~} 혹은 elseif(){~~~}에 있는 코드로 넘어가 실행된다.

```javascript
const age = prompt("당신의 나이는?");

if (isNaN(age)) {
  console.log("나이를 입력해주세요");
} else {
  console.log("당신의 나이는 " + age + " 입니다.");
}
```

![2](https://user-images.githubusercontent.com/103993019/172572682-d1a367d2-3725-4158-889f-bbf29c44baf1.PNG)
![3](https://user-images.githubusercontent.com/103993019/172572686-8c67ffa1-26c9-4ef2-b921-2f7ce7a55b02.PNG)
![4](https://user-images.githubusercontent.com/103993019/172572705-13782aac-e31b-4fc9-9736-ffd3a7ff9b91.PNG)
![5](https://user-images.githubusercontent.com/103993019/172572707-5778097b-5c1d-41f4-bdf3-e3f11df20d50.PNG)

### &&(and)와 ||(or)

- true && true => true, true && false => false, false && false => false다. &&(and)는 둘 다 true일 때 true를 반환한다.

- true || true => true, true || false => true, false || false => false다. ||(or)는 둘 중 하나만 true이면 true를 반환한다.

```javascript
const age = prompt("당신의 나이는?");

if (isNaN(age)) {
  console.log("나이를 입력해주세요");
} else if (age < 20 || age >= 100) {
  console.log("술은 어른되고 젊을 때 마시는거에요");
} else if (age >= 20 && age < 100) {
  console.log("즐술");
}
```

![1](https://user-images.githubusercontent.com/103993019/172577843-9c31882b-5117-4682-9f60-dd87a38deb4b.PNG)
![2](https://user-images.githubusercontent.com/103993019/172577848-eb37a1bb-7de9-4085-9210-88048e060260.PNG)
![3](https://user-images.githubusercontent.com/103993019/172577850-946fb431-84d3-440d-8e73-aa1daaeb1c27.PNG)
![4](https://user-images.githubusercontent.com/103993019/172577858-b06b0809-3289-47c2-8bd4-ae366f38a6cf.PNG)

## 22.06.08. #3.0 ~ #3.2

### console에 document 호출하기

- 브라우저 console에 document를 호출하면 해당 브라우저랑 연결된 HTML을 보여준다.
  또한 console.dir(document)로 호출을 하면 HTML 내부의 속성들이 object(객체)의 형식으로 나열되어 보여진다.
  js에서 object의 요소들을 불러올 때 처럼 document.title을 써서 호출하면 정말로 HTML코드의 title property(요소)의 key(값)를 가져올 수 있고 값을 변환 할 수도 있다.
  물론 이는 브라우저의 console 뿐만 아니라 vsc의 js파일에서도 가능하다.

![1](https://user-images.githubusercontent.com/103993019/173184652-33769212-8cb5-4a33-a2b4-d256d3665399.PNG)
![2](https://user-images.githubusercontent.com/103993019/173184654-6b843e94-0c46-47bb-bc9f-217e61f3ac40.PNG)
![3](https://user-images.githubusercontent.com/103993019/173184655-8018b666-85a8-40cf-bf4d-bd3b66c5088a.PNG)
![4](https://user-images.githubusercontent.com/103993019/173184656-8ecaf4e6-ff7d-4c24-ab07-b9d65527f02d.PNG)

### element(속성) 불러오기

- console.dir()을 통해 객체형태로 document를 보면 수많은 요소들 중 getElementsById라는 것이 있다.
  이는 요소들 중 mothod값을 가지는 함수형태의 요소로 이를 이용하면 특정 id값을 가지는 HTML의 부분을 가져올 수 있다.
  이 때 이러한 HTML의 부분을 JS에서는 element(속성)라고 부른다.
  또한 title의 경우와 마찬가지로 VSC를 통한 JS조작을 통해 브라우저에서 보여지는 값을 변경할 수도 있다.

![5](https://user-images.githubusercontent.com/103993019/173184657-a0ba1ab8-d142-46aa-b902-7dde6ffa1741.PNG)
![6](https://user-images.githubusercontent.com/103993019/173184658-bb8c0cf0-3c01-4a82-98ca-94b9ac2b1067.PNG)
![7](https://user-images.githubusercontent.com/103993019/173184659-d2a2fee7-f400-4673-86aa-c8987446e2b1.PNG)
![8](https://user-images.githubusercontent.com/103993019/173184662-83bd7950-2d42-43a7-9576-f465ee6bb740.PNG)

- 추가로 속성을 불러오는데는 getElementById 외에도 태그, class이름 등 불러오고 싶은 방식에 따라 getElementsByClassName, getElementsByTagName 등을 쓸 수 있고 css선택자 방식을 적극 사용할 경우 querySelector 혹은 querySelectorAll을 이용할 수 있다.

```javascript
const classes = document.getElementsByClassName("int");
const divs = document.getElementsByTagName("div");
const css1 = document.querySelector("div > h1");
const css2 = document.querySelectorAll("div");

console.log(classes);
console.log(divs);
console.log(css1);
console.log(css2);
```

![9](https://user-images.githubusercontent.com/103993019/173184663-b688d3c1-bd21-40b0-b80a-e63b4ff4fef9.PNG)

## 22.06.12. #3.3 ~ 3.5

### js로 style 설정하기

- 거의 모든 element들에는 style이 property로 들어있다.
  따라서 object불러오는 것 처럼 style을 불러온 후 값을 변경하는 것으로 css작업도 할 수 있다.

```javascript
const title = document.querySelector("div > h1");

title.style.color = "blue";
```

![1](https://user-images.githubusercontent.com/103993019/173230957-c4537b03-6c85-4294-ba9b-34e1c474b65f.PNG)

### js의 기능부여 event!

- 지정해준 element에 기능을 부여하는 공식이 있다.
  title이란 변수로 element를 지정했다고 했을 때, title.addEventListener("조건", 함수)라고 쓰면 특정 조건을 하였을 때 함수가 작용하도록 element가 역할을 하는 것이다.
  아래는 hello를 클릭했을 때 console.log가 작동되도록 코드를 짠 것이다.

```javascript
const title = document.querySelector("div > h1");

function handleTitleClick() {
  console.log("이벤트 테스트!");
}

title.addEventListener("click", handleTitleClick);
```

![2](https://user-images.githubusercontent.com/103993019/173230961-2f08563a-98be-4050-acf1-233e083ab59d.PNG)

### 이벤트로 style 바꾸기

함수 안에 스타일을 넣어주면 끗

```javascript
const title = document.querySelector("div > h1");

function handleTitleClick() {
  title.style.color = "orange";
}

title.addEventListener("click", handleTitleClick);
```

![3](https://user-images.githubusercontent.com/103993019/173230962-bd9e4efd-03db-4262-be6c-a50a3bdf71e0.PNG)

### click 외 다른 event들

- console.dir() 또는 https://developer.mozilla.org/ko/docs/Web/Events 사이트에서 또다른 event들을 찾아볼 수 있다.
  그 중에 가장 대표적인 mouseenter와 mouseleave를 title의 event로 설정하고 각각의 function을 만들어주면 다음과 같이 할 수 있다.

```javascript
const title = document.querySelector("div > h1");

function handleTitleClick() {
  title.style.color = "orange";
}

function handleTitleEnter() {
  title.innerText = "mouse here!";
}
function handleTitleLeave() {
  title.innerText = "mouse gone..";
}

title.addEventListener("click", handleTitleClick);
title.addEventListener("mouseenter", handleTitleEnter);
title.addEventListener("mouseleave", handleTitleLeave);
```

![4](https://user-images.githubusercontent.com/103993019/173230963-2a11c773-9256-4347-9430-b32263790110.PNG)
![5](https://user-images.githubusercontent.com/103993019/173230964-d1a6d5ee-c04b-43ee-a580-20b3879ab1c2.PNG)

- addEventListener("click") 대신 property의 이름 그대로 onclick을 쓸 수도 있다.
  단, removeEventListenr와 같이 쓸 수 있는 특징 때문에 니꼬쌤은 addEventListener을 추천하셨다.

```
title.addEventListener("click", handleTitleClick) -> title.onclick = handleTitleClick
```

- eventlitening은 직접 만든 element외에 title, body 등에도 지정해줄 수 있다.
  특정 element에 listening 하기 애매한 창 크기 변화, 스크롤 움직이기, 인터넷 연결여부 등의 event를 listening 해주고 싶을 때는 window에 해주면 된다.

```javascript
const title = document.querySelector("div > h1");

function handleTitleClick() {
  title.style.color = "orange";
}

function handleTitleEnter() {
  title.innerText = "mouse here!";
}

function handleTitleLeave() {
  title.innerText = "mouse gone..";
}

function handleWindowScroll() {
  title.innerText = "Scroll faster!";
}
function handleWindowResize() {
  title.innerText = "Change size";
  document.body.style.backgroundColor = "teal";
}
function handleWindowsOffline() {
  alert("I can't connect Internet.. Please check your computer that Wifi");
}
function handleWindowOnline() {
  alert("Success connecting Internet!");
}

title.addEventListener("click", handleTitleClick);
title.addEventListener("mouseenter", handleTitleEnter);
title.addEventListener("mouseleave", handleTitleLeave);
window.addEventListener("scroll", handleWindowScroll);
window.addEventListener("resize", handleWindowResize);
window.addEventListener("online", handleWindowOnline);
window.addEventListener("offline", handleWindowsOffline);
```

![6](https://user-images.githubusercontent.com/103993019/173230966-2fdf85e9-72be-437a-9558-37418643b239.PNG)
![7](https://user-images.githubusercontent.com/103993019/173230967-98241849-7ec1-461a-9139-c2e6856d1373.PNG)
![8](https://user-images.githubusercontent.com/103993019/173230968-221e0b41-3052-425d-8d45-e3ac6250da28.PNG)
![9](https://user-images.githubusercontent.com/103993019/173230969-f9f31422-9607-4be8-bcca-b63926a4e608.PNG)

## #3.6 ~ #3.7

### 조건문(if else)을 넣어 기능을 다채롭게 하기.

- 위처럼 h1을 title란 이름의 element로 가져왔을 때 title이 초록색일 때는 주황색으로, 아니라면 초록색으로 변하는 것을 onclick event만으로 만들 때는 함수에 조건문을 넣어주면 가능하다.

```javascript
const title = document.querySelector("div > h1");

function handleTitleClick() {
  const beforColor = title.style.color;
  let afterColor = "";
  if (beforColor === "teal") {
    afterColor = "tomato";
  } else {
    afterColor = "teal";
  }
  title.style.color = afterColor;
}

title.addEventListener("click", handleTitleClick);
```

<!--teal-->
<!--orange-->

### js를 css와 함께 써서 style 바꾸기

- js로 element 내의 property를 찾아서 직접 style을 바꾸는 것도 가능하지만 니꼬쌤 왈 가능한 style은 css를 사용해 바꿔주는 것이 좋다고 하신다.
  해법은 그냥 className을 바꿔주는 것!

```javascript
const title = document.querySelector("div > h1");

function handleTitleClick() {
  const fontColor = title.className;
  let afterColor = "";
  if (fontColor === "teal") {
    title.className = "orange";
  } else {
    title.className = "teal";
  }
  afterColor = title.className;
}

title.addEventListener("click", handleTitleClick);
```

<!--style-->
<!--console ""-->
<!--console changeColor-->

## 22.06.13. #3.8

### className이 복합적으로 있을 때 한 개만 쏙 집어 넣고 빼기

- <div class="red"></div> 요렇게 있으면 위에처럼 className을 바꿔주는 것으로 style을 바꿀 수 있지만 <div class="font-blue red"></div> 이런식으로 여러개 있는 경우에는 저렇게 했다가는 기존에 있는 css효과가 없어져버린다.
  그럴 때는 <클래스이름의 포함여부>를 확인 후 <추가> 혹은 <제거> 해주는 순서를 밟는다.
  <클래스이름의 포함여부>로 쓰이는 것이 classList.contains <추가>는 classList.add, <제거>는 classList.remove를 써주면 된다.

```javascript
const title = document.querySelector("div > h1");

function handleTitleClick() {
  const colorName = "changeColor";
  if (title.classList.contains(colorName)) {
    title.classList.remove(colorName);
  } else {
    title.classList.add(colorName);
  }
}

title.addEventListener("click", handleTitleClick);
```

<!--remove-->
<!--add-->

### 같은 기능 toggle 하나로 끝내기

- 위의 함수는 포함여부 -> 추가 or 제거의 기능을 가지는데 처음부터 이 기능을 가진 내장함수가 존재한다.
  contains + add + remove => toggle!!

```javascript
const title = document.querySelector("div > h1");

function handleTitleClick() {
  title.classList.toggle("changeColor");
}

title.addEventListener("click", handleTitleClick);
```

<!--remove toggle-->
<!--add toggle-->
