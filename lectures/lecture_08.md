# 같은 레벨의 컴포넌트간의 데이터 통신 방법

### 부모로 보내고 다시 받고, 중간에 data를 통해서

![06](./img/05.JPG)


   <div id="app">
       <app-header v-bind:propsdata="num"></app-header>
       <app-content v-on:pass="deliverNum"></app-content>
     </div>

     <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
     <script>
       var appHeader = {
         template: '<div>header</div>',
         props: ['propsdata']
       }
       var appContent = {
         template: '<div>content<button v-on:click="passNum">pass</button></div>',
         methods: {
           passNum: function() {
             this.$emit('pass', 10);
           }
         }
       }
       new Vue({
         el: '#app',
         components: {
           'app-header': appHeader,
           'app-content': appContent
         },
         data: {
           num: 0
         },
         methods: {
           deliverNum: function(value) {
             this.num = value;
           }
         }
       })
     </script>

   





