# 컴포넌트 생성 및 등록하기 

### 컴포넌트 생성

    <template>
        <div>Something</div>
    </template>
    <script></script>
    <style></style>


### 컴포넌트 등록

    <template>
        <SomethingComponent></SomethingComponet>
    </template>
    <script>
    import SomethingComponent from'./components/SomethingComponent'
    
    export default {
        components : {
            // 컴포넌트 태그명 : 컴포넌트 내용
            'SomethingComponent' : SomethingComponent
        }
    }
    </script>
    <style></style>

