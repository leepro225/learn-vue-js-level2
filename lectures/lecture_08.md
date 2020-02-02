# const and let 새로운 변수 선언 방식

### const & let

 - 블록단위의 변수선언 방식
 - const : 한번 선언한 값에 대해서 변경할 수 없음(상수 개념)
 - let : 한번 선언한 값에 대해서 다시 선언할 수 없음


### ES5의 특징 - 변수의 scope
 
 - 기존 자바스크립트(ES5)는 {} 에 상관없이 스코프가 설정됨
 
    var sum = 0;
    for (var i =1; i <= 5; i++) {
       sum = sum + i;
    }
    console.log(sum);
    console.log(i);
  
  
  
### ES5의 특징 - Hoisting

  - Hoisting 이란 선언한 함수와 변수를 해석기가 가장 상단에 있는 것처럼 인식한다.
  - js 해석기는 코드의 라인 순서와 관계 없이 함수선언식과 변수를 위한 메모리 공간을 먼저 확보한다.
  - 따라서, function a() (함수선언문)와 var(변수)는 코드의 최상단으로 끌어올린

    function() willBeOveridden() {
      return 10;
    }
    willBeOveridden(); // 5
    function() willBeOveridden() {
      return 5;
    }
  


