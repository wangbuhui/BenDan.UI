<template>
    <a-layout style="height: 100vh" id="admin-layout">
        <a-layout-sider :trigger="null" collapsible v-model="collapsed" :width="256">
            <div class="admin-logo">
                <img :src="logo" v-if="collapsed"/>  
           
                 <img  v-if="!collapsed"  class="maxlogo" :src="maxlogo"/>
            
            </div>
            <a-menu theme="dark" :defaultSelectedKeys="['1']" mode="inline">
                <a-menu-item key="1">
                    <a-icon type="pie-chart" />
                    <span>仪表盘</span>
                </a-menu-item>
                <a-menu-item key="2">
                    <a-icon type="desktop" />
                    <span>Option 2</span>
                </a-menu-item>
                <a-sub-menu key="sub1">
                    <span slot="title">
                        <a-icon type="user" />
                        <span>User</span>
                    </span>
                    <a-menu-item key="3">Tom</a-menu-item>
                    <a-menu-item key="4">Bill</a-menu-item>
                    <a-menu-item key="5">Alex</a-menu-item>
                </a-sub-menu>
                <a-sub-menu key="sub2">
                    <span slot="title">
                        <a-icon type="team" />
                        <span>Team</span>
                    </span>
                    <a-menu-item key="6">Team 1</a-menu-item>
                    <a-menu-item key="8">Team 2</a-menu-item>
                </a-sub-menu>
                <a-menu-item key="9">
                    <a-icon type="file" />
                    <span>File</span>
                </a-menu-item>
            </a-menu>
        </a-layout-sider>
        <a-layout>
            <a-layout-header style="background: #fff; padding: 0">
                <a-icon class="trigger" :type="collapsed ? 'menu-unfold' : 'menu-fold'" @click="()=> collapsed = !collapsed" />
            </a-layout-header>
            <a-layout-content :style="{ margin: '24px 16px', padding: '24px', background: '#fff', minHeight: '280px' }">
                Content
            </a-layout-content>
        </a-layout>
    </a-layout>
</template>
<script>
import logo from '@/assets/logo.png';
import maxlogo from '@/assets/maxlogo.png';
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
 
  img {
      height: 56px;  
         border-radius: 10px;  
  }
}


</style>