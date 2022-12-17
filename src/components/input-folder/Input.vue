<template>
    <form action="#" class="form-group" @submit.prevent>

        <div class="input-box  d-flex justify-content-center mt-5">

            <input type="text" placeholder="firstname" class="form-control" v-model="name" />

            <input type="text" placeholder="lastname" class="form-control" v-model="lname" />

            <input type="email" placeholder="email" class="form-control" v-model="email" />

        </div>

         <div class="btn-box d-flex justify-content-center my-4">
            <button  @click="addForm" class="btn btn-outline-success">Submit</button>
            <button @click="add" class="btn btn-outline-primary" 
            >Update</button>
        </div>

    </form>
</template>

<script>
export default {
    name: 'Input',
    data() {
        return {
            name:'',
            email:'',
            lname:'',
            id: this.forms.length
        }
    },
    props:{
        forms:{
            type: Array,
            required: true
        },
        users:{
            type: Object,
            required: true
        },
        updateUser:{
            type: Function,
            required: true
        }
    },
    methods: {
        addForm() {
            if(this.users.isUser === true){
                let findUser = this.forms.find(user => user.id == this.users.userId)
                findUser.name = this.name,
                findUser.lname = this.lname,
                findUser.email = this.email
                this.users.isUser = null,
                this.users.userId =  false 
                this.lname = '';
                this.name = '';
                this.email = ''; 

                return
            }
            
            else if(this.name == '' || this.email == '' || this.lname == ''){
                alert('Bo\'sh Maydonni To\'ldiring Iltimos')
                return
            }else{
            }
            const item = {
                name : this.name,
                email : this.email,
                lname : this.lname,
                id : this.forms.length+1
            }
            this.$emit('newForm',item)
            this.lname = '';
            this.name = '';
            this.email = '';                
        },  
        add() {
            if(this.users.name == '' || this.users.lname == '' || this.users.email == ''){
                alert('Itemni Updateni Tugmasini Bosing Iltimos!!!')
            }else{
                this.name = this.users.name
                this.lname = this.users.lname
                this.email = this.users.email
            }
        },
    },  
}
</script>

<style scoped>
    /* Input Validation Start */
    input {
        padding: .5rem 2rem;
        margin-left: 1rem;        
        border-radius: 0 1rem 0 1rem;
        transition: .555555s;        
        color: red;
    } 
    input:focus{
        border-radius: 1rem 0 1rem 0;
    }
    /* Input Validation End */
    
    /* Box Start */
    .btn{
        padding: .5rem 6rem;
        margin-left: 1rem;
        position: relative;
        top: 1.5rem;
    }
    .input-box{
        width: 100%;
        height: 7vh;
        margin: 0 auto;
    }
    /* Box End */
</style>