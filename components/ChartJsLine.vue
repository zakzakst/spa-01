<script>
import { Line } from 'vue-chartjs'
export default {
  extends: Line,
  props:['chartdata', 'options'],
  methods: {
    init() {
      this.renderChart(this.chartdata, this.options);
    }
  },
}
</script>
