<template>
    <div :id="chart.id"/>
</template>

<script>
    import * as G2Plot from '@antv/g2plot'

    export default {
        props: ['chart'],
        name: 'Chart',
        data() {
            return {
                c: null
            }
        },
        watch: {
            chart() {
                const that = this
                if (that.c) {
                    that.c.destroy()
                }
            }
        },
        updated() {
            const that = this
            const container = document.getElementById(this.chart.id);
            const a = {
                ...that.chart.configs,
                data: that.chart.data
            }
            that.c = new G2Plot[that.chart.configs.type](container, a);
            that.c.render();
        },
        mounted() {
            let that = this
            const container = document.getElementById(this.chart.id);
            const a = {
                ...that.chart.configs,
                data: that.chart.data
            }
            that.c = new G2Plot[that.chart.configs.type](container, a);
            that.c.render();
        }
    }
</script>

