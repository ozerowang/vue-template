<template>
    <div class="root">
        <div class="chart" id="chart"></div>
        <div>{{array}}{{reverse}}</div>
    </div>
</template>

<script>
export default {
    name: "EchartsDemo",
    data(){
        return{
            array: [1,2,3]
        }
    },
    mounted() {
        this.initChart();
    },
    methods:{
        initChart(){
            // 基于准备好的dom，初始化echarts实例
            const myChart = this.$echarts.init(document.getElementById('chart'));
            // 绘制图表
            myChart.setOption({
                title: {
                    text: 'ECharts 入门示例'
                },
                tooltip: {},
                xAxis: {
                    data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
                },
                yAxis: {},
                series: [{
                    name: '销量',
                    type: 'bar',
                    data: [5, 20, 36, 10, 10, 20]
                }]
            });
        }
    },
    computed:{
        reverse(){
            return _.reverse(this.array)
        }
    }
}
</script>

<style scoped lang="stylus">
    .root
        width 800px
        height 800px
        display flex
        justify-content center
        align-items center
        #chart
            width 500px
            height 500px
</style>
