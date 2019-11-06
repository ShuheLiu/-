<template>
    <div>
        <div id='relate_graph2' :style="{width: '100%', height: '320px'}"></div>
    </div>
</template>

<script>
    import echarts from 'echarts'
    export default {
        name: "drawGraph",

        data(){
            return{
                //graph:'',
                list1:[{
                    'serviceCode':'0001',
                    'serviceName':'系统1',
                    'psize':60,
                    'csize':20,
                    'category':2,
                    'name':'系统2',
                    'x':122,
                    'y':307,
                    //'color':'#a75ebc',
                },{
                    'serviceCode':'0002',
                    'serviceName':'系统3',
                    'psize':30,
                    'csize':40,
                    'category':0,
                    'name':'系统4',
                    'x':0,
                    'y':450,
                    //'color':'#a75ebc',
                },{
                    'serviceCode': 10000,
                    'serviceName': '总行前置1',
                    'psize': 20,
                    'csize': 30,
                    'category': 1,
                    'name': '总行前置1',
                    'x':108,
                    'y':22,
                    'color':'#a75ebc',
                }, {
                    'serviceCode': 10001,
                    'serviceName': '总行前置2',
                    'psize': 16,
                    'csize': 30,
                    'category': 2,
                    'name': '总行前置2',
                    'x':260,
                    'y':146,
                }, {
                    'serviceCode': 10002,
                    'serviceName': '总行前置3',
                    'psize': 56,
                    'csize': 30,
                    'category': 1,
                    'name': '总行前置3',
                    'x':308,
                    'y':250,
                }],
                list2:[{
                    'sourceId':'0002',
                    'targetId':'0001',
                },{
                    'sourceId': '10000',
                    'targetId': '10001'
                }, {
                    'targetId': '10000',
                    'sourceId': '10001'
                },{
                    'targetId': '10002',
                    'sourceId': '10001'
                },{
                    'targetId': '0002',
                    'sourceId': '10002'
                }]
            }
        },

        mounted(){
            this.initGraph();
        },

        methods:{
            initGraph(){
                //let this_ = this;
                //this.GetRandom(this.list1);
                //let myChart = echarts.init(document.getElementById("myGraph"));
                //var categories = [];
                /*for (var i = 0; i < 9; i++) {
                    categories[i] = {
                        name: '类目' + i
                    };
                }*/
                /*graph.nodes.forEach(function (node) {
                    node.itemStyle = null;
                    node.value = node.symbolSize;
                    node.symbolSize /= 1.5;
                    node.label = {
                        normal: {
                            show: node.symbolSize > 30
                        }
                    };
                    node.category = node.attributes.modularity_class;
                });*/
               /*let option = {
                    title: {
                        text: 'Les Miserables',
                        subtext: 'Default layout',
                        top: 'bottom',
                        left: 'right'
                    },
                    tooltip: {},
                    legend: [{
                        // selectedMode: 'single',
                        /!*data: categories.map(function (a) {
                            return a.name;
                        })*!/
                        x: "center",
                        show: false,
                        data: ["包含", "包含", '包含']
                    }],
                    animationDuration: 1500,
                    animationEasingUpdate: 'quinticInOut',
                    series : [
                        {
                            name: 'Les Miserables',
                            type: 'graph',
                            layout: 'none',
                            //data: graph.nodes,
                            //links: graph.links,
                            links:{source : 2, target : 1, value : 5, label: '女儿'},
                            //categories: categories,
                            //links:link,
                            categories: [{
                                name: 'per',
                                itemStyle: {
                                    normal: {
                                        color: "#009800",
                                    }
                                }
                            }, {
                                name: 'loc',
                                itemStyle: {
                                    normal: {
                                        color: "#4592FF",
                                    }
                                }
                            }, {
                                name: 'org',
                                itemStyle: {
                                    normal: {
                                        color: "#ff232b",
                                    }
                                }
                            }, {
                                name: 'time',
                                itemStyle: {
                                    normal: {
                                        color: "#e6dd1c",
                                    }
                                }
                            }, {
                                name: 'body',
                                itemStyle: {
                                    normal: {
                                        color: "#c489e6",
                                    }
                                }
                            }, {
                                name: 'sigos',
                                itemStyle: {
                                    normal: {
                                        color: "#a0e6a5",
                                    }
                                }
                            }, {
                                name: 'check',
                                itemStyle: {
                                    normal: {
                                        color: "#e6bfac",
                                    }
                                }
                            }, {
                                name: 'disease',
                                itemStyle: {
                                    normal: {
                                        color: "#859f89",
                                    }
                                }
                            }, {
                                name: 'treatmeot',
                                itemStyle: {
                                    normal: {
                                        color: "#686767",
                                    }
                                }
                            }],
                            roam: true,
                            focusNodeAdjacency: true,
                            itemStyle: {
                                normal: {
                                    borderColor: '#fff',
                                    borderWidth: 1,
                                    shadowBlur: 10,
                                    shadowColor: 'rgba(0, 0, 0, 0.3)'
                                }
                            },
                            label: {
                                position: 'right',
                                formatter: '{b}'
                            },
                            lineStyle: {
                                color: 'source',
                                curveness: 0.3
                            },
                            emphasis: {
                                lineStyle: {
                                    width: 10
                                }
                            }
                        }
                    ]
                };*/

                var myChart = echarts.init(document.getElementById('relate_graph2'));
                var option = {
                    animationDurationUpdate: 1500,
                    animationEasingUpdate: 'quinticInOut',
                    color:['#6832ed', '#abcdef','#adc123'],
                    legend: {
                        show: true,
                        data: [
                            {name: '知识点类别1', textStyle:{color:'#333'}},
                            {name: '知识点类别2', textStyle:{color:'#333'}},
                            {name: '知识点类别3', textStyle:{color:'#333'}}
                        ]
                    },
                    series : [{
                        type: 'graph',
                        layout: 'none',
                        draggable:true,
                        legendHoverLink : true, //是否启用图例 hover(悬停) 时的联动高亮。
                        hoverAnimation : true, //是否开启鼠标悬停节点的显示动画
                        data: this.list1.map(function (node) {
                            return {
                                x: node.x,
                                y: node.y,
                                id: node.serviceCode,
                                symbolSize: node.psize,
                                symbolSize1: node.csize,
                                category: node.category,
                                itemStyle: {
                                    normal: {
                                        color: node.color
                                    }
                                }
                            };
                        }),
                        edges: this.list2.map(function (edge) {
                            return {
                                source: edge.sourceId,
                                target: edge.targetId
                            };
                        }),
                        label : { //=============图形上的文本标签
                            normal : {
                                show : true, //是否显示标签。
                                position : 'right', //标签的位置。['50%', '50%'] [x,y]
                                /*textStyle : { //标签的字体样式
                                    color : '#333', //字体颜色
                                    fontStyle : 'normal', //文字字体的风格 'normal'标准 'italic'斜体 'oblique' 倾斜
                                    fontWeight : 'bolder', //'normal'标准'bold'粗的'bolder'更粗的'lighter'更细的或100 | 200
                                    fontFamily : 'sans-serif', //文字的字体系列
                                    fontSize : 12 //字体大小
                                },*/
                                formatter: function(params){
                                    return params.data.name;
                                },
                            },
                            emphasis : { //高亮状态
                                textStyle : { //标签的字体样式
                                    // color : '#a25fbc', //字体颜色
                                    fontStyle : 'normal', //文字字体的风格 'normal'标准 'italic'斜体 'oblique' 倾斜
                                    fontWeight : 'bolder', //'normal'标准'bold'粗的'bolder'更粗的'lighter'更细的或100 | 200
                                    fontFamily : 'sans-serif', //文字的字体系列
                                    fontSize : 12 //字体大小
                                }
                            }
                        },
                        edgeSymbol: [ 'arrow', 'none' ],
                        roam: true,
                        focusNodeAdjacency: true, //是否在鼠标移到节点上的时候突出显示节点以及节点的边和邻接节点
                        lineStyle : { //==========关系边的公用线条样式。
                            normal : {
                                color: '#333',
                                width : '1',
                                type : 'solid', //线的类型 'solid'（实线）'dashed'（虚线）'dotted'（点线）
                                curveness : 0.3, //线条的曲线程度，从0到1
                                opacity : 0.6
                                // 图形透明度。支持从 0 到 1 的数字，为 0 时不绘制该图形。默认0.5
                            },
                            emphasis : { //高亮状态
                                width : '2',
                                color: '#333',
                                type : 'solid', //线的类型 'solid'（实线）'dashed'（虚线）'dotted'（点线）
                                curveness : 0.3, //线条的曲线程度，从0到1
                                opacity : 1
                            }
                        },
                        edgeLabel : { //==============线条的边缘标签
                            normal : {
                                show : false,
                                textStyle: {
                                    fontSize: 10
                                }
                            },
                            emphasis : { //高亮状态
                                show : false,
                                textStyle: {
                                    fontSize: 12
                                }
                            }
                        },
                        categories:[
                            {name: '知识点类别1'},
                            {name: '知识点类别2'},
                            {name: '知识点类别3'},
                        ]
                    }],
                    tooltip: { //==============显示鼠标移入的显示
                        triggerOn: 'mousemove', //点击  mousemove
                        enterable: true,
                        hideDelay: 50,
                        padding: 0,
                        confine: true,
                        formatter: function(params, ticket, callback) {
                            if (params.dataType === 'node') {
                                var html = '';
                                html += '<div class="dialogShow"><h5>依赖的服务数量为：' + params.data.symbolSize + '</h5>'
                                html += '<div>被依赖的服务数量为：' + params.data.symbolSize1 + '</div>'
                                html += '</div>'
                                return html;
                            } else if (params.dataType === 'edge') {
                                var html1 = '';
                                html1 += '<div class="dialogShow"><h5>内容' + params.data.source + '</h5></div>';
                                return html1;
                            }
                        }
                    }
                }

                console.log(this.list1);
                myChart.setOption(option);
            },

            GetRandom (list) {
                for (var i = 0; i < list.length; i++) {
                    var x = Math.floor(Math.random() * 400);
                    var y = Math.floor(Math.random() * 400);
                    var colorAll = ['#a75ebc', '#0025ff', '#ff7e00', '#289c00', '#cccccc'];
                    var n = Math.floor(Math.random() * 3);
                    var color = colorAll[n];
                    this.list1[i].x = x;
                    this.list1[i].y = y;
                    this.list1[i].color = color;
                }
            },
        }
    }
</script>

<style scoped>

</style>