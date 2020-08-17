<script>
import { Bar } from 'vue-chartjs'
export default {
  extends: Bar,
  props:['chartdata', 'options'],
  methods: {
    init() {
      this.renderChart(this.chartdata, this.options);
    }
  },
}
</script>
