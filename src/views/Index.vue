<template>

    <el-container style="height: 500px; border: 1px solid #eee">
        <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
            <el-menu router :default-openeds="['0','1']">
                <el-submenu v-for="(item,index) in $router.options.routes" :index="index+''" v-if="item.show">
                    <template #title><i class="el-icon-setting"></i>{{item.name}}</template>
                    <el-menu-item v-for="(item2,index2) in item.children" :index="item2.path"
                                  :class="$route.path==item2.path?'is-active':''">{{item2.name}}
                    </el-menu-item>
                </el-submenu>
            </el-menu>

        </el-aside>
        <el-main>
            <router-view></router-view>
        </el-main>

    </el-container>

</template>

<script>
    export default {
        name: "Index"
    }
</script>

<style scoped>

</style>