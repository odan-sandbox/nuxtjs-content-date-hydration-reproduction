<template>
  <div>
    <section>
      <h2>createdAt</h2>
      <p>
        {{ page.createdAt }}
        {{ typeof page.createdAt }}
      </p>
    </section>
    <section>
      <h2>publishedAt</h2>
      <p>
        {{ page.publishedAt }}
        {{ typeof page.publishedAt }}
      </p>
    </section>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

// on SSR: Sun Jun 07 2020 03:37:06 GMT+0900 (日本標準時) object
// on CSR: 2020-06-06T18:37:06.335Z string

export default Vue.extend({
  async asyncData({$content}){
    const page = await $content("index").fetch()
    return { page }
  }
})
</script>
