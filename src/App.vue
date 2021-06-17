<template>
  <div class="signup">
    <img src="./assets/Signup.svg" alt="logo"/>
    <SignupForm />
  </div>
</template>

<script>
import SignupForm from './components/SignupForm.vue'

export default {
  name: 'App',
  components: {
    SignupForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

body {
  margin: 0;
  height: 100%;
  background-size: cover;
  background-repeat:no-repeat;
  background: linear-gradient(45deg, #19134e, #abb1f3);  
}

img {
  width: 250px;
  margin: 0 60px;
}

.signup {
  max-width: 900px;
  margin: 190px auto;
  background: white;
  display: flex;
  border-radius: 10px;
}
</style>
