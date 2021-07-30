<template>
  <div>
    <file_num1></file_num1>
    <div class="background">
      <div>
        <AppSearchInput/>
        <article>
          <h1>{{ article.title }}</h1>
          <p>{{ article.description }}</p>
          <img :src="article.img" :alt="article.alt"/>
          <p>Article last updated: {{ formatDate(article.updatedAt) }}</p>

          <nuxt-content :document="article"/>

          <author :author="article.author"/>

          <prev-next :prev="prev" :next="next"/>
        </article>
      </div>

      <file_num2/>

    </div>
  </div>
</template>
<script>

import file_num1 from "../../components/file_num1";
import file_num2 from "../../components/file_num2";

export default {
  components: {file_num1, file_num2},
  async asyncData({$content, params}) {
    const article = await $content('articles', params.slug).fetch()

    console.log(article)
    const [prev, next] = await $content('articles')
      .only(['title', 'slug'])
      .sortBy('createdAt', 'asc')
      .surround(params.slug)
      .fetch()

    return {
      article,
      prev,
      next
    }
  },
  methods: {
    formatDate(date) {
      const options = {year: 'numeric', month: 'long', day: 'numeric'}
      return new Date(date).toLocaleDateString('en', options)
    }
  }
}
</script>

<style>
.background {
  display: flex;
  justify-content: space-between;
}

.nuxt-content h2 {
  font-weight: bold;
  font-size: 28px;
}

.nuxt-content h3 {
  font-weight: bold;
  font-size: 22px;
}

.nuxt-content p {
  margin-bottom: 20px;
}

</style>
