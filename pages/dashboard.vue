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
        <chart-js-bar v-if="currentChart === 'chart-bar'" ref="chartBar" :chartdata="chartBarData" :options="chartBarOptions" />
        <chart-js-line v-if="currentChart === 'chart-line'" ref="chartLine" :chartdata="chartLineData" :options="chartLineOptions" />
        <chart-js-pie v-if="currentChart === 'chart-pie'" ref="chartPie" :chartdata="chartPieData" :options="chartPieOptions" />
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
import ChartJsBar from '@/components/ChartJsBar'
import ChartJsLine from '@/components/ChartJsLine'
import ChartJsPie from '@/components/ChartJsPie'

export default {
  data() {
    return {
      chartItems: [
        {
          id: 'chart-bar',
          label: '売上',
          icon: ['fas', 'chart-bar'],
          targetRef: 'chartBar',
        },
        {
          id: 'chart-line',
          label: '前年比',
          icon: ['fas', 'chart-line'],
          targetRef: 'chartLine',
        },
        {
          id: 'chart-pie',
          label: 'シェア',
          icon: ['fas', 'chart-pie'],
          targetRef: 'chartPie',
        },
      ],
      currentChart: '',
      chartBarData: {
        labels: ['January', 'February', 'March', 'April'],
        datasets: [
          {
            label: ['Data One'],
            backgroundColor: '#3273dc',
            data: [40, 30, 10, 20]
          },
        ]
      },
      chartBarOptions: {
        responsive: true,
        maintainAspectRatio: false
      },
      chartLineData: {
        labels: ['January', 'February', 'March', 'April'],
        datasets: [
          {
            label: ['Data One'],
            backgroundColor: '#3273dc',
            borderColor: '#3273dc',
            fill: false,
            data: [40, 30, 10, 20]
          },
        ]
      },
      chartLineOptions: {
        responsive: true,
        maintainAspectRatio: false
      },
      chartPieData: {
        labels: ['January', 'February', 'March', 'April'],
        datasets: [
          {
            label: 'Data One',
            backgroundColor: ['#3273dc', '#00d1b2', '#f14668', '#363636'],
            data: [40, 30, 10, 20]
          },
        ]
      },
      chartPieOptions: {
        responsive: true,
        maintainAspectRatio: false
      },
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
  components: {
    ChartJsBar,
    ChartJsLine,
    ChartJsPie,
  },
  methods: {
    changeChart(id) {
      this.currentChart = id;
    }
  },
  mounted() {
    this.currentChart = 'chart-bar';
  },
  watch: {
    currentChart(value) {
      const chart = this.chartItems.find(item => {
        return item.id === value;
      });
      setTimeout(() => {
        this.$refs[chart.targetRef].init();
      }, 0);
    }
  }
}
</script>
