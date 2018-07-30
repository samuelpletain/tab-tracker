<template>
  <div>
    <section class="section">
      <div class="container">
        <div class="columns">
          <div class="is-offset-4 column is-4 has-text-centered">
            <h1 class="title">Register</h1>
            <div class="field">
              <div class="control">
                <input type="email" class="input is-info" placeholder="Email" v-model="email">
              </div>
            </div>
            <div class="field">
              <div class="control">
                <input type="password" class="input is-info" placeholder="Password"
                v-model="password">
              </div>
            </div>
            <div class="button" @click="register">Register</div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import AuthenticationService from '@/services/AuthenticationService'
export default {
  name: 'Register',
  data () {
    return {
      email: '',
      password: ''
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
