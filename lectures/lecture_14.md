# 싱글파일 컴포넌트

### data

      <script>
      export default {
        data: function() {
                  return { // 꼭 데이터라는 function의 return값으로 사용해야한다.
                  }        // data : {}이러케 해버리면 다른 컴포넌트들에서도 참고가 가능해져 에러가 발생하기 때문
            }
      }
      </script>
      
      
### 컴포넌트 등록하기

      <AppHeader></AppHeader>
      
컴포넌트명은 두 단어 이상조합, 파스칼 케이스로 권장한다. 이렇게 안하면 브라우저가 기존의 html태그와 구분이 어렵다.



      <template>
        <div>
          <app-header></app-header>
        </div>
      </template>

      <script>
      import AppHeader from './components/AppHeader.vue';
      
      export default {
        components: {
          'app-header': AppHeader
        }
      }
      </script>

