<template>
  <div>
    <p>コンテンツ一覧ページ</p>
    <div v-for="n in response.list" :key="n.slug">
      <nuxt-link :to="`/contents/${n.topics_id}`">
        {{ n.ymd }} {{ n.subject }}
      </nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $axios }) {
    return {
      response: await $axios.$get('/rcms-api/3/service '),
    };
  },
};
</script>