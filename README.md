## Pseudo-Selectors

#### 1. flex-wrap
flex-wrap은 flex의 하위 요소들이 flex를 선언한 영역을 벗어날 경우, 강제로 한 줄로 배치할 지 행을 나눠서 배치할 지 결정하는 속성입니다. <br/>
flex-wrap: wrap 을 선언한다면, flex를 선언한 영역을 벗어날 경우 행을 나눠서 배치하게 됩니다. <br/>
default값은 nowrap으로, 강제로 한 줄로 배치합니다. <br/>
wrap-reverse 값은 행을 나눠서 배치하되, 위로 나뉩니다. <br/>
일반적인 flex-wrap: wrap의 경우, 1 2 3 4 의 순서로 행이 나뉘는 반면, flex-wrap: wrap-reverse의 경우, 3 4 1 2 의 순서로 행이 나뉩니다.

#### 2. nth-child
:nth-child(n)는 형제들 사이에서 n번째 요소를 선택할 수 있는 의사 선택자입니다. <br/>
선택자 뒤에 추가되는 형식으로 작성됩니다. (ex. div:nth-child(3), #text:nth-child(4)) <br/>
nth-child은 형제들의 타입은 신경쓰지 않습니다. 오로지 순서만 따집니다. <br/>
![ex01](https://user-images.githubusercontent.com/88027485/195149087-63fb2768-e9e8-4b48-92dc-e8f0f2641b0a.png) <br/>
위의 html 코드에서 h1:nth-child(2) { color: red; } 를 한다면, 어떠한 글자도 빨간색이 되지 않습니다. 왜냐하면 h1이면서 형제들 중 2번째인 요소는 없기 때문이죠. <br/>
span:nth-child(1) { color: green; } 도 마찬가지입니다. <br/>
만약 h1 요소들 중에 2번째 h1을 선택하고 싶다면, :nth-of-type(n) 을 사용하면 됩니다. <br/>
nth-of-type은 동일한 타입들 안에서 순서를 따집니다. <br/>
위의 html 코드에서 h1:nth-type(2) { color: red; } 를 한다면, 2번째 h1에 빨간색이 적용될 것입니다. <br/>
첫 번째 혹은 마지막 번째의 요소를 선택하고 싶다면, first-child, last-child, first-of-type, last-of-type 을 사용하면 됩니다. <br/>
또한 뒤에서 n번째 요소를 선택하고 싶다면, nth-last-child, nth-last-of-type 을 사용하면 됩니다. <br/>
짝수 혹은 홀수만 선택하거나, n의 배수 등을 선택하는 방법이 있습니다. <br/>
nth-child(n) 의 n 자리에 odd(홀수), even(짝수), 3n, 4n-1 등을 넣어 다양한 선택자로 활용할 수 있습니다.

#### 3. Position 속성
Position의 default 값은 static 입니다. <br/>
브라우저는 우리가 입력한 여러 요소에 대한 기본적인 크기와 위치 등을 가지고 있고, 이를 바탕으로 문서의 흐름에 따라 배치합니다. <br/>
이렇게 기본적인 흐름으로 배치하도록 두는 것이 static 속성입니다. <br/>
이때는 top, bottom, left, right 등 위치를 설정하는 속성값이 영향을 주지 않습니다. <br/>
이와 비슷한 속성으로 relative가 있습니다. <br/>
최초의 위치는 static과 동일하며, top, bottom, left, right 속성값의 영향을 받습니다. <br/>
top, bottom, left, right 값은 현재 위치를 기준으로 합니다. (ex. top: 100px; 은 현재 위치에서 아래로 100px 옮깁니다.) <br/>
absolute는 static, relative와 다르게 일반적인 문서 흐름에서 제외됩니다. <br/>
대신 부모 및 조상요소들 중 position: static이 아닌 가장 가까운 조상을 기준으로 잡습니다. (ex. top: 100px;은 static이 아닌 가장 가까운 조상을 기준으로, 상단에서 100px 만큼 떨어진 곳으로 옮깁니다.) <br/>
이러한 특성때문에 absolute를 사용할 때, 위치의 기준으로 삼을 부모에 position: relative를 선언합니다. <br/>

### 결론
1. flex-wrap을 이용하면 flex만으로 여러 행을 구현할 수 있습니다. <br/>
하지만 grid도 정말 편리합니다. <br/>
코코아톡 클론 코딩이 즐거우셨다면, css layout 강의도 추천드립니다! <br/>
2. nth-child는 좁은 범위로 사용하시는 게 좋습니다. <br/>
일반적은 태그보다, class와 함께 사용하세요. <br/>
사용되는 범위가 넓을 수록 의도치 않게 동작할 확률이 높습니다. <br/>
3. absolute는 relative와 함께. <br/>
relative는 top, bottom 등 위치 속성을 사용하지 않는다면 static과 다를 바 없습니다. <br/>
요소중에 absolute를 사용해야된다면 위치의 기준이 될 부모에 relative를 선언해주세요. <br/>
