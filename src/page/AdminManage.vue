<template>
    <div class="manage_page fillcontain" >
        <meta  http-equiv="Cache-Control" content="no-cache,no-store,must-revlidate">
        <meta  http-equiv="Expires" content="O">
        <meta http-equiv="Pragma" content="no-cache">

        <el-row style="height: 100%;">
            <el-col :span="4"  style="min-height: 100%; background-color: #324057;">
                <el-menu :default-active="defaultActive" style="min-height: 100%;" theme="dark" router>
                    <el-menu-item index="AdminManage"><i class="el-icon-menu"></i>首页</el-menu-item>
                    <el-submenu index="1">
                        <template slot="title"><i class="el-icon-document"></i>管理车次</template>
                        <el-menu-item index="AdminTrain">新增车次</el-menu-item>
                        <el-menu-item index="AdminTrain">修改车次</el-menu-item>
                    </el-submenu>

                    <el-submenu index="2">
                        <template slot="title"><i class="el-icon-plus"></i>管理用户</template>
                    </el-submenu>

                </el-menu>
            </el-col>
            <el-col :span="20" style="height: 100%;overflow: auto;">
                <keep-alive>
                    <router-view></router-view>
                </keep-alive>
            </el-col>
        </el-row>
    </div>
</template>
<script>
    export default {

        computed: {
            defaultActive: function(){
                return this.$route.path.replace('/', '');
            }
        },
    }
</script>


<style lang="less" scoped>
    @import '../style/mixin';
    .manage_page{

    }
</style>
