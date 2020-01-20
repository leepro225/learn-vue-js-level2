# 뷰 라우터

####  뷰 라우터 소개와 설치

싱글 페이지 어플리케이션을 구현을 위한 뷰 라이브러리

### NPM 방식 설치

    npm install vue-router
    

### 라우터 연결하기

    <div id="app">
    <div>
        <router-link to="/login"></router-link>
        <router-link to="/main"></router-link>
    </div>
    <router-view></router-view> // new Vue 에서 app에 router를 등록했기때문에 사용가능한 컴포넌트, 이 안에 path에 따라 컴포넌트가 표현된다
    </div>
       
    <script>
        const LoginComponent = {
            template : '<div>login</div>
        }
        const MainComponent = {
            template : '<div>main</div>
        }
        
        const Router = new VueRouter({
            // url에 #없애는 설정값
            mode : 'history', 
            // 페이지의 라우팅 정보(어디로 이동할지에 대한 정보)
            routes : [
                {
                    // 페이지의 url 주소
                    path : '/login',
                    // 해당 url에서 표시될 컴포넌트
                    component : LoginComponent 
                },
                {
                    path : '/main',
                    component : MainComponent
                }                                                       
            ]
        });
        
        new Vue({
            el : '#app',
            router : Router
        });
    </script>
    
router는 methods처럼 기본 내장된 예약어임. 라우터를 인스턴스화 하고  app태그와 연결함.



네비게이션 가드 : https://joshua1988.github.io/web-development/vuejs/vue-router-navigation-guards/




