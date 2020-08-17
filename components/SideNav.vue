<template>
  <nav class="panel">
    <p class="panel-heading">メニュー</p>
    <nuxt-link v-for="item in navItems" :key="item.link" :to="item.link" class="panel-block">
      <span class="panel-icon">
        <fa :icon="item.icon" />
      </span>
      {{ item.label }}
    </nuxt-link>
  </nav>
</template>

<script>
export default {
  data() {
    return {
      navItems: [
        {
          label: 'ユーザー',
          link: 'users',
          icon: ['fas', 'user'],
        },
        {
          label: '画像',
          link: 'images',
          icon: ['fas', 'image'],
        },
        {
          label: 'タスク',
          link: 'tasks',
          icon: ['fas', 'clipboard-check'],
        },
        {
          label: 'ダッシュボード',
          link: 'dashboard',
          icon: ['fas', 'chart-area'],
        },
        {
          label: '設定',
          link: 'settings',
          icon: ['fas', 'cog'],
        },
      ]
    }
  }
}
</script>
