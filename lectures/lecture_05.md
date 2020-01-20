# props 속성

### props 속성

    <div id="app">
        // <app-header v-bind:프롭스 속성 이름="상위 컴포넌트의 데이터 이름"></app-header>
           <app-header v-bind:propsData="message"></app-header>
    </div>
    <script>
        const appHeader = {
            template : '<h1>header</h1>',
            props : ['propsData']
        }

        new Vue({
            el : '#app',
            components : {
                'app-header' : 'appHeader'
            },
            data : {
                message : 'hi'
            }
        });
    </script>
    
 ### props 속성의 특징
    
 v-bind로 상위 컴포넌트의 데이터를 물려 받음.
 따라서 상위 컴포넌트의 data인 message의 내용이 바뀌면 하위 컴포넌트의 data도 바뀐다.







