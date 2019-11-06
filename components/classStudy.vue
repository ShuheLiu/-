<template>
    <div class="classStudybody">
        <div class="course">
            <el-card>
                <p style="text-align: center">4.2 结构化分析与设计</p>
                <iframe src="https://www.icourse163.org/course/UIBE-1205987812" style="width: 98%;height: 550px;margin-top: 20px;margin-left: 8px"></iframe>
            </el-card>
        </div>
        <div class="course">
            <div style="width: 100%">
            <el-card>
                <p style="text-align: center">图谱工作间</p>
                <!--<img src="../assets/image/index-background.jpg" alt="Nothing" style="height: 300px;margin-top: 20px">-->
                <draw-graph></draw-graph>
            </el-card>
            </div>
            <div style="width: 100%;margin-top: 20px;">
                <el-card>
                    <!--<el-scrollbar>-->
                    <p>课堂讨论区</p>
                    <el-card style="margin-top: 10px;height: 110px;overflow-y: scroll">
                        <div v-for="o in 10" :key="o" class="text item">
                            {{'列表内容 ' + o }}
                        </div>
                    </el-card>
                    <el-row style="margin-top: 5px">
                        <el-input placeholder="我也说两句" style="width: 83%" v-model="message"></el-input>
                        <el-button style="margin-left: 10px;background: green;color: white;padding-right: 25px" icon="el-icon-check">发送</el-button>
                    </el-row>
                    <!--</el-scrollbar>-->
                </el-card>

            </div>
        </div>
    </div>
</template>

<script>
    import DrawGraph from "./base/drawGraph";
    export default {
        name: "classStudy",
        components: {DrawGraph},
        data(){
            return{
                message:'',
            }
        }
    }
</script>

<style scoped>
    .classStudybody{
        /*background-color: black;*/
        margin-top: 20px;
        width: 100%;
        max-height: 800px;
        position: relative;
    }
    .course{
        float: left;
        width: 45%;
        margin-left: 50px;
        height: 650px;
        /*background-color: black;*/

    }
</style>