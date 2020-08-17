<template>
  <div>
    <h1 class="title">画像一覧</h1>
    <div class="mb-4">
      <button class="button is-primary" @click="createImage">
        <span class="icon">
          <fa :icon="['fas', 'plus']" />
        </span>
        <span>新規画像登録</span>
      </button>
    </div>
    <div class="tabs is-boxed">
      <ul>
        <li v-for="tab in tabItems" :key="tab.id" :class="{ 'is-active': currentTab === tab.id }">
          <a @click.prevent="changeTab(tab.id)">
            <span class="icon is-small">
              <fa :icon="tab.icon" />
            </span>
            <span>{{ tab.label }}</span>
          </a>
        </li>
      </ul>
    </div>
    <div class="columns is-multiline">
      <div v-for="(image, index) in imageItems" :key="index" class="column is-one-quarter">
        <figure class="image is-1by1">
          <img :src="image.url">
        </figure>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tabItems: [
        {
          id: 'all',
          label: '全て',
          icon: ['fas', 'list'],
        },
        {
          id: 'animal',
          label: '動物',
          icon: ['fas', 'paw'],
        },
        {
          id: 'nature',
          label: '自然',
          icon: ['fas', 'tree'],
        },
      ],
      currentTab: 'all',
      imageItems: [
        {
          url: 'https://bulma.io/images/placeholders/256x256.png'
        },
        {
          url: 'https://bulma.io/images/placeholders/256x256.png'
        },
        {
          url: 'https://bulma.io/images/placeholders/256x256.png'
        },
        {
          url: 'https://bulma.io/images/placeholders/256x256.png'
        },
      ]
    }
  },
  methods: {
    createImage() {
      console.log('作成');
    },
    changeTab(id) {
      this.currentTab = id;
    }
  }
}
</script>
