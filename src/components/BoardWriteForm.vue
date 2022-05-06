<template>
    제목 : <input type="text" id="title" @input="inputHandler"/>
    작성자 : <input type="text" id="writer" @input="inputHandler"/>
    
    <button @click="writeHandler">글쓰기</button>
</template>

<script>
export default {
    name : "BoardWriteForm",
    data(){
        return{
            writeboard : {
                title : "",
                writer : ""
            }  
        }
       
    },
    methods : {
        inputHandler(e){
            {this.writeboard[e.target.id] = e.target.value;}
        },
        writeHandler(){
            this.$emit("writeFromChild", this.writeboard.title, this.writeboard.writer);
        }
    }
}
</script>

<style>
    button{
        background-color: olive;
    }
</style>