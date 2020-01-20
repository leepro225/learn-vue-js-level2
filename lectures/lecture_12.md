# 템플릿 문법 - 실전

### watch 속성

      <div id="app">
        {{ num }}
        <button v-on:click="addNum">increase</button>
      </div>
      <script>
        new Vue({
          el: '#app',
          data: {
            num: 10
          },
          watch: { 
            num: function() { // num을 감시하다가 바뀌면 아래 로직을 실행함
              this.logText();
            }
          },
          methods: {
            addNum: function() {
              this.num = this.num + 1;
            },
            logText: function() {
              console.log('changed');
            }
          }
        })
      </script>
      
      
  watch 속성과 computed 속성 차이점에 관한 공식 문서 링크 : https://vuejs.org/v2/guide/computed.html#ad
  
  
### watch와 computed의 차이

      <div id="app">
        {{ num }}
      </div>
      <script>
        new Vue({
          el: '#app',
          data: {
            num: 10
          },
          computed: {
            doubleNum: function() {
              return this.num * 2;
            }
          },
          watch: {
            num: function(newValue, oldValue) {
              this.fetchUserByNumber(newValue);
            }
          },
          methods: {
            fetchUserByNumber: function(num) {
              // console.log(num);
              axios.get(num);
            }
          }
        });
      </script>
      
#### computed
가볍고, 즉각적 데이터 반영, 캐싱

#### watch

function의 인자값으로 (새로운값, 기존값)을 받을 수 있음. 받은 값으로 api를 요청한다던지 어떤 로직을 수행하는데 적합.
조금 더 복잡하고 무거운 느낌쓰




### computed를 이용한 클래스 바인딩 방법 

  <style>
     .warning {
        color: red;
     }
  </style>
  <div id="app">
    <p v-bind:class="{ warning : isError }">Hello</p> // ture면 warging이라는 class를 넣는다.
    <p v-bind:class="errorTextColor">Hello</p> // computed 속성을 이용하기
  </div>
  <script>
    new Vue({
      el: '#app',
      data: {
        isError: false
      },
      computed: {
        errorTextColor: function() {
          return this.isError ? 'warning' : null;
        }
      }
    });
  </script>







