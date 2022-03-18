<template>
    <div class="backdrop" @click.self="close2">
        <div class="modal" :class="{green:theme==='success',orange:theme==='fail'}">                          
            <h1>{{header2}}</h1>
            <h3>{{content2}}</h3>
            <slot name="link2"></slot>                                                   <!--custom slot area-->
        </div>
    </div>
</template>

<script>
export default {
    props:['header2','content2','theme2'],
    methods:{
        close2(){
            this.$emit('close2');
        }
    }
}
</script>

<style>
    .backdrop{
        position: fixed;
        top:0;
        background-color: grey;
        width: 100%;
        height: 100%;
        text-align: center;
    }
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background-color: white;
        border-radius: 10px;
    }
    .green{
        color: white;
        background: green;
    }
    .orange{
        color: white;
        background: orange;
    }
</style>