<template>
    <div>
        <h1> {{number}} </h1>
        <button @click="increase()">증가</button>
        <button @click="decrease()">감소</button>
        <!-- <button @mouseover="init()">초기화</button> -->
        <button v-if="number>10">초기화</button>
    </div>
</template>

<script>
    export default {
        name : "MyApp3",
        data() {
            return {
               number : 0
            }//리턴 객체 내부 변수
        },//함수 end

        methods : {
            //메소드명 : {동작}
            increase(){this.number += 1},
            decrease(){this.number -= 1},
            init(){this.number = 0; alert(this.number);}
            //init=()=>{this.number = 0; alert(this.number);}   
        }
    }
</script>

<style>
    h1 {color : green;}
</style>