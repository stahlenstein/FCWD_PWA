<!-- npm install chromedriver@87.0.1 -->

<template>
<div id="app">

<div class="login-page">
   <transition name="fade">
      <div v-if="!registerActive" class="wallpaper-login"></div>
   </transition>
   <div class="wallpaper-register"></div>

   <div class="container">
      <div class="row">
         <div class="col-lg-4 col-md-6 col-sm-8 mx-auto">
            <div v-if="!registerActive" class="card login" v-bind:class="{ error: emptyFields }">
               <h1>Sign In</h1>
               <form class="form-group">
                  <input v-model="emailLogin" type="email" class="form-control" placeholder="Email" required>
                  <input v-model="passwordLogin" type="password" class="form-control" placeholder="Password" required>
                  <input type="submit" class="btn btn-primary" value="Submit" @click="doLogin">
                  <a class="forgot" href="#">Forgot your password?</a>
               </form>
            </div>

            <div v-else class="card register" v-bind:class="{ error: emptyFields }">
               <h1>Sign Up</h1>
               <form class="form-group">
                  <input v-model="emailReg" type="email" class="form-control" placeholder="Email" required>
                  <input v-model="passwordReg" type="password" class="form-control" placeholder="Password" required>
                  <input v-model="confirmReg" type="password" class="form-control" placeholder="Confirm Password" required>
                  <input type="submit" class="btn btn-primary" @click="doRegister">
                  <p>Already have an account? <a href="#" @click="registerActive = !registerActive, emptyFields = false">Sign in here</a>
                  </p>
               </form>
            </div>
         </div>
      </div>
   </div>
</div>

</div>
</template>

<script>
export default {
  name: 'app',
  data: {
    registerActive: false,
    emailLogin: '',
    passwordLogin: '',
    emailReg: '',
    passwordReg: '',
    confirmReg: '',
    emptyFields: false
  },
  methods: {
    doLogin () {
      if (this.emailLogin === '' || this.passwordLogin === '') {
        this.emptyFields = true
      } else {
        alert('You are now logged in')
      }
    },
    doRegister () {
      if (this.emailReg === '' || this.passwordReg === '' || this.confirmReg === '') {
        this.emptyFields = true
      } else {
        alert('You are now registered')
      }
    }
  }
}
</script>


<style>
.container {
    z-index: 1;
    position: absolute;
    align-self: center;
    left:5vw;
    width: 15em;
    height: 25em;
    background-color: white;
    border:black thin;
    border-radius: 0.25rem;
    box-shadow: 5px 5px 30px black;
}
.card h1 {
text-align: left;
font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
.row {
    position: absolute;
}
.p {
  line-height: 1rem;
}
.card {
  padding: 20px;
}
.form-control {
  margin-bottom: 5px;
  border-radius: .2rem;
  border: 1px;
  border-style: solid;
  border-color: lightgray;
  height: 1.25rem;
  font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
}
.btn-primary {
    display: block;
    background-color: #007bff;
    border: #007bff;
    color: white;
    align-self: center;
    border-radius: 0.25rem;
    margin-top: 30px;
    font: 1em sans-serif;
    font-weight: 600;
    text-align: center;
    font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    font-size: 16px;
    height: 30px;
    width: 70px;
    right: 1.5rem;
    position: absolute;
    transition: color .15s ease-in-out,background-color .15s ease-in-out,border-color .15s ease-in-out,box-shadow .15s ease-in-out;
}
.forgot {
    padding: 10px;
    font-size: .7rem;
    position: relative;
}
.login-page {
  justify-content: center;
  display: flex;
  height: 100vh;
}
.login-page .wallpaper-login {
  background: url(https://images.unsplash.com/photo-1615800634551-745f94ffa49d?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=scale&w=2242&q=100&orient=8) no-repeat center center;
  background-size: cover;
  height: 100%;
  position: relative;
  width: 100%;
  z-index: 0;
}
.login-page .fade-enter-active, .login-page .fade-leave-active {
  transition: opacity 0.5s;
}
.login-page .fade-enter, .login-page .fade-leave-to {
  opacity: 0;
}
.login-page .wallpaper-register {
  background: url() no-repeat center center;
  background-size: cover;
  height: 100%;
  position: absolute;
  width: 100%;
  z-index: -1;
}
.login-page h1 {
  margin-bottom: 3rem;
  color: black;
}
.error {
  animation-name: errorShake;
  animation-duration: 0.3s;
}
@keyframes errorShake {
  0% {
    transform: translateX(-25px);
  }
  25% {
    transform: translateX(25px);
  }
  50% {
    transform: translateX(-25px);
  }
  75% {
    transform: translateX(25px);
  }
  100% {
    transform: translateX(0);
  }
}
</style>
