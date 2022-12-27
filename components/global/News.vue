<template>
  <div class="news">
    <div class="item" :style="{backgroundImage: `url(${news[0].image})`}">
      <div class="item-content">
        <h2 class="item-title">{{ news[0].title }}</h2>
        <div class="item-details">
          <p class="item-description">
            <b>Neu:</b>
            {{ news[0].description }}
          </p>
          <div class="item-action">
            <Button v-if="news && news[0]" :to="news[0].url">Jetzt mehr erfahren</Button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Button from "~/components/global/Button.vue";

export default {
  name: 'News',
  components: {Button},
  // data() {
  //   return {
  //     news: []
  //   }
  // },
 props: {
   news: {
     type: Array,
     default: () => []
   }
 }
}
</script>

<style lang="postcss" scoped>
.news {
  position: relative;
}

.item {
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  min-height: 80vh;
  padding-top: 40%; /* 40% of the width */
  display: flex;

  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  top: 0;
}

.item-content {
  text-align: left;
  color: white;
  background-color: rgba(256, 256, 256, 0.9);

  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;

  padding-bottom: var(--default-spacing-bottom);
}

.item-title {
  display: block;
  background-color: #FFFFFF;
  padding: var(--default-text-padding-horizontal) var(--default-sidebar-width);
}

.item-details {
  display: flex;
  flex-direction: row;

  margin: var(--default-box-padding-vertical) var(--default-sidebar-width);
}

.item-action {
  flex-grow: 0;
  margin-right: auto;
}

.item-description {
  padding: var(--default-text-padding-vertical) var(--default-text-padding-horizontal) var(--default-text-padding-vertical) 0;
  flex-grow: 0;
}

.item-content {
  color: #444;
}

</style>
