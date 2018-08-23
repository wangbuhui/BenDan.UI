<template>
    <a-layout style="height: 100vh" id="admin-layout">
        <a-layout-sider :trigger="null" collapsible v-model="collapsed" :width="256">
            <div class="admin-logo">
                <img :src="logo" v-if="collapsed" />
                <img v-if="!collapsed" class="maxlogo" :src="maxlogo" />
            </div>
            <a-menu theme="dark" mode="inline">
                <a-sub-menu key="sub1">
                    <span slot="title">
                                    <a-icon type="dashboard" />
                                    <span>控制台</span>
                    </span>
                    <a-menu-item key="1">概要</a-menu-item>
                    <a-menu-item key="2">备份</a-menu-item>
                    <a-menu-item key="3">个人设置</a-menu-item>
                </a-sub-menu>
                <a-sub-menu key="sub2">
                    <span slot="title">
                                    <a-icon type="edit" />
                                    <span>撰写创作</span>
                    </span>
                    <a-menu-item key="4">撰写文章</a-menu-item>
                    <a-menu-item key="5">创建页面</a-menu-item>
                </a-sub-menu>
                <a-sub-menu key="sub3">
                    <span slot="title">
                                    <a-icon type="appstore-o" />
                                    <span>系统管理</span>
                    </span>
                    <a-menu-item key="6">文章</a-menu-item>
                    <a-menu-item key="7">独立页面</a-menu-item>
                    <a-menu-item key="8">评论</a-menu-item>
                    <a-menu-item key="9">分类</a-menu-item>
                    <a-menu-item key="10">标签</a-menu-item>
                    <a-menu-item key="11">文件</a-menu-item>
                    <a-menu-item key="12">用户</a-menu-item>
                </a-sub-menu>
                <a-sub-menu key="sub4">
                    <span slot="title">
                                    <a-icon type="setting" />
                                    <span>基础设置</span>
                    </span>
                    <a-menu-item key="13">基本</a-menu-item>
                    <a-menu-item key="14">评论</a-menu-item>
                    <a-menu-item key="15">阅读</a-menu-item>
                    <a-menu-item key="16">永久链接</a-menu-item>
                </a-sub-menu>
            </a-menu>
        </a-layout-sider>
        <a-layout>
            <a-layout-header style="background: #fff;     padding: 0 12px 0 0;
    -webkit-box-shadow: 0 1px 4px rgba(0,21,41,.08);
    box-shadow: 0 1px 4px rgba(0,21,41,.08);">
                <a-icon class="trigger" :type="collapsed ? 'menu-unfold' : 'menu-fold'" @click="()=> collapsed = !collapsed" />
                <div style="float: right;padding:0 20px">
                    <span style="margin:0 30px;">
                    <a-badge count="12">
                        <a-icon style="font-size: 16px; padding: 4px" type="bell" />
                    </a-badge>
                    </span>
                    <a-dropdown style="display: inline-block; height: 100%; vertical-align: initial">
                        <span style="cursor: pointer">
                              <a-avatar class="avatar" size="small" shape="circle" :src="logo"/>
                             <span>笨蛋</span>
                        </span>
                        <a-menu style="width: 150px" slot="overlay">
                            <a-menu-item>
                                <a-icon type="user" />
                                <span>个人中心</span>
                            </a-menu-item>
                            <a-menu-item>
                                <a-icon type="setting" />
                                <span>设置</span>
                            </a-menu-item>
                            <a-menu-divider />
                            <a-menu-item>
                                <router-link to="/login">
                                    <a-icon type="poweroff" />
                                    <span>退出登录</span>
                                </router-link>
                            </a-menu-item>
                        </a-menu>
                    </a-dropdown>
                </div>
            </a-layout-header>
            <a-layout-content :style="{ margin: '24px 16px', padding: '24px', background: '#fff', minHeight: '280px' }">
                Content
            </a-layout-content>
        </a-layout>
    </a-layout>
</template>
<script>
    import logo from "@/assets/logo.png";
    import maxlogo from "@/assets/maxlogo.png";
    export default {
        data() {
            return {
                collapsed: false,
                logo,
                maxlogo
            };
        }
    };
</script>
<style lang="less">
    #admin-layout .trigger {
        font-size: 18px;
        line-height: 64px;
        padding: 0 24px;
        cursor: pointer;
        transition: color 0.3s;
    }
    #admin-layout .trigger:hover {
        color: #1890ff;
    }
    #admin-layout .admin-logo {
        height: 64px;
        line-height: 64px;
        text-align: center;
        background: #052842;
        img {
            height: 45px;
            border-radius: 10px;
        }
    }
    .avatar {
        margin: 20px 4px 20px 0;
        color: #1890ff;
        background: hsla(0, 0%, 100%, .85);
        vertical-align: middle;
    }
</style>