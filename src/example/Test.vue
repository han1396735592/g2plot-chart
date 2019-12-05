<template>
    <div>
        <Chart :chart="chart"></Chart>
        <textarea style="width:500px;height:500px" v-model="chartText"></textarea>
    </div>

</template>

<script>

    import {Chart} from 'g2plot-chart'
    const chart = {
        "id": "u-df5b-f26",
        "configs": {
            "title": {
                "visible": true,
                "text": "分组条形图"
            },
            "description": {
                "visible": true,
                "text": "一个基础的分组条形图"
            },
            "padding": "auto",
            "legend": {
                "visible": true,
                "position": "right-top",
                "flipPage": false
            },
            "tooltip": {
                "visible": false,
                "shared": true,
                "crosshairs": {
                    "type": "rect"
                }
            },
            "xAxis": {
                "visible": true,
                "autoHideLabel": false,
                "autoRotateLabel": false,
                "autoRotateTitle": false,
                "grid": {
                    "visible": true
                },
                "line": {
                    "visible": false
                },
                "tickLine": {
                    "visible": false
                },
                "label": {
                    "visible": false
                },
                "title": {
                    "visible": true,
                    "offset": 12,
                    "title": "数值"
                }
            },
            "yAxis": {
                "visible": true,
                "autoHideLabel": false,
                "autoRotateLabel": false,
                "autoRotateTitle": true,
                "grid": {
                    "visible": false
                },
                "line": {
                    "visible": false
                },
                "tickLine": {
                    "visible": false
                },
                "label": {
                    "visible": true,
                    "style": {
                        "fill": "rgba(0, 0, 0, 0.65)"
                    }
                },
                "title": {
                    "visible": false,
                    "offset": 12,
                    "title": "日期"
                }
            },
            "label": {
                "visible": true,
                "position": "right",
                "adjustColor": true,
                "offset": 8
            },
            "forceFit": false,
            "animation": false,
            "width": 560,
            "height": 376,
            "media": "PC",
            "type": "GroupBar",
            "xField": "y",
            "yField": "x",
            "groupField": "serie",
            "data": {
                "dimension": 2,
                "rows": [
                    "London",
                    "Paris"
                ],
                "cols": [
                    "2019-03",
                    "2019-04",
                    "2019-05",
                    "2019-06",
                    "2019-07"
                ],
                "y": {
                    "min": 0,
                    "max": 1000
                },
                "styles": {}
            }
        },
        "data": [
            {
                "x": "2019-03",
                "y": 385,
                "serie": "Paris"
            },
            {
                "x": "2019-04",
                "y": 888,
                "serie": "Paris"
            },
            {
                "x": "2019-05",
                "y": 349,
                "serie": "Paris"
            },
            {
                "x": "2019-06",
                "y": 468,
                "serie": "Paris"
            },
            {
                "x": "2019-07",
                "y": 477,
                "serie": "Paris"
            },
            {
                "x": "2019-03",
                "y": 291,
                "serie": "London"
            },
            {
                "x": "2019-04",
                "y": 484,
                "serie": "London"
            },
            {
                "x": "2019-05",
                "y": 293,
                "serie": "London"
            },
            {
                "x": "2019-06",
                "y": 147,
                "serie": "London"
            },
            {
                "x": "2019-07",
                "y": 618,
                "serie": "London"
            }
        ]
    }
    export default {
        name: 'Test',
        components: {Chart},
        data() {
            return {
                chartText: ''
            }
        },
        computed: {
            chart() {
                if (this.chartText) {
                    return JSON.parse(this.chartText)
                } else {
                    return chart
                }

            }
        }
    }
</script>

