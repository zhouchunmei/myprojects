<template>
    <div class="pos-echarts">
        <div>会员总数：99</div>
        <div>日增长人数：昨日增长100</div>
        <div
            id="memberEcharts"
            class="echartsSty"
        ></div>
    </div>
</template>

<script>
// 引入基本模板
let echarts = require('echarts/lib/echarts');
// 引入柱状图组件
require('echarts/lib/chart/line');
// 引入提示框和title组件
require('echarts/lib/component/tooltip');
require('echarts/lib/component/title');
export default {
    name: 'Echarts',
    data() {
        return {
            msg: 'Welcome to Your Vue.js App'
        }
    },
    mounted() {
        this.drawLine();
    },
    methods: {

        drawLine() {
            // 基于准备好的dom，初始化echarts实例
            let myChart = echarts.init(document.getElementById('memberEcharts'))
            // 绘制图表
            myChart.setOption({
                title: { text: '' },
                tooltip: {},
                xAxis: {
                    type: 'category',
                    data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
                },
                yAxis: {
                    type: 'value'
                },
                series: [{
                    data: [820, 932, 901, 934, 1290, 1330, 1320],
                    type: 'line'
                }]
            });
        }
    }
}
</script>

<style lang="scss" scoped>
.pos-echarts {
    padding-top: 100px;
    .echartsSty {
        width: 100%;
        height: 500px;
        margin: 0 auto;
    }
}
</style>
