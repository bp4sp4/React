# ReactJS 로 영화 웹 서비스 만들기
<h1>ReactJS 1일차<br>23.08.12</h1>

<h3>JS와 ReactJs 차이점</h3>
<ul>
<li> 따로 js로 html태그를 만들어 줄 필요가없다. </li>
<li> 이벤트 등록을 한 컴포넌트에 한번에 할 수 있다.</li>
<li> 어떤 코드인지 한눈에 들어온다.</li>
</ul>

<h3>React Js</h3>

```
<body>
    <div id="root"></div>
</body>
<script src="https://unpkg.com/react@17.0.2/umd/react.production.min.js"></script> <!-- React JS 상호작용의 원동력 -->
<script src="https://unpkg.com/react-dom@17.0.2/umd/react-dom.production.min.js"></script> <!-- ReactDOM React element를 가져다가 HTML로 바꾸는 역할 -->
<script src="https://unpkg.com/@babel/standalone@7.22.10/babel.min.js"></script>
<script type="text/babel">

 // 쉬운방식으로 코딩
    const root = document.getElementById("root");
    const Title = () => (
        <h3 id="title" onMouseEnter={() => console.log("mouse enter")}>
            Hello I'm a Span
        </h3>
    );
    const Button = () => (
        <button
            style={{
                backgroundColor: "tomato",
            }}
            onClick={() => console.log("i'm clicked")}>
            Click me
        </button>
    );
    const CONTAINER = () => (  // 만든 컴포넌트는 대문자로 만들어줘야함
        <div>
            <Title />
            <Subtitle />
        </div>
    );
    ReactDOM.render(<CONTAINER />, root); // React span element를 id="root"인 안에 html로 만들어 배치
```

<h3>Vanilla JS</h3>

```
<body>
    <span>Total clicks : 0</span>
    <button id="btn">Click me</button>
</body>

    let counter = 0;
    const span = document.querySelector("span");
    const button = document.getElementById("btn");
    function handleClick(){
        counter = counter + 1;
        span.innerText = `Total Clicks : ${counter}`;
    }
    button.addEventListener("click", handleClick );
```