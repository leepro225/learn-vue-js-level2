# 뷰 소개 

### 뷰란 무엇인가
![01](./img/01.JPG)

View - 사용자가 보는 html 화면, 사용자에 의해 특정 이벤트가 발생하면 
ViewModel의 DOM Listeners가 청취하다가 이벤트를 받아 자바스크립트에 있는 특정 데이터를 바꿔주거나 자바스크립트 로직을 실행하게 된다. 

Model - 자스의 데이터가 변했을 때 데이터 바인딩을 통해 View에 반영한다.





### 일반적인 자스 개발
리액트, 뷰 등을 사용하지 않고 개발한다면, 돔 타겟을 잡고 innerHtml을 이용해 데이터를 바꿈.  
사용자 인터렉션이 일어나 나중에 데이터가 변경된다면 다시 한번 innerHtml을 이용해 데이터를 바꿈. 두번 일함. 중복 코드.





### 뷰의 핵심 reactivity를 자스로 구현

    Object.defineProperty(viewModel, 'str', {
      // 속성에 접근했을 때의 동작을 정의
      get: function() {
        console.log('접근');
      },
      set: function(newValue) {
        console.log('할당', newValue);
        div.innerHTML = newValue; // 데이터 바인딩
      }
    })






### 위 코드를 라이브러리화 하기

    (function() {
        function init() {
            Object.defineProperty(viewModel, 'str', {
              // 속성에 접근했을 때의 동작을 정의
              get: function() {
                console.log('접근');
              },
              set: function(newValue) {
                console.log('할당', newValue);
                div.innerHTML = newValue; // 데이터 바인딩
              }
        }
        
        function render(value) {
            div.innerHTML = value;
        }
        
        init();
    })();
    
이런식으로 라이브러리들은 즉시 실행함수에 코드를 넣어 유효 범위 안에 가둬둠
