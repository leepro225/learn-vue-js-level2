# 싱글파일 컴포넌트

### emit로 데이터 보내기

#### 자식 컴포넌트

      <template>
        <header>
          <h1>{{ propsdata }}</h1>
          <button v-on:click="sendEvent">send</button>
        </header>
      </template>

      <script>
      export default {
        props: ['propsdata'],
        methods: {
          sendEvent: function() {
            this.$emit('renew'); // renew 상위로 보낼 이벤트의 이름
          }
        }
      }
      </script>

 
 #### 부모 컴포넌트
 
      <template>
        <div>
          <app-header 
            v-bind:propsdata="str"
            v-on:renew="renewStr"></app-header> // v-on:하위에서 받은 emit의 이름="상위의 메소드 명"
        </div>
      </template>

      <script>
      import AppHeader from './components/AppHeader.vue';

      export default {
        data: function() {
          return {
            str: 'Header'
          }
        },
        components: {
          'app-header': AppHeader
        },
        methods: {
          renewStr: function() {    // renew를 받아 renewStr을 실행하겠쥬
            this.str = 'hi';        // 이게 실행되면 propsdata로 하위로 데이터를 보낼테니 화면에서 값이 바뀐다~
          }
        }
      }
      </script>


      


