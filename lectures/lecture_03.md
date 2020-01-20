# 컴포넌트 개념 

### 컴포넌트
    
재사용성을 올리기 위해 화면의 영역을 나누어 컴포넌트 단위로 코드를 개발  
컴포넌트 간의 관계가 생긴다


### 전역 컴포넌트 등록

    <div id="app">
        <app-header></app-header>
    </div>
    
    Vue.component('app-content', {
        template : '<h1>Header</h1>'
    });
    
    new Vue({
        el : '#app'
    });
    
실무에서는 잘 쓰지 않음!





### 지역 컴포넌트 등록

    new Vue({
        el : '#app',
        components : {
            // '컴포넌트 이름' : 컴포넌트 내용
            'app-footer' : {
                template : '<footer>something</footer>
            }
        }
    });





### 전역 컴포넌트와 지역 컴포넌트의 차이점

전역 : 플러그인이나 라이브러리의 개념으로 전역에서 사용하고 싶을 때   
지역 : components 안에 여러개 사용, 그 컴포넌트 파일 안에서 사용하고 싶을 때





### 컴포넌트와 인스턴스와의 관계


