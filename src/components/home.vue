<template>
  <div class="home">
    <head-top></head-top>
    <el-container style="height:100%">
      <div style="border-right:1px solid #dcdfe6;" :style="height" class="leftm">

  
        <el-aside width="200px">

          
          <el-menu :default-active="$route.path" style="min-height: 100%;" router>
            <el-menu-item index="/home/first">
              <i class="el-icon-odometer"></i>
              <span slot="title">罗盘项目管理系统</span>
            </el-menu-item>
            
            <el-submenu index="2">
              <template slot="title">
                <i class="el-icon-aim"></i>
                <span>系统管理</span>
              </template>
              <el-menu-item-group>
                <el-menu-item index="/home/peopleTable">人员管理</el-menu-item>
              </el-menu-item-group>

              <el-menu-item-group>
                <el-menu-item index="/home/deptList">部门管理</el-menu-item>
              </el-menu-item-group>
            </el-submenu>

            <el-submenu index="3">
              <template slot="title">
                <i class="el-icon-s-promotion"></i>
                <span>业务管理</span>
              </template>

              <el-menu-item-group>
                <el-menu-item index="/home/materialNum">业务申请</el-menu-item>
              </el-menu-item-group>

              <el-menu-item-group>
                <el-menu-item index="/home/materialInfo">业务审批</el-menu-item>
              </el-menu-item-group>

              <el-menu-item-group>
                <el-menu-item index="/home/materialD">业务数据</el-menu-item>
              </el-menu-item-group>
            </el-submenu>

            <el-submenu index="4">
              <template slot="title">
                <i class="el-icon-shopping-bag-1"></i>
                <span>计划管理</span>
              </template>
              <el-menu-item-group>
                <el-menu-item index="/home/needPlan">需求计划申请</el-menu-item>
              </el-menu-item-group>

              <el-menu-item-group>
                <el-menu-item index="/home/needPlanp">需求计划审批</el-menu-item>
              </el-menu-item-group>

              <el-menu-item-group>
                <el-menu-item index="/home/pruchase">项目申请</el-menu-item>
              </el-menu-item-group>

              <el-menu-item-group>
                <el-menu-item index="/home/No">项目通过</el-menu-item>
              </el-menu-item-group>
            </el-submenu>

              <el-menu-item index="/home/webMap">
              <i class="el-icon-discover"></i>
              <span slot="title">地图查看</span>
            </el-menu-item>

            <el-menu-item index="/home/materialD">
              <i class="el-icon-s-claim"></i>
              <span slot="title">数据管理</span>
            </el-menu-item>


          
          </el-menu>
        </el-aside>
      </div>

      <el-container>
        <!-- 主要内容 -->
        <el-main>
          <!-- <web-map></web-map> -->

          <div class="bar">
            <nav-bar></nav-bar>
          </div>
          <transition name="slide-fade">
            <router-view></router-view>
          </transition>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
import headTop from "./headTop.vue";
import webMap from "../page/webMap.vue";
import userList from "../page/userList";
import charts from "../page/someCharts";
import materialInfo from "../page/materialInfo";
import navBar from "../components/navBar";
export default {
  data() {
    return {
      height: {
        height: ""
      },
      isCollapse: true
    };
  },
  components: {
    headTop,
    webMap,
    navBar
  },
  mounted() {},
  methods: {
    hh() {
      this.height.height = window.innerHeight - 60 + "px";
    },
    handleOpen(key, keyPath) {
      console.log(key, keyPath);
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath);
    }
  },
  created() {
    this.hh();
  },
  computed: {},
  watch: {}
};
</script>

<style>
html,
body {
  margin: 0;
  padding: 0;
  font-family: sans-serif;
  background-color: #fff;
  height: 100%;
}

.el-aside {
  background-color: #545c64;
}
.el-menu {
  border: none;
}
.bar {
  margin-bottom: 8px;
}
.slide-fade {
  position: absolute;
  left: 0;
  right: 0;
}
.slide-fade-enter-active {
  transition: all 1.2s ease;
}
.slide-fade-leave-active {
  transition: all 0.1s cubic-bezier(2, 0.5, 0.8, 1);
}
.slide-fade-enter,
.slide-fade-leave-to {
  left: 0;
  right: 0;
  transform: translateX(50px);
  opacity: 0;
}
.el-menu-item-group__title {
  padding: 0px 0px 0px 20px;
}
</style>
