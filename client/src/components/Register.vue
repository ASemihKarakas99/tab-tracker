<template>
  <div class>
    <h1>Register</h1>
    <input
        type="text"
        name="email"
        v-model="email"
        placeholder="email" />
        <br>
     <input
        type="password"
        name="password"
        v-model="password"
        placeholder="password" />
        <br>
    <button
      @click="register">
      Register</button>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  name: 'Register',
  data () {
    return {
      email: 'abc',
      password: '123'
    }
  },
  methods: {
    async register () {
      const response = await AuthenticationService.register({
        email: this.email,
        password: this.password
      })
      console.log(response.data)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
