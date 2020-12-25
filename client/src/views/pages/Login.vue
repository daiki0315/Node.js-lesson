<template>
  <my-login-form
    :user="user"
    :loginUser="loginUser"
    @login="login"
  />
</template>

<script>
import { mapState } from 'vuex';

import MyLoginForm from '@/components/LoginForm.vue';

export default {
  components: {
    MyLoginForm,
  },
  data() {
    return {
      user: {
        username: '',
        password: '',
      },
    };
  },
  methods: {
    login() {
      const param = {
        username: this.user.username,
        password: this.user.password,
      };
      this.$store.dispatch('updateLoginUser', param);
    },
  },
  computed: {
    ...mapState([
      'loginUser',
      'isAuthenticated',
    ]),
  },
  watch: {
    isAuthenticated() {
      if (this.isAuthenticated) {
        this.$router.push({ name: 'home' });
      }
    },
  },
};
</script>
