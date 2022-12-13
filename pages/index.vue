<template>
  <div>
    <p>コンテンツ一覧ページ</p>
    <div v-for="n in response.list" :key="n.slug">
      <nuxt-link v-if="n.slug != ''" :to="`/contents/${n.slug}`">
        {{ n.ymd }} {{ n.subject }}
      </nuxt-link>
      <nuxt-link v-else :to="`/contents/${n.topics_id}`">
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