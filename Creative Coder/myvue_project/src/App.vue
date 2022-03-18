<template>
    <h1 ref="change">Click Anyone</h1>
    <button @click="modal()"> Show Modal </button>
    <button @click="modal2()"> Show Modal2 </button>
    <div v-if="showModal" >
        <Modal :header="header" content="content" :theme="theme" @close="showModal=false">
            <h1>Login Success</h1>
            <h3>Welcome to David</h3>
            <template v-slot:link>                                                          <!--if want to call, use links-->
                <button>Log In</button> 
                <button>Register</button> 
            </template>
        </Modal>
    </div>

    <div v-if="showModal2" >
        <Modal2 :header2="header2" :content2="content2" :theme2="theme2" @close2="showModal2=false">
            <template v-slot:link2>                                                          <!--if want to call, use links-->
                <button>Log In</button> 
                <button>Register</button> 
            </template>
        </Modal2>
    </div>
</template>

<script>
import Modal from "./components/Modal.vue"
import Modal2 from "./components/Modal2.vue"
export default {
    data(){
        return {
            name : 'David',
            header: 'Login Success',
            content: 'Welcome to David',
            theme : "fail",
            showModal: false,

            name2 : 'John',
            header2: 'Please Log in',
            content2: 'Welcome to John',
            theme2 : "success",
            showModal2: false,
        }
    },
    methods:{
        changeName(){
            return this.$refs.change.innerText = "I am david"
        },
        modal(){
            this.showModal = true
        },
        modal2(){
            this.showModal2 = true
        }
    },
    components:{
        Modal, Modal2
    }
}
</script>

<style scoped>
    h1{
        color:red;
    }
    button{
        margin: 20px;
    }
</style>