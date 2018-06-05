<template>
  <v-app>
    <v-container grid-list-xl text-xs-center>
      <v-layout row wrap>
        <v-flex xs6 offset-xs3>
          <v-card color="white" class="pa-5">
            <v-form ref="form">
              <v-text-field v-bind="name" label="Name" type="text" prepend-icon="account_circle" single-line required/>
              <v-text-field
                v-bind="password"
                label="Password"
                :type="can_see ? 'text': 'password'"
                prepend-icon="lock"
                :append-icon="can_see ? 'visibility' : 'visibility_off'"
                :append-icon-cb="() => (can_see = !can_see)"
                single-line required/>
              <v-text-field
                v-show="is_register"
                v-bind="repassword"
                label="Re-Enter"
                :type="can_see ? 'text': 'password'"
                prepend-icon="lock"
                :append-icon="can_see ? 'visibility' : 'visibility_off'"
                :append-icon-cb="() => (can_see = !can_see)"
                single-line required/>
              <p @click="toggleSignin" class="text-xs-left ml-1 hover">{{msg}}</p>
              <v-btn color="success">{{btn_txt}}</v-btn>
            </v-form>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>

<script>
export default {
  name: 'login-page',
  data () {
    return {
      name: '',
      password: '',
      repassword: '',
      msg: 'I don`t have an account',
      btn_txt: 'Sing in',
      can_see: false,
      is_register: false
    }
  },
  methods: {
    toggleSignin () {
      this.is_register = !this.is_register
      this.msg = this.is_register ? 'I`m already a member' : 'I don`t have an account'
      this.btn_txt = this.is_register ? 'Sign up' : 'Sign in'
    }
  }
}
</script>

<style scoped>
.hover:hover{
  color: #1470aa;
  cursor: pointer;
}
</style>
