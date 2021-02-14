<template>
  <div>
    <SearchBox />
    <List />
  </div>
</template>

<script>
import { createClient } from '~/plugins/contentful.js'

const client = createClient()

export default {
  async asyncData({ params }) {
    const entries = await client.getEntries({
      content_type: process.env.CTFL_CONTENT_TYPE_POST
    })
    console.log(entries.items[0].fields.caller)
  },
}
</script>
