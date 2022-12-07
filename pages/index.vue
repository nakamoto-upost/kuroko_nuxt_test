<template>
  <div>
    <h1>{{response.details.subject}}</h1>
    <div>{{response.details.ext_2}}</div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    return { response: await $axios.$get('/rcms-api/3/service/3') };
  },
};
</script>