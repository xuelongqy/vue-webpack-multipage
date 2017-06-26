<template>
  <div id="app">
    <header>
      <!--侧边栏-->
      <ul id="slide-out" class="side-nav fixed">
        <!--侧边栏头部-->
        <li><div class="userView">
          <div class="background">
            <img src="./assets/img/side-nev_bg.jpg">
          </div>
          <a href="javascript:void(0)"><img class="circle" src="./assets/img/side-nev_head.jpg"></a>
          <a href="javascript:void(0)"><span class="white-text name">QY-Store</span></a>
          <a href="javascript:void(0)"><span class="white-text email">商品信息及数据分析</span></a>
        </div></li>

        <!--分级列表-->
        <li><ul class="collapsible" id="menu-list">

          <!--商品分析-->
          <li>
            <a href="javascript:void(0)" class="collapsible-header waves-effect waves-teal"><i class="material-icons">shop</i>商品分析</a>
            <div class="collapsible-body">
              <ul>
                <li><a href="#/commodity@commodity_info" class="waves-effect waves-teal menu-item">商品信息</a></li>
                <li><a href="#/commodity@commodity_time" class="waves-effect waves-teal menu-item">商品入库时间段</a></li>
                <li><a href="#/commodity@commodity_type" class="waves-effect waves-teal menu-item">商品类型统计</a></li>
              </ul>
            </div>
          </li>

          <!--销售分析-->
          <li>
            <a href="javascript:void(0)" class="collapsible-header waves-effect waves-teal"><i class="material-icons">assignment</i>销售分析</a>
            <div class="collapsible-body">
              <ul>
                <li><a href="#/sale@sale_info" class="waves-effect waves-teal menu-item">销售信息</a></li>
                <li><a href="#/sale@sale_time" class="waves-effect waves-teal menu-item">销售时间段</a></li>
                <li><a href="#/sale@sale_type" class="waves-effect waves-teal menu-item">分类商品销售统计</a></li>
              </ul>
            </div>
          </li>

          <!--环境分析-->
          <li>
            <a href="javascript:void(0)" class="collapsible-header waves-effect waves-teal"><i class="material-icons">visibility</i>环境分析</a>
            <div class="collapsible-body">
              <ul>
                <li><a href="#/environment@area_info" class="waves-effect waves-teal menu-item">区域信息</a></li>
                <li><a href="#/environment@area_sale_time" class="waves-effect waves-teal menu-item">区域时间段销售份额</a></li>
                <li><a href="#/environment@area_trends" class="waves-effect waves-teal menu-item">区域活跃度</a></li>
              </ul>
            </div>
          </li>

          <!--用户分析-->
          <li>
            <a href="javascript:void(0)" class="collapsible-header waves-effect waves-teal"><i class="material-icons">account_box</i>用户分析</a>
            <div class="collapsible-body">
              <ul>
                <li><a href="#/user@user_info" class="waves-effect waves-teal menu-item">用户信息</a></li>
                <li><a href="#/user@user_spending" class="waves-effect waves-teal menu-item">用户消费</a></li>
                <li><a href="#/user@user_stay" class="waves-effect waves-teal menu-item">用户留存率</a></li>
                <li><a href="#/user@user_trends" class="waves-effect waves-teal menu-item">用户活跃度</a></li>
                <li><a href="#/user@user_usetime" class="waves-effect waves-teal menu-item">用户使用时间段</a></li>
              </ul>
            </div>
          </li>

          <!--管理-->
          <li>
            <a href="javascript:void(0)" class="collapsible-header waves-effect waves-teal"><i class="material-icons">settings</i>管理</a>
            <div class="collapsible-body">
              <ul>
                <li><a href="#/management@management_commodity" class="waves-effect waves-teal menu-item">商品管理</a></li>
                <li><a href="#/management@management_staff" class="waves-effect waves-teal menu-item">员工管理</a></li>
                <li><a href="#/management@management_area" class="waves-effect waves-teal menu-item">区域管理</a></li>
              </ul>
            </div>
          </li>

          <!--关于-->
          <li>
            <a href="#/about" class="collapsible-header waves-effect waves-teal menu-item"><i class="material-icons">info</i>关于</a>
          </li>
        </ul></li>


      </ul>
      <!--顶部栏-->
      <nav class="extended-nav indigo z-depth-2">
        <div class="nav-wrapper">
          <!--菜单按钮-->
          <a href="#" data-activates="slide-out" class="button-collapse waves-effect"><i class="material-icons">menu</i></a>
          <a href="#" class="brand-logo hide-on-small-and-down"><p class="nav-name">商品信息</p></a>
          <!--右侧导航-->
          <ul class="right">
            <li><a href="#" class="waves-effect"><i class="material-icons left">contacts</i><span class="hide-on-med-and-down">联系</span></a></li>
            <li><a href="#" class="waves-effect"><i class="material-icons left">more</i><span class="hide-on-med-and-down">更多</span></a></li>
            <li><a href="#" class="waves-effect"><i class="material-icons left">info</i><span class="hide-on-med-and-down">信息</span></a></li>
          </ul>
        </div>
      </nav>
    </header>
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
  window.$ = window.jQuery = require('materialize-css/node_modules/jquery/dist/jquery.js')
  require('materialize-css')
export default {
  name: 'app',
  //  页面加载之前
  created() {
  },
  //  页面加载后
  mounted() {
    //注册菜单和侧边栏分级事件
    $(".button-collapse").sideNav();
    $('.collapsible').collapsible();

    //菜单列表点击隐藏
    $('.menu-item').click(function () {
      $('#menu-list').sideNav('hide');
    })
  }
}
</script>

<style>
  @import "../../../node_modules/materialize-css/bin/materialize.css";
  #app {
  }

  /*侧边栏头部背景*/
  .side-nav .userView .background img {
    width: 100%;
  }

  /*导航名字*/
  .nav-name {
    margin: 0 15px;
    padding:0;
    font-size: 16px;
  }

  /*右侧导航栏图标*/
  .nav-wrapper .right li a i{
    padding: 0;
    margin: 0;
    font-size: 16px;
  }
  /*右侧导航栏文字*/
  .nav-wrapper .right li a span{
    margin-left: 8px;
  }

  /*为大屏幕的侧边栏提供空间*/
  header, main, footer {
    padding-left: 300px;
  }

  /*主干区域*/
  main {
    position: fixed;
    width: 100%;
    height: calc(100% - 64px);
    z-index: -1;
  }

  @media only screen and (max-width : 992px) {
    header, main, footer {
      padding-left: 0;
    }
  }
</style>
