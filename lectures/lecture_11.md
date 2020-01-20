# 템플릿 문법 - 기본

###  데이터 바인딩과 디렉티브
뷰 템플릿 문법 : 화면을 조작하는 방법을 의미  
크게 데이터 바인딩과 디렉티브로 나뉜다.  

### 데이터 바인딩
뷰 인스턴스에서 정의한 속성들을 화면에 표시하는 방법. 기본적인 데이터 바인딩 방식으로 콧수염 괄호가 있음  

    <div>{{ message }}</div>
    
    new Vue({
      data : {
        message : 'Hello Vue.js'
      }
    })
    
### 디렉티브
화면 조작에 자주 사용되는 방식들을 모아 디렉티브 형태로 제공. v-가 붙으면 vue가 디렉티브로 인식  
아래의 예처럼 특정 속성 값에 따라 화면의 영역을 표시하거나 표시하지 않을 수 있다.

    <div>
     Hello <span v-if="show">Vue.js</span>
    </div>
    
    new Vue({
     data : {
       show : false
     }
    })
    
    
### 데이터 바인딩과 computed 속성

     <div id="app">
        <p>{{ num }}</p>
        <p>{{ doubleNum }}</p>
     </div>

     <script>
        new Vue({
          el: '#app',
          data: {
            num: 10,
          },
          computed: {
            doubleNum: function() {
              return this.num * 2;
            }
          }
        })
      </script>


computed속성은 data의 변화에 따라 변화하게 될 속성을 정의한다.




### v-bind로 id와 class 바인딩하기

     <div id="app">
        <p v-bind:id="uuid" v-bind:class="name">{{ num }}</p>
     </div>
      <script>
        new Vue({
          el: '#app',
          data: {
            num: 10,
            uuid: 'abc1234',
            name: 'text-blue'
          }
        })
      </script>
   
  id와 class를 데이터에 따라 동적으로 바꾸고 싶을 때 v-bind를 사용한다.
  
  
  
  
  ### v-if, 데이터에 따라 특정 태그를 보여주냐 마냐 할때
  
    <div id="app">
        <div v-if="loading">
          Loading...
        </div>
        <div v-else>
          test user has been logged in
        </div>
    </div>
    
    <script>
        new Vue({
          el: '#app',
          data: {
            loading: true
          }
        })
    </script>
  
 ※ dom에서 완전히 제거됨
 
 
 
 
 ### v-show, 데이터에 따라 특정 태그를 보여주냐 마냐 할때
  
    <div id="app">
        <div v-show="loading">
          Loading...
        </div>
    </div>
    
    <script>
        new Vue({
          el: '#app',
          data: {
            loading: true
          }
        })
    </script>
  
 ※ dom에서 style에 display:none이 추가됨 
 
 
 
 
 
 ### 모르는 문법이 나왔을 때 공식 문서를 보고 해결하는 방법
 
 www.vuejs.org 에서 검색, 예제를 보고 따라하기
 
 
 
 
 ### methods 속성과 click 이벤트
 
      <div id="app">
        <button v-on:click="logText">click me</button>
      </div>
      <script>
        new Vue({
          el: '#app',
          methods: {
            logText: function() {
              console.log('clicked');
            }
          }
        })
      </script>
  
  
  
  
  ### methods 속성과 v-on 디렉티브를 이용한 키보드, 마우스 이벤트 처리 방법
  
      <div id="app">
        <input type="text" v-on:keyup="logText"> // 사용자가 키보드를 누를때마다
        <input type="text" v-on:keyup.enter="logText"> // 사용자가 엔터버튼을 누르면
        <button>add</button>
      </div>
      <script>
        new Vue({
          el: '#app',
          methods: {
            logText: function() {
              console.log('clicked');
            }
          }
        })
      </script>
  
  
keyup. 뒤에 있는 것을 modify라고 함
 
 

 


