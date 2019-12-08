<template>
  <div class="signin">
      <div class="signin-header">
          <p>WELCOME BACK TO getCRYPTO!</p>
      </div>
      <form @submit.prevent="onSubmit"  class="sign-in-form">
          <span>SIGN IN</span>

          <P v-if="$v.email.$error" 
          :style="$v.email.$error ? 'color:red' : ''"
          >please provide valid email</P>  
          <input :class="{invalid: $v.email.$error}"
           v-model="email" @blur="$v.email.$touch()" 
          type="text"  name="email" id="email" placeholder="Your Email"
            
          >
          
          
          <p v-if="$v.password.$error"
            :style="$v.password.$error ? 'color:red' : '' "
          >Password must be 6 ch or higher</p>  
          <input v-model="password" 
            @blur="$v.password.$touch()"
            :class="{invalid: $v.password.$error}"
           type="password" name="password" id="password" 
           placeholder="Your Password">
          <button >getCRYPTO</button>
      </form>
  </div>
</template>

<script>
import {required , email , minLength } from 'vuelidate/lib/validators'
export default {
    name: 'Signin',

    data(){
        return{
            email: null,
            password: null,
        }
    },

    validations: {
        email: {
            required,
            email,
        },

        password : {
            required,
            minLen : minLength(6)
        }
    },

    methods: {
        onSubmit(){
            if(this.email && this.password){
                this.email = null
                this.password = null
                this.$router.push({name: "home"})
            } 
            
        }
    },

    
}
</script>

<style scoped>

    .invalid {
        border: 2px solid red;
    }

   form span.error {
        display: none;
        color: red;
        
    }

    .signin-header {
        text-align: center;
        font-size: 25px;
        margin: 20px 0 ;
    }

    .sign-in-form {
        margin: 0 auto;
        margin-bottom: 45px;
        width: 450px;
        height: 240px;
        background: #3ed0d1;
        padding: 20PX;
    }

    .sign-in-form span {
        color: #fff;
        display: block;
    }

    .sign-in-form input {
        padding: 10px;
        display: block;
        height: 38px;
        width: 100%;
        margin: 10px 0;
    }

    .sign-in-form input::placeholder {
        color: #000;
    }

    .sign-in-form button {
        font-size: 14px;
        width: 100%;
        background: #000;
        color: #fff;
        outline: none;
        border: none;
        height: 38px;
        margin: 20px 0;
        cursor: pointer;

    }

    
</style>