<template>
    <div>
      <h1 class="title">{{ response.details.subject }}</h1>
      <div><a :href="response.details.ext_1.url"><img :src="response.details.ext_1.url" alt=""></a></div>
      <div class="post" v-html="response.details.ext_2"></div>
    </div>
  </template>
  
  <script>
  export default {
    async asyncData({ $axios, params }) {
      return { response: await $axios.$get(`/rcms-api/3/service/${params.slug}`) };
    },
  };
  </script>
  