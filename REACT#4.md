### REACT#4
> Props
```javascript
// 상위 컴포넌트인 App에서 데이터를 받아서
// 하위 컴포넌트인 Btn에 데이터를 전송하는 props
<script type="text/babel">
    // 인자를 받을 때 상위 컴포넌트의 이름을 그대로 가져와야 된다
	function Btn({text, onClick}){
		console.log(text)
		return (<button 
		onClick={onClick}
		style={{
			backgroundColor:'tomato',
			color:'white',
			padding:"10px 20px",
			border:0,
			borderRadius:10
		}}>{text}</button>)
	}

    // propTypes를 이용하면 각각의 컴포넌트에 들어갈 변수들의 타입들을 정할 수 있다
	Btn.propTypes = {
		text : PropTypes.string.isRequired
	}

    // React.memo 를 이용하면 그 컴포넌트의 변경 사항이 없고 다른 컴포넌트만 변경 사항이 있을 때
    // 변경되는 컴포넌트만 랜더링하게 된다

	const MemorizedBtn = React.memo(Btn)
	function App(){
		const [value,setValue] = React.useState('Save Changes')
		const changeValue = () => setValue("Revert Changes")
		return (
			<div>
                // text에 넣고 싶은 값을 넣어준다
                // onClick 처럼 함수도 가능하다
				<MemorizedBtn text={value} onClick={changeValue}/>
				<MemorizedBtn text="Continue" />
			</div>
	)}
	const root = document.getElementById('root')
	ReactDOM.render(<App />, root)
</script>

```