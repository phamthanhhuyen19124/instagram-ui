<template>
  <div class="container">
    <div class="login">
      <div class="title-login"> Đăng kí</div>
      <div>
        <input v-model="email" class="dang-ki" type="text" placeholder="Enter email i’d">
      </div>
      <div>
        <input v-model="password" class="dang-ki" type="password" placeholder="Enter password">
      </div>
      <div>
        <input v-model="name" class="dang-ki" type="password" placeholder="Mời nhập tên của bạn">
      </div>
      <div class="error">{{error}}</div>
      <button @click="registerFrom" class="nut-an">{{registerBtn}}</button>
      <router-link class="lien-ket" to="/login"><span class="active">Login</span></router-link>
    </div>
  </div>
</template>
<script>
import axios from "axios";
export default {
  data(){
    return{
      name:'',
      password:'',
      email:'',
      error:'',
      loading: false

    }
  },
  computed:{
    registerBtn(){
      if(this.loading){
        return 'Đăng kí...'
      }
      return 'Đăng kí'
    },
    nameTooShort() {
      return this.name.length < 5;
    }

  },
  methods:{
    registerFrom(){
      if (this.loading) return;
      if(this.nameTooShort){
        this.error = 'ký tự quá ngắn mời bạn nhập lại !';
        return;
      }
      this.error = ''
      this.loading = true;
      axios({
        url:'register',
        method:'post',
        data:{
          "email": this.email,
          "password": this.password,
          "name":this.name,
        },
      }).then( (resp) =>{
        this.$router.push('/login');
        console.log('resp',resp);
        console.log('email',this.name ,'password', this.password,'name',this.name);
      }).catch( (error) =>{
        console.log('error',error)
          this.loading = false;
          if(error.response.data.email){
            console.log('email',error.response.data.email)
            this.error = error.response.data.email.join(',')
          }
      })
    }
  }
}
</script>
<style scoped>
  .container{
    width: 100%;
    height: 100vh;
    background: #E5E5E5;
  }
  .login{
    margin: 0 auto;
    text-align: center;
    width: 500px;
    padding: 20px;

  }
  .title-login{
    font-weight: 500;
    font-size: 60px;
    color: #000000;
    line-height: 76px;
    padding: 51px 0;
  }
  .dang-ki{
    font-weight: 400;
    font-size: 15px;
    color: #6D6A6A;
    padding: 14px 252px 14px  17px;
    border: 1px solid #6C6A6A;
    border-radius: 8px;
    margin-bottom: 10px;
  }
  .nut-an{
    background: #FFC600;
    border-radius: 8px;
    width: 100%;
    border: 0;
    padding: 12px 140px;
    font-weight: 400;
    font-size: 18px;
    color: #000000;
    margin-bottom: 35px;
    transition: .3s;
  }
  .nut-an:hover{
    background: #42b983;
    cursor: pointer;
  }
  .error{
    color: red;
  }

</style>