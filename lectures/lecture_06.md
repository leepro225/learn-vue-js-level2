# event emit 개념

### event emit (자식이 부모에게 이벤트 방출하고 부모가 받기)

    <div id="app">
        // <app-header v-on:하위컴포넌트에서 발생한 이벤트 이름="상위 컴포넌트의 메서드"></app-header>
           <app-header v-on:pass="logText"></app-header>
    </div>
    <script>
        const appHeader = {
                     // <button v-on:click="메서드명">header</button>'
            template : '<button v-on:click="passEvent">header</button>',
            methods : {
                passEvent : function() {
                    this.$emit('pass');
                }
            }
        }

        new Vue({
            el : '#app',
            components : {
                'app-header' : 'appHeader'
            },
            methods : {
                logText : function() {
                    console.log('say hi'); // 하위 버튼 클릭시 상위 이벤트 발생
                }
            }
        });
    </script>
    
 emit은 자식이 부모로 데이터를 보낼때 사용  
 버튼을 클릭하면 passEvent라는 메서드를 실행, 안을 들어가보니 pass라는 메서드를 실행하라고 함.  




### event logging

![04](./img/04.JPG)

이벤트 이력(logging)을 확인할 수 있는 탭  
<app-header>컴포넌트로부터 pass라는 이벤트가 발생했다는 뜻



