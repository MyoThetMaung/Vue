<template>
    <div class="backdrop" @click.self="close">
        <div class="modal" :class="{green:theme==='success',orange:theme==='fail'}">
            <slot></slot>                                                               <!--default slot area-->
            <slot name="link"></slot>                                                   <!--custom slot area-->
        </div>
    </div>
</template>

<script>
export default {
    props:['theme'],
    methods:{
        close(){
            this.$emit('close');
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