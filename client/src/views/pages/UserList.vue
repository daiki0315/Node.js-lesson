<template>
  <div>
    <my-navi />
    <router-view
      v-for="user in userList"
      :key="user.id"
      :user="user"
    />
  </div>
</template>

<script>
import { mapGetters, mapActions } from 'vuex';
import MyNavi from '@/components/Navi.vue';

export default {
  components: {
    MyNavi,
  },
  created() {
    this.getAllUser();
  },
  methods: {
    ...mapActions([
      'getAllUser',
    ]),
  },
  computed: {
    ...mapGetters([
      'userList',
    ]),
  },
};
</script>
