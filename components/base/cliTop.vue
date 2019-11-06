<template>
    <div class="menu">
        <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
            <el-menu-item index="1">用户登录</el-menu-item>
            <el-menu-item index="2">系统设置</el-menu-item>
            <el-menu-item index="3">联系我们</el-menu-item>
        </el-menu>
    </div>
</template>

<script>
    export default {
        name: "cliTop",
        data() {
            return {
                activeIndex: '1',
            };
        },
        methods: {
            handleSelect(key, keyPath) {
                console.log(key, keyPath);
            }
        }
    }
</script>

<style scoped>

    .menu{
        /*float: right;*/
        margin-right: 40px;
        z-index: 1;

    }
</style>