<template>
  <div>
    {{ page.createdAt }}
    {{ typeof page.createdAt }}
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
