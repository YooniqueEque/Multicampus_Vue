<template>
    <div>
        <h1>
            <ul>
                <li v-for="(m, i) in menus" v-bind:key="m"> {{1+i}}번째 메뉴 : {{m}} </li>
            </ul>
        </h1>
    </div>
</template>

<script>
    export default {
        name : "MyApp2",
        data() {
            return {
                menus : ["home", "boardlist", "board"]
            }//리턴 객체 내부 변수
        }//함수 end
    }
</script>

<style>
    h1 {color : green;}
</style>