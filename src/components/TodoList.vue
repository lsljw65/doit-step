<template>
    <section>
        <transition-group name="list" tag="ul">
            <li v-for="(todoItem,index) in propsdata" :key="todoItem" class="shadow">
                <i class="checkBtn fas fa-check" aria-hidden="true"></i>
                {{ todoItem }}
                <!-- <span class="removeBtn" type="button" @click="removeTodo">
                    <i class="far fa-trash-alt" aria-hidden="true"></i>
                </span> -->
                <span class="removeBtn" type="button" @click="removeTodo(todoItem,index)">
                    <i class="far fa-trash-alt" aria-hidden="true"></i>
                </span>
                
            </li>
        </transition-group>
    </section>
</template>
<script>
export default{
    props:['propsdata'],
    /* data(){
        return{
            todoItems:[]
        }
    }, */
    /* created(){
        if(localStorage.length > 0){
            for (var i=0; i<localStorage.length; i++){
                this.todoItems.push(localStorage.key(i));
            }
        }
    }, */
    methods:{
        removeTodo(todoItem,index){
            // console.log("clicked")
            // console.log(todoItem,index)
            // localStorage.removeItem(todoItem);
            // this.todoItems.splice(index,1);
            this.$emit('removeTodo',todoItem, index)
        }
    }
    
    
}
</script>

<style>
    section{
        width:98%;
        margin:auto;
    }
    ul{
        list-style-type:none;
        padding-left:0;
        margin-top:0;
        text-align:left;
    }
    li{
        display:block;
        display:flex;
        height:50px;
        min-height:50px;
        line-height:50px;
        margin:0.5rem 0;
        padding:0 0.9rem;
        background:white;
        border-radius:5px;
    }
    .checkBtn{
        line-height:45px;
        color:#62acde;
        margin-right:5px;
    }
    .removeBtn{
        margin-left:auto;
        color:#de4343;
    }
    /* transition-group 추가 */
    .list-item {
        display: inline-block;
        margin-right: 10px;
    }
    .list-move {
    transition: transform 1s;
    }
    .list-enter-active, .list-leave-active {
    transition: all 1s;
    }
    .list-enter, .list-leave-to {
        opacity: 0;
        transform: translateY(30px);
    }

</style>