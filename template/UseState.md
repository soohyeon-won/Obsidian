예제
```
const PracticeComp = () => {
const { width, height } = useWindowSize();
const [ isOn, setToggle ] = useState(true);
const toggleBtn = () => setToggle(!isOn)

const [price, setPrice] = useState(0);
const incrementPrice = (price: number) => {
setPrice((prevValue) => prevValue + price);
};

const [ titleText, setText ] = useState("placeholder");
const setTitle = (text: string) => {
console.log(text);
setText(text);
};

const [ savedText, setSavedText ] = useState("");
const setSavedTitle = () => setSavedText(titleText);

return <div>
<p>1. useState를 이용한 Toggle버튼</p>
<button onClick={toggleBtn}>{isOn ? "ON":"OFF"}</button>
<br></br>

<p>2. 버튼에 있는 값 input으로 옮기기</p>
<button onClick={() => incrementPrice(10)}>10+</button>
<button onClick={() => incrementPrice(50)}>50+</button>
<input value={price}></input>

<p>3. input Text 저장하기</p>
<input onChange={(input) => setTitle(input.target.value)}></input>
<p>{titleText}</p>
<button onClick={setSavedTitle}>저장</button>
<p>{savedText}</p>
</div>

}
```