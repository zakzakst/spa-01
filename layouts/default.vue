<template>
  <div class="mx-4 my-4">
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
