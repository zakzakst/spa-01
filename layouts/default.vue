<template>
  <div class="l-wrapper">
    <div class="columns">
      <div class="column is-one-quarter">
        <side-nav />
      </div>
      <div class="column is-three-quarters">
        <Nuxt />
      </div>
    </div>
  </div>
</template>

<script>
import SideNav from '~/components/SideNav';
export default {
  components: {
    SideNav,
  }
}
</script>

<style lang="scss">
.l-wrapper {
  padding: $space--sm;
}
</style>
