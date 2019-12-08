<template>
  <div class="navbar-main-page">
      <nav class="main-nav"
      :class="this.$route.path === '/' ? '' : 'border-bottom' " 
      :style="this.$route.path ===  '/register' ? 'border-bottom:none' : '' " 
      >
        <div class="container">
            <div class="main-nav-logo">
               
                <router-link :to="{name: 'home'}"> <img src="../../assets/otclabs-logo.png" alt=""></router-link>
            </div>       

            <div class="main-nav-spans"
            :class="this.$route.path === '/' ? 'display-signin' : 'display-signin-none' "   
            >
              <span>BUY/SELL</span>
              <span>MARKET DATA</span>
              <span>MARGIN TRADING</span>
            </div>

            <div class="nab-bar-btns">
              <div class="sign-in">
                <button @click="goToSignin"
                 class="signinBg"
                 :class="this.$route.path === '/' ? 'display-signin' : 'display-signin-none' "    
                 >sign in</button>
              </div>

              <div class="register">
                <button @click="goToRegister"
                 class="registerBg"
                  :class="this.$route.path === '/register' ? 'display-register-none' : 'display-register' "
                 >register</button>

              </div>
              
              <div @click="openMobileNavbar = !openMobileNavbar" 
              class="mobile-menu"
              >
                <div class="bar"></div>
                <div class="bar"></div>
                <div class="bar"></div>
              </div>
            </div>
        </div>
      </nav>

      <transition name="fade">
           <div class="mobile-navbar"
      v-if="openMobileNavbar"
      >
        <div class="sign-in">
                <button @click="goToSignin"
                 class="signinBg"
                 :class="this.$route.path === '/' ? 'display-signin' : 'display-signin-none' "    
                 >sign in</button>
              </div>

              <div class="register">
                <button @click="goToRegister"
                 class="registerBg"
                  :class="this.$route.path === '/register' ? 'display-register-none' : 'display-register' "
                 >register</button>

              </div>
      </div>
      </transition>
 
  </div>
</template>

<script>

export default {
    name: "NavbarMainPage",

    data(){
      return{
        openMobileNavbar : false,
      }
    },

    methods: {
      goToSignin(){
        this.$router.push({name: "signin"})
      },

      goToRegister(){
        this.$router.push({name: "register"})
      },


      
    }
}
</script>

<style scoped> 
    .container {
      display: flex;
      justify-content: space-between;
      align-items: flex-end;
      flex-wrap: wrap;
    }
    .main-nav {
      height: 120px;
      display: flex;
      align-items: center;
      padding: 0 50px
     
    }

    .mobile-navbar {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      background: #000;
      transition: all 1s;
      padding: 10px;
    }

    .fade-enter-active, .fade-leave-active {
  transition: opacity 1s;
  
 
}
.fade-enter, .fade-leave-to {
  opacity: 0;
 
   }

       .mobile-navbar button {
      outline: none;
      border: none;
      width: 300px;
      height: 35px;
      color: #fff;
      cursor: pointer;
      text-transform: uppercase;
      font-size: 14px;
      margin: 5px 5px;
    }

    .navbar-main-page {
      position: sticky;
      top:0;
      left: 0;
      z-index: 100;
      background: #fff;
    }

    .main-nav-spans {
      font-size: 14px
    }
    .main-nav-spans span {
        margin: 0 15px;
        font-weight: bold;
    }

    .nab-bar-btns {
      display: flex;
      flex-wrap: wrap;
    }

    .nab-bar-btns button {
      outline: none;
      border: none;
      width: 146px;
      height: 35px;
      color: #fff;
      cursor: pointer;
      text-transform: uppercase;
      font-size: 14px;
      margin: 0 5px;
    }

    .signinBg {
      background: #19afb0;
    }
    .registerBg {
      background: #e7762b;
    }


    .display-signin-none {
      display: none;
      
    }

    .display-signin {
      display: block;
    }

    .display-register-none {
      display: none;
      
    }

    .display-register {
      display: block;
    }

    .border-bottom {
      border-bottom: 1px solid #000;
    }

    .mobile-menu .bar {
      width: 50px;
      height: 5px;
      background: #000;
      margin: 10px;
      display: none;
      cursor: pointer;
    }

    
    @media (max-width: 1010px){
      

      .nab-bar-btns button {
        display: none;
      }

      .mobile-menu .bar {
        display: block;
      }

      .main-nav-logo {
        margin: 10px 0;
      }

      .main-nav-spans {
        display: none;
      }

      

      .main-nav {
        height: auto;
      }

      .nab-bar-btns {
        margin: 10px 0;
      }
    }

</style>