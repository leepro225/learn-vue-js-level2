# mapMutations, mapActions

### 헬퍼의 유연한 문법
 - Vuex에 선언한 속성을 그대로 컴포넌트에 연결하는 문법
 
       // 배열 리터럴
       ...mapMutations([
        'clickBtn', // 'clickBtn' : clickBtn
        'addNumber' // addNumber(인자)
       ])
       
 - vuex에 선언한 속성을 컴포넌트의 특정 메서드에다가 연결하는 문법
       
       // 객체 리터럴
       ...mapMuations({
         popupMsg: 'clickbtn' // 컴포넌트 메서드 명 : Store 의 뮤테이션 명
       })
       
 

