### REACT#2
the basic of react

```javascript
  const btn = React.createElement("button",{
    style:{backgroundColor: 'tomato'},
    onClick:() => console.log('cLick')
  },"Click me")

  createElement('tag',{각종 id,classname, style, 함수 등등등}, {innertext, 내용 등등등})
  ```

```javascript
  ReactDOM.render(container,root)
  // React element들을 root div 안에서 보여주라는 뜻
  ```

# JSX
- 자바스크립트를 확장한 문법
- 생긴건 HTML이랑 비슷함
- JSX자체만으로는 브라우저가 인식을 못함
  - 그래서 babel을 이용해 변환 시켜줘야 됨
