# 인스턴스 개념 

### 인스턴스 new Vue()
    function Vue() {
      this.logText = function() {
        console.log('hello');
      }
    const vm = new Vue();
    
    vm.logText(); // hello
    
vue안의 내장 객체들을 사용하기 위해 인스턴스를 생성한다.
인스턴스를 생성하면 화면에 Root컴포너트가 생긴다. 뷰 인스턴스 하나 = 루트 컴포넌트 하나



    const options = {
      el : '#app', // app 안에서 뷰를 사용하겠다는 뜻
      data : {
        message : 'hi'
      }  
    }
    const vm = new Vue(options);
 
생성한 뷰 인스턴스 안은 객체!





### 인스턴스 속성

    new Vue({
        el : ,
        template : ,
        data : ,
        methods : ,
        created : ,
        watch : ,
    });
    
 el : 인스턴스가 그려지는 화면의 시작점 (특정 HTML 태그)  
 template : 화면에 표시할 요소(HTML, CSS 등)  
 data : 뷰의 반응성(Reactivity)가 반영된 데이터 속성  
 methods : 화면의 동작과 이벤트 로직을 제어하는 메서드  
 created : 뷰의 라이프 사이클과 관련된 속성  
 watch : data에서 정의한 속성이 변화했을 때 추가 동작을 수행할 수 있게 정의하는 속성  

