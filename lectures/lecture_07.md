# 뷰에서의this

### object안에서의this는 object를 가리킨다.

    const obj = {
        hi : 'hello',
        greeting : function() {
            console.log(this.hi);
        }
    }

마찬가지로 vue 인스턴스도 객체니까 this는 vue를 가리킨다.   
  
참고 : https://www.w3schools.com/js/js_this.asp  
https://medium.com/better-programming/understanding-the-this-keyword-in-javascript-cb76d4c7c5e8





