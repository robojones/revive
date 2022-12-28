<template>
  <main>
<!--    <section class="self-center flex flex-col flex-1 items-center justify-center navbar" v-if="info">-->
<!--      <h1 class="title text-center">{{ info.sitename }}</h1>-->
<!--      <h2 class="subtitle text-center">Boilerplate</h2>-->
<!--    </section>-->


    <news :welcome-message="page.welcomeMessage" :news="page.news"></news>
    <feature v-for="feature in page.features" :image="feature.image" :title="feature.title" :text="feature.text" :link="feature.url" v-bind:key="feature.title"></feature>
<!--    <section class="mt-8">-->
<!--      <img src="/img/stock-hands.webp">-->
<!--    </section>-->

<!--    <section class="mt-8">-->
<!--      <h3 class="text-primary-600 dark:text-primary-400 max-w-5xl mx-auto">Latest blog post</h3>-->
<!--      <posts post-type="blog" :amount="1" />-->
<!--    </section>-->
  </main>
</template>

<style lang="postcss" scoped>
main {
  padding: 0;
}
</style>

<script>
import News from "~/components/global/News";
import Feature from "~/components/global/Feature.vue";
export default {
  computed: {
  },
  components: {News, Feature},
  async asyncData({ $content, error }) {
    let info, page;
    try {
      info = await $content("site", "info").fetch();
    } catch (e) {
      error({ message: "Content not found" });
    }
    try {
      page = await $content("page", "landing-page").fetch();
    } catch (e) {
      error({ message: "Content not found" });
    }
    return { info, page };
  },
}
</script>
