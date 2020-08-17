<template>
  <div>
    <h1 class="title">ダッシュボード</h1>
    <section class="card mb-4">
      <header class="card-header">
        <h2 class="card-header-title">チャート</h2>
      </header>
      <div class="card-content">
        <div class="tabs is-boxed">
          <ul>
            <li v-for="chart in chartItems" :key="chart.id" :class="{ 'is-active': currentChart === chart.id }">
              <a @click.prevent="changeChart(chart.id)">
                <span class="icon is-small">
                  <fa :icon="chart.icon" />
                </span>
                <span>{{ chart.label }}</span>
              </a>
            </li>
          </ul>
        </div>
        <!-- チャートの内容 -->
      </div>
    </section>
    <section class="card mb-4">
      <header class="card-header">
        <h2 class="card-header-title">メッセージ</h2>
      </header>
      <div class="card-content">
        <!-- メッセージの内容 -->
        <article v-for="message in messageItems" :key="message.id" class="media">
          <figure class="media-left">
            <p class="image is-64x64">
              <img class="is-rounded" :src="message.img">
            </p>
          </figure>
          <div class="media-content">
            <div class="content">
              <p class="mb-2"><strong>{{ message.name }}</strong></p>
              <p>{{ message.text }}</p>
            </div>
          </div>
        </article>
      </div>
    </section>
  </div>
</template>

<script>
export default {
  data() {
    return {
      chartItems: [
        {
          id: 'chart1',
          label: '売上',
          icon: ['fas', 'chart-bar'],
        },
        {
          id: 'chart2',
          label: '前年比',
          icon: ['fas', 'chart-line'],
        },
        {
          id: 'chart3',
          label: 'シェア',
          icon: ['fas', 'chart-pie'],
        },
      ],
      currentChart: 'chart1',
      messageItems: [
        {
          id: 'message1',
          img: 'https://bulma.io/images/placeholders/128x128.png',
          name: '山田 太郎',
          text: 'メッセージが入ります。メッセージが入ります。メッセージが入ります。メッセージが入ります。メッセージが入ります。'
        },
        {
          id: 'message2',
          img: 'https://bulma.io/images/placeholders/128x128.png',
          name: '佐藤 次郎',
          text: 'メッセージが入ります。メッセージが入ります。メッセージが入ります。メッセージが入ります。メッセージが入ります。'
        },
      ],
    }
  },
  methods: {
    changeChart(id) {
      this.currentChart = id;
    }
  }
}
</script>
