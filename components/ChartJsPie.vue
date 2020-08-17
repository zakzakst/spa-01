<script>
import { Pie } from 'vue-chartjs'
export default {
  extends: Pie,
  props:['chartdata', 'options'],
  methods: {
    init() {
      this.renderChart(this.chartdata, this.options);
    }
  },
}
</script>
