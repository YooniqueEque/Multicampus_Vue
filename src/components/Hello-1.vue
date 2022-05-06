<template>
    <div>{{title}} 컴포넌트</div>
    <div>{{name}}</div>
    <div>{{number}}</div>
    <div>자식태그에서 수정 <input type="text" :value="number" @input="increase"></div>
</template>

<script>
export default {
    name:"MyHello1",
    data : function(){
        return{
            title : "MyHello1"
        }
    },
    props : {
        name : {type : String},
        number : {type : Number/* , required:false, default:-1 */}
    },
    methods : {
        increase(e){
            //console.log(e.target.value);

            //입력값 변경을 알려주는 이벤트 정의, 부모에게 전달, 부모가 변경
            //this.$emit("이름설정", 변경값)
            this.$emit("setNumberFromChild", e.target.value);
        }
    }
}
</script>

<style>
    div{
        color : olive;
        font-size : 20px;
    }
</style>