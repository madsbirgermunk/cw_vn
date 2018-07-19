<template>
  <div>
    <h1>Register</h1>

    <input  type="email"
            name="email"
            v-model="email"
            placeholder="email" />
    <br>
    <input  type="password"
            name="password"
            v-model="password"
            placeholder="password" />
    <br>
    <button @click="register">Register</button>
  </div>
</template>

<script>
import AuthentificationService from '@/services/AuthentificationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      const response = await AuthentificationService.register({
        email: this.email,
        password: this.password
      })
      console.log(this.email + ' tries to register with password ' + this.password)
      console.log(response.data)
    }
  }

  /*  Testfunktionen
  watch: {
    email (value) {
      console.log('email has changed', value)
    }
  },
  mounted () {
    setInterval(() => {
      this.email = 'Beeilen Sie sich lieber!'
    }, 5000)
  }
  */
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
