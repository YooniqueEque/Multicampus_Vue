<template>
    <div>
        <h1> {{number}} </h1>
        <button @click="increase()">증가</button>
        <button @click="decrease()">감소</button>
        <!-- <button @mouseover="init()">초기화</button> -->
        <button v-if="number>10">초기화</button>

        <h3>{{now()}}</h3>
        <h3>{{nowComputed}}</h3>
        <h3>{{increaseComputed}}</h3>
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

        methods : { //변수값이 변경되면 렌더링되면서 메소드의 함수들이 다 호출됨
            //메소드명 : {동작}
            increase(){this.number += 1},
            decrease(){this.number -= 1},
            init(){this.number = 0; alert(this.number);},
            //init=()=>{this.number = 0; alert(this.number);}   
            /* vue는 메소드 안에서 컴포넌트 인스턴스를 항상 참조할 수 있도록 this 값을 자동 바인딩.
            이렇게 하면 메서드가 이벤트 리스너나 콜백으로 사용될 때, 올바른 this값을 유지하게 됨
            화살표 함수를 사용해서 메소드를 정의하면 vue가 적절한 this 값을 바인딩 하지 못함
            this가 필요하면 메소드를 정의할 때 화살표함수 사용하지 말 것. */

            now(){
                return new Date().toLocaleString();
            }
        },

        computed : { //메소드 나열 (최초 호출시의 값을 고정시킴)
            nowComputed(){
                return new Date().toLocaleString();
            }  ,
            increaseComputed(){ //값변경 문장 사용 불가, 변경값을 확인하는 것만 가능
                return this.number;
            } 
        }
    }
</script>

<style>
    h1 {color : green;}
</style>