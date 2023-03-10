---
description: id 기본값 대신에 왜 getElementById를 쓸까?
---

# getElementById를 사용하는 이유

Javascript를 사용하다보면 의문이 하나있다.&#x20;

id에 대한 내용이다.



사실 id는 고유의 값으로 javascript를 사용할 때

document.getElementById를 사용하지 않아도 사용할 수 있다.



예시)

```html
<input type="text" id="username">
```

이와 같이 username이라는 id가 있으면 javascript에서 즉시 사용할 수 있다.

```javascript
username.value
```



이렇게 간편하게 사용할 수 있지만, 왜 굳이 getElementById를 사용하는 것은.

#### 1. id값의 이름은 다른 변수지정에 의해 사용이 불가능 할수 있다.

ex)

```javascript
const username = "Kim"; // 변수로 문자열을 지정
```

이 처럼 변수에 같은 이름을 지정하면\
값을 변수에 저장하지 않은 username의 사용처는 변경된다.



#### 2. 가독성.

username을 id값으로 기본적으로 사용할수 있더라도. 변수로 지정되지 않거나\
getElementById('username') 이라고 명시하지 않고,\
단순히 username만 아이디값으로 사용한다면 협업할때 본인은 알고있더라도\
다른사람들에게는 혼란을 줄 수 있다.\
고로 명확히 getElementById('username') 또는 querySelector("#username") 을 사용하는 방법이 낫다.



마지막으로.

id값을 편하게 사용할 수 있더라도, 혹시나 모를 에러를 방지하기 위함과, 가독성을 위해서

반드시 명시적으로 표현하는 것이 좋다.
