<template>
  <!-- Parent Box Start -->
  <div class="content" :class="show ? 'mode' : ''">
    
    <!-- Light mode Dark mode Button Start -->
    <div class="img mt-2">
      <button @click="lightBtn"  class="btn-mode" v-if="show">
        <svg xmlns="http://www.w3.org/2000/svg" height="40" width="40">
          <path
            d="M20 25.167q2.167 0 3.667-1.5t1.5-3.667q0-2.167-1.5-3.667T20 14.833q-2.167 0-3.667 1.5T14.833 20q0 2.167 1.5 3.667t3.667 1.5Zm0 3.166q-3.458 0-5.896-2.437-2.437-2.438-2.437-5.896 0-3.458 2.437-5.896 2.438-2.437 5.896-2.437 3.458 0 5.896 2.437 2.437 2.438 2.437 5.896 0 3.458-2.437 5.896-2.438 2.437-5.896 2.437Zm-16.958-6.75q-.667 0-1.125-.458-.459-.458-.459-1.125t.459-1.125q.458-.458 1.125-.458h3.916q.667 0 1.125.458.459.458.459 1.125t-.459 1.125q-.458.458-1.125.458Zm30 0q-.667 0-1.125-.458-.459-.458-.459-1.125t.459-1.125q.458-.458 1.125-.458h3.916q.667 0 1.125.458.459.458.459 1.125t-.459 1.125q-.458.458-1.125.458ZM20 8.542q-.667 0-1.125-.459-.458-.458-.458-1.125V3.042q0-.667.458-1.125.458-.459 1.125-.459t1.125.459q.458.458.458 1.125v3.916q0 .667-.458 1.125-.458.459-1.125.459Zm0 30q-.667 0-1.125-.459-.458-.458-.458-1.125v-3.916q0-.667.458-1.125.458-.459 1.125-.459t1.125.459q.458.458.458 1.125v3.916q0 .667-.458 1.125-.458.459-1.125.459ZM9.667 11.875 7.5 9.75q-.5-.458-.479-1.125.021-.667.479-1.125.458-.5 1.125-.5t1.125.5l2.125 2.167q.458.458.458 1.104 0 .646-.458 1.104-.417.458-1.063.458-.645 0-1.145-.458ZM30.25 32.5l-2.125-2.167q-.458-.458-.458-1.104 0-.646.458-1.104.458-.5 1.083-.479.625.021 1.125.479L32.5 30.25q.5.458.479 1.125-.021.667-.479 1.125-.458.5-1.125.5t-1.125-.5Zm-2.125-20.625q-.5-.458-.479-1.083.021-.625.479-1.125L30.25 7.5q.458-.5 1.125-.479.667.021 1.125.479.5.458.5 1.125t-.5 1.125l-2.167 2.125q-.458.458-1.104.458-.646 0-1.104-.458ZM7.5 32.5q-.5-.458-.5-1.125t.5-1.125l2.167-2.125q.458-.458 1.104-.458.646 0 1.104.458.5.458.479 1.083-.021.625-.479 1.125L9.75 32.5q-.458.5-1.125.479-.667-.021-1.125-.479ZM20 20Z"
            fill="#cda274"
          />
        </svg>
      </button>
      <button @click="darkBtn" class="btn-mode" v-else>
        <svg xmlns="http://www.w3.org/2000/svg" height="40" width="40">
          <path
            d="M21.25 22.042Zm.583 16.458h-4.75l.584-.5q.583-.5 1.271-1.083.687-.584 1.25-1.084l.562-.5h1.167q3.791 0 7.041-2.125 3.25-2.125 5.125-5.375-3.625-.375-6.937-1.812-3.313-1.438-5.896-3.979-2.583-2.584-4-5.875-1.417-3.292-1.792-6.917-3.291 1.917-5.354 5.083-2.062 3.167-2.104 7v.396q0 .229.042.396l-.48.187q-.479.188-1.062.396-.583.209-1.062.396l-.48.188q-.083-.5-.104-.938-.021-.437-.021-.854 0-6.167 3.959-10.875 3.958-4.708 10.041-5.833-.666 4.125.5 8.083 1.167 3.958 4.167 6.958 2.958 2.959 6.917 4.125 3.958 1.167 8.125.542-1.084 6.125-5.813 10.062Q28 38.5 21.833 38.5ZM10 35.333h7.5q1.208 0 2.042-.833.833-.833.833-2 0-1.208-.813-2.042-.812-.833-1.979-.833h-1.916l-.75-1.792q-.625-1.458-1.959-2.333-1.333-.875-2.916-.875-2.25 0-3.834 1.563-1.583 1.562-1.583 3.77 0 2.25 1.563 3.813Q7.75 35.333 10 35.333Zm0 3.167q-3.542 0-6.042-2.5t-2.5-6.042q0-3.541 2.5-6.02 2.5-2.48 6.042-2.48 2.542 0 4.625 1.354 2.083 1.355 3.125 3.646 2.417.125 4.104 1.854 1.688 1.73 1.688 4.146 0 2.5-1.771 4.271T17.5 38.5Z"
            fill="#cda274"
          />
        </svg>
      </button>
      
    </div>
    <!-- Light mode Dark mode Button End -->

    <!-- Add Form Start  -->
    <div class="main">
      <Input @newForm="newForm" :users="users" :updateUser="updateUser"  :forms="forms"/>
    </div>
    <!-- Add Form End -->

      <!-- User Data Box Start -->
    <div class="add-form mt-5" :class="show ? 'ul-mode': ''">
      <ul class="list-group" >        
        <li class="list-group-item d-flex justify-content-between">
          <span>Id:</span>
          <span>Name:</span>
          <span>Lastname:</span>
          <span>Email:</span>
          <button class="btn btn-outline-primary">Update</button>
          <Button @click="deleteUser(forms.length)">Delete</Button>
        </li>
        <li v-if="forms.length == 0" class="list-group-item">
          <p class="text-center">Odamlar Haqida Ma'lumot Yuq</p>
        </li>

        <li v-for="form in forms" :key="form.id" class="list-group-item d-flex justify-content-between">
          <span> {{form.id}} </span> 
          <span> {{form.name}}</span>
          <span> {{form.lname}}</span> 
          <span> {{form.email}}</span>
          <button @click="updateUser(form.id)" class="btn btn-outline-primary">Update</button>
          <Button @click="deleteUser(form.id)">Delete</Button>
        </li>
      </ul>
    </div>
    <!-- User Data Box End -->

  </div>
  <!-- Parent Box End -->
</template>

<script>
import Input from '../input-folder/Input.vue';
import Button from '../button/Button.vue';
export default {

  /* Data Start */
  data() {
    return {

      forms:[

        {name:"Ozodbek",lname:"Nazarbekov",email:"ozod@gmail.com",id: 1},

        {name:"Javokhir",lname:"Komiljonov",email:"javohir@gmail.com",id: 2},

      ],
      users:{
        name:'',
        lname:'',
        email:'',
        userId: null,
        isUser: false
      },
      show: true
    }
  },
  /* Data End */

  /* Methods Start */
  methods: {
    newForm(item) {
      this.forms.push(item);
    },
    deleteUser(id) {
      if(confirm('Ma\'lumotni O\'chirishga Aminmisiz')){
        this.forms = this.forms.filter(count => count.id !== id)
      }else{
        return
      }
    },
    updateUser(id) {
      let updateUserData = this.forms.find(user => user.id === id)
      this.users.name = updateUserData.name,
      this.users.lname = updateUserData.lname,
      this.users.email = updateUserData.email,
      this.users.userId = updateUserData.id,
      this.users.isUser = true
    },
    darkBtn() {
        this.show = !this.show
    },
    lightBtn() {
      this.show = !this.show
    }
  },  
  /* Methods End */

  /* Components Start */
  components: {
    Input,
    Button
  },
  /*Components End*/

  /* Mounted */
  mounted() {
    alert('Update qilayotganda birinchi Itemni Tugmasini keyin esa submitni yonboshidagi Updateni Tugmasini bosing')
  },
}
</script>

<style>

  /* Content Style Start */
  .content {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin: 0 auto;
  }
  /* Content Style End */

  /* Header Style Start */
  .add-form {
    width: 100%;
    padding: 1.5rem;
    border-radius: 4px;
    box-shadow: 15px 15px 15px rgba(0, 0, 0, .15);
    background: rgb(230, 228, 228);
    color: rgb(65, 211, 131);
    margin: 10rem;
    box-shadow: 0 0  30px 5px rgba(46, 49, 43, 0.411);
  }

  /* Header Style End */

  /* Main Style Start */
  .list-group{
    animation: animate 5s ease-in infinite alternate-reverse;
    background: none;
  }
  
  .list-group-item{
    padding: 15px 20px;    
    animation: animate 3s ease-in infinite alternate-reverse;
    border: none;
    font-size: 1rem;
    border-radius: 1rem;
  }
  .list-group-item:hover{
    position: relative;
    top: -0.2rem;
    z-index: 2;
  }
  @keyframes animate {
    0%{
      box-shadow: 3px 4px 29px 3px rgba( 255, 0, 0, .7);
      -webkit-box-shadow: 3px 4px 29px 3px rgba(255, 0, 0,.7);
      -moz-box-shadow: 3px 4px 29px 3px rgba(255, 0, 0,.7);
    }
    50%{
      box-shadow: 3px 4px 29px 3px yellowgreen;
      -webkit-box-shadow: 3px 4px 29px 3px yellowgreen;
      -moz-box-shadow: 3px 4px 29px 3px yellowgreen;
    }
    100%{ 
    box-shadow: 3px 4px 29px 3px rgba(0, 255,8,.7);
    -webkit-box-shadow: 3px 4px 29px 3px rgba(0, 255,8,.7);
    -moz-box-shadow: 3px 4px 29px 3px rgba(0, 255,8,.7);
    }
  }
  .list-group-item:last-child{
    border-bottom: none;
  }
  .list-group-item span{
    line-height: 35px;
    font-style: 2.1rem;
    cursor: pointer;
    width: 15%;
  }
  .list-group-item input{
    line-height: 2.1rem;
    font-style: 1.8rem;
    text-align: center;
    border: none;
    outline: none;
  }
  /* Main Style End */
</style>