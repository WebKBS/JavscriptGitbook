---
description: Image Element 생성
---

# new Image() 사용법.

이미지 생성 방법에는 2가지 방법이 있다.

```javascript
const image = document.createElement("img");
```

```javascript
const image = new Image()
```

createElement는 document.createElement(태그이름, \[옵션])으로 구성되고

new Image()는 new Image(width, height)로 구성된다.



### new Image에 대해서 알아보자.

new Image()에 파라미터로 number (width, height)를 전달하면

이미지 생성 당시 width 값과 height 값을 정할 수 있다.

```javascript
const image = new Image(300, 300) // 가로 300, 세로 300 사이즈 이미지
```

const image = new Image(300) 하나만 지정시 width값만 가능.



new Image()의 속성

* width
* height
* naturalWidth
* naturalHeight
* complete
* currentSrc
* src
* decode()

```javascript
const image = new Image();
image.src = "주소"; // 이미지 src 추가
image.width = 100; // number 이미지 width 설정
image.height = 100; // number 이미지 height 설정
image.naturalWidth // 이미지 고유의 원본 이미지 가로 사이즈
image.naturalHeight // 이미지 고유의 원본 이미지 세로 사이즈
image.complete // 이미지가 완전히 다운로드되었거나 이미지가 지정되지 않은 경우 true를 반환 그렇지 않을 경우 false
image.crrentSrc // 이미지 절대 URL

image.decode() // 이미지를 병렬로 디코딩.
// 이미지가 디코딩이 완료되면 promise를 반환. 이미지를 디코딩할수 없는 경우 EncodingError반환, 프로미스 error
```

new Image()에는 onload 이벤트가 있다.

```javascript
const image = new Image();
image.src = "주소";
image.onload = () => {
    document.body.appendChild(image);
};
image.onerror = () => {
    document.body.appendChild(new Text("Could not load the nebula :("));
};
```

onload 대신에 decode()를 사용할 수 도있다.

```javascript
const image= new Image();
image.src = "주소";
image.decode().then(() => {
    document.body.appendChild(image);
}).catch(() => {
    document.body.appendChild(new Text("Could not load the nebula :("));
});

```



자세한 사항은 아래 주소에서 살펴 보자.

{% embed url="https://html.spec.whatwg.org/multipage/embedded-content.html#the-img-element" %}

{% embed url="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/Image" %}

{% embed url="https://developer.mozilla.org/en-US/docs/Web/API/HTMLImageElement/decode" %}
