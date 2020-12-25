<template>
  <ul>
    <li>{{ user.username }}</li>
  </ul>
</template>

<script>
export default {
  props: {
    user: {
      type: Object,
    },
  },
};
</script>
