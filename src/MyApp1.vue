<template>
    <div>
        <img :src="logofile" :alt="logoname" />
        <!-- 콧수염괄호(mustache태그) {{}} -->
        <h1> {{name}} </h1>
        <p v-bind:style="style1"> {{age}}세입니다.</p>
    </div>
</template>

<script>
    export default {
        name : "MyApp1",
        data() {
            return {
                name : "방국봉",
                age : 30,
                style1 : "color:pink",
                logoname : "로고",
                logofile : require("./assets/logo.png")
            }//리턴 객체 내부 변수
        }//함수 end
    }
</script>

<style>
    h1 {color : green;}
</style>