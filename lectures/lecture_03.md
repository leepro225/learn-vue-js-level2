# v-for 

### v-for를 이용해 리스트 뿌리기
    
    <template>
      <div>
        <ul>
          <li v-for="todoItem in todolist" v-bind:key="index">
            <span>{{ todoItem }}</span>
          </li>
        </ul>
      </div>
    </template>

    <script>
    export default {
        props: ['todolist'],
        data() {
                return {
        	        todoItems: []
            };
        },
        methods: {
            fetchTodoItems: function() {
                // 브라우저 저장소의 데이터를 불러오기
                for (var i = 0; i < localStorage.length; i++) {
            	    var item = localStorage.key(i);
           	        this.todoItems.push(item);
                }
                // 서버의 데이터 불러오기
                axios.get();
            }
        },
        // // 컴포넌트가 생성되자마자 실행되는 로직
        created: function() {
            this.fetchTodoItems();
        },
    };
    </script>
    <style>
    </style>
    

