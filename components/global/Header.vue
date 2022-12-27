<template>
  <nav class="scrim-bg fixed z-40 top-0 inset-x-0 pt-3 px-3 navbar" aria-label="Main Menu">
    <div class="logo">

    </div>
<!--    <ul class="flex">-->
<!--      <li class="flex-1">-->
<!--        <nuxt-link class="btn block" to="/">Home</nuxt-link>-->
<!--      </li>-->
<!--      <li class="flex-1 ml-2">-->
<!--        <nuxt-link class="btn block" to="/blog">Blog</nuxt-link>-->
<!--      </li>-->
<!--      <li class="flex-1 ml-2">-->
<!--        <nuxt-link class="btn block" to="/projects">Projects</nuxt-link>-->
<!--      </li>-->
<!--    </ul>-->
  </nav>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="postcss" scoped>
.logo {
  height: 2.5rem;
  width: 15.18rem;
  background-size: contain;
  background-position: left;
  background-repeat: no-repeat;
  background-image: url("/img/logo.svg");
}
.navbar {
  background-color: var(--bg-transparent);
  padding: 0.75rem;
}
</style>
