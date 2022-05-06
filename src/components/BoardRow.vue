<template>
    <tbody>
        <tr v-for="(oneboard) in board" :key="oneboard.seq">
            <td>{{oneboard.seq}}</td>
            <td>{{oneboard.title}}</td>
            <td>{{oneboard.writer}}</td>
            <td>{{oneboard.viewcount}}</td>
            <td><button @click="updateHandler" :id="oneboard.seq">수정</button></td>
            <td><button @click="deleteHandler" :id="oneboard.seq">삭제</button></td>
        </tr>
    </tbody>

</template>

<script>
export default {
    name : "BoardVue",
    props : {
        board : {type:Array}
    },
    methods : {
        deleteHandler(e){
            this.$emit("deleteFromChild", e.target.id);
        },
        updateHandler(e){
            this.$emit("updateFromChild", {seq:e.target.id, title:"수정", writer:"수정", viewcount:0});
        }
    }
}
</script>

<style>
    th{
        border : 1px solid gray;
        width : 100px;
    }
</style>