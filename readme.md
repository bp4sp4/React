# ReactJS 로 영화 웹 서비스 만들기
<h1>ReactJS 2일차<br>23.08.13</h1>
<h2>시간 <-> 분</h2>
<pre>
<code>
function App() { 
        const [amount, setAmount] = React.useState(0);
        const [flipped, setFlipped]= React.useState(false);
        const onChange = (event) => {
            setAmount(event.target.value);
        }
        const reset = () => setAmount(0);
        const onFlip = () => {
            reset();
            setFlipped((current) => !current);
        }
        return (
        <div>
            <h1>Super Converter</h1>
            <div><label for="minutes">Minutes</label>
            <input 
            value={flipped ? amount*60 : amount } 
            id="minutes" 
            placeholder ="Minutes"  
            type="number"
            onChange={onChange}
            disabled = {flipped}
            />
            </div>
            <div>
            <label for="hours">Hours</label>
            <input 
            value={flipped ? amount : Math.round(amount / 60)}
            id="hours" 
            placeholder ="Hours" 
            type="number"
            disabled={!flipped}
            onChange={onChange}
            />
            </div>
            <button onClick={reset}>Rest</button>
            <button onClick={onFlip}>Filp</button>
        </div>
        )
    };
    const root = document.getElementById("root");
    ReactDOM.render(<App />,  root);  // React span element를 id="root"인 안에 html로 만들어 배치
</code>
</pre>

<h2>아직 웹서비스 만들기 전 기초문법</h2>
<pre><code>
   const root = document.getElementById("root");
    function App() { 
        const [counter, setCounter] = React.useState(0); // 배열을 만들어줌 첫번쨰요소 counter 두번째요소 modifier
        const onClick = () => { // state를 바꿔주는 두가지 방법
        //    setCounter(counter +1);
        setCounter((current) => current + 1);
        };
        return (
        
        div
           h3Total clicks : {counter}/h3
            button onClick={onClick}>Click me /button
        /div
        )
    };
    ReactDOM.render(<App />,  root);  // React span element를 id="root"인 안에 html로 만들어 배치

</code></pre>

<h1>ReactJS 1일차<br>23.08.12</h1>
<h3>ReactJs JS 차이점</h3>
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