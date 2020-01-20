# 싱글파일 컴포넌트

### props로 데이터 내리기

#### 부모 컴포넌트

      <template>
      <div>
          <!-- <app-header v-bind:프롭스 속성 이름="아래로 내릴 상위 컴포넌트의 데이터 이름"></app-header> -->
          <app-header v-bind:propsdata="str"></app-header>
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
        }
      }
      </script>

 오른쪽이 현재 파일의 데이터, 왼쪽이 하위로 내렸을 때 프롭스 이름
 
 #### 자식 컴포넌트
 
      <template>
        <header>
          <h1>{{ propsdata }}</h1>
        </header>
      </template>

      <script>
      export default {
        props: ['propsdata'],
      }
      </script>

프롭스 속성을 배열로 받아 사용하면 됨!!!
      


