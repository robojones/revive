<template>
  <nuxt-link class="button" :to="to">
    <a class="button-text">
      <slot>Weiter</slot>
    </a>
    <div class="icon">
      <svg class="icon-svg" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24">
        <path fill="#FFFFFF" d="M8.59,16.58L13.17,12L8.59,7.41L10,6L16,12L10,18L8.59,16.58Z" />
      </svg>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'Button',
  // data() {
  //   return {
  //     news: []
  //   }
  // },
 props: {
   to: String,
   text: String,
 }
}
</script>

<style lang="postcss" scoped>
.button {
  background-color: var(--default-button-background-color);
  white-space: nowrap;

  display: inline-flex;
  flex-direction: row;
  padding: var(--default-button-padding);
}

.button-text {
  color: var(--color-white);
  margin-right: 1rem;
}

.icon {
  margin: auto;
}

.icon-svg {
  height: 3em;
  width: 3em;
  margin: -1em;
}
</style>
