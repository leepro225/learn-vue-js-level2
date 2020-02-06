# Vuex 기술 요소

- state : 여러 컴포넌트에 공유되는 데이터 data  
- getters : 연산된 state 값을 접근하는 속성 computed  
- mutations : state 값을 변경하는 이벤트 로직과 메서드 methods  
- actions : 비동기 처리 로직을 선언하는 메서드 async methods -->api call할때 사용   


### state 란?

- 여러 컴포넌트 간에 공유할 데이터 - 상태  

      // Vue  
      data : {
            message : 'Hello Vue.js!'
      }
      
      // Vuex  
      state : {
            message : 'Hello Vue.js!'
      }
      
      // 접근방법
      
      <!-- Vue -->
      <p>{{ message }}</p>
      
      <!-- Vuex -->
      <p>{{ this.$store.state.message }}</p>
      
      
### getters 란?
 - state값을 접근하는 속성이자 computed() 처럼 미리 연산된 값을 접근하는 속성
 
            // store.js
            state : {
                  num : 10
            },
            getters : {
                  getNumber(state) {
                        return state.num;
                  },
                  doubleNumber(state) {
                        return state.num * 2;
                  }

            }

            // 접근 방법
            <p>{{ this.$store.getters.getNumber }}</p>
            <p>{{ this.$store.getters.doubleNumber }}</p>

      
- 나중에 배우게될 헬퍼함수로 축약해서 접근 가능  



### mutations 란?

 - state의 값을 변경할 수 있는 유일한 방법이자 메서드  
 - 뮤테이션은 commit()으로 동작시킨다.
 
          // store.js
          state : { num : 10},
          mutations : {
                printNumbers(state) {
                      return state.num
                },
                sumNumbers(state, anotherNum) {
                      return state.num + anotherNum;
                }
          }

          // App.vue
          this.$store.commit('printNumbers');
          this.$store.commit('sumNumbers', 20);

### mutations의 commit() 형식
 - state를 변경하기 위해 mutations를 동작시킬 때 인자(payload)를 전달할 수 있음  
 
     // store.js
     state : { storeNum : 10 },
     mutations : {
           modifyState(state, payload) {
                 console.log(payload.str);
                 return state.storeNum += payload.num;
           }
     }
      
     // App.vue
     this.$store.commit('modifyState', {
           str : 'passed from payload',
           num : 20
     });



