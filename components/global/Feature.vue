<template>
  <div :class="{feature: true, textLeft: textLeft}">
    <div class="image-box">
      <div class="image" :style="{backgroundImage: `url(${image})`}"></div>
    </div>
    <div class="content">
      <h1 class="feature-title">{{title}}</h1>
      <p class="text">{{text}}</p>
      <div class="actions">
        <Button :to="link">Jetzt mehr erfahren</Button>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "~/components/global/Button.vue";

export default {
  name: 'Feature',
  components: {Button},
  // data() {
  //   return {
  //     news: []
  //   }
  // },
  props: {
    image: String,
    title: String,
    text: String,
    link: String,
    textLeft: Boolean,
  }
}
</script>

<style lang="postcss" scoped>
.feature {
  position: relative;
  min-height: var(--default-mid-section-min-height);

  display: flex;
  flex-direction: row;
}

.feature.textLeft {
  flex-direction: row-reverse;
}

.feature > * {
  flex-grow: 1;
}

.image-box {
  min-width: 35%;
}

.image {
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;

  height: 100%;
  padding-top: 100%; /* should be at minimum a square */
}

.content {
  padding: 5rem;

  display: flex;
  flex-direction: column;
}

.feature-title {
  font-weight: normal;
  margin-top: auto;
  padding-bottom: var(--default-text-padding-horizontal);
}

.text {
  padding-bottom: var(--default-text-padding-horizontal);
}

.actions {
  margin-bottom: auto;
}
</style>
