<template>
  <div class="news">
    <div v-for="(item, index) in news" v-bind:key="item.description" :class="{item: true, first: index === 0, active: index === active}" :style="{backgroundImage: `url(${item.image})`}">
      <div class="item-content">
        <h2 class="item-title">{{ welcomeMessage }}</h2>
        <div class="item-details">
          <p class="item-description">
            <b>Neu:</b>
            {{ item.description }}
          </p>
          <div class="item-action">
            <Button :to="item.url">Jetzt mehr erfahren</Button>
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
  data() {
    return {
      active: 0,
    }
  },
  props: {
    welcomeMessage: String,
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

  pointer-events: none;
  opacity: 0;
  transition: opacity 1s linear;
}

.item.first {
  position: relative;
}

.item.active {
  pointer-events: all;
  opacity: 1;
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
  font-weight: normal;
}

.item-details {
  margin: var(--default-box-padding-vertical) var(--default-sidebar-width);

  display: flex;
  flex-direction: row;
}

.item-description {
  flex-grow: 1;
  padding: var(--default-text-padding-vertical) var(--default-text-padding-horizontal) var(--default-text-padding-vertical) 0;
}

.item-action {
  flex-grow: 0;

  //margin-right: auto;
}

.item-content {
  color: #444;
}

</style>
