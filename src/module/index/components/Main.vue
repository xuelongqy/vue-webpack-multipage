<template>
  <iframe v-bind:src="getPagePath" width="100%" height="100%" frameborder="0" id="external-frame"></iframe>
</template>

<script>
  export default {
    name: 'main',
    data () {
      return {
        //缓存页面路径
        page_path: 'about.html',
        //页面容器,用于存放需要跳转页面的路径
        page_list: {
          //index
          'index': 'index.html',
          //about
          'about': 'about.html',
          //commodity
          'commodity@commodity_info': 'commodity/commodity_info.html',
          'commodity@commodity_time': 'commodity/commodity_time.html',
          'commodity@commodity_type': 'commodity/commodity_type.html',
          //sale
          'sale@sale_info': 'sale/sale_info.html',
          'sale@sale_time': 'sale/sale_time.html',
          'sale@sale_type': 'sale/sale_type.html',
          //environment
          'environment@area_info': 'environment/area_info.html',
          'environment@area_sale_time': 'environment/area_sale_time.html',
          'environment@area_trends': 'environment/area_trends.html',
          //user
          'user@user_info': 'user/user_info.html',
          'user@user_spending': 'user/user_spending.html',
          'user@user_stay': 'user/user_stay.html',
          'user@user_trends': 'user/user_trends.html',
          'user@user_usetime': 'user/user_usetime.html',
          //management
          'management@management_area': 'management/management_area.html',
          'management@management_commodity': 'management/management_commodity.html',
          'management@management_staff': 'management/management_staff.html',
          //baidu
          'baidu': 'http://www.baidu.com'
        }
      }
    },
    computed: {
        //获取页面路径
        getPagePath (){
          if (this.page_list[this.$route.params.page_path]) {
            this.page_path = this.page_list[this.$route.params.page_path]
          }
          else if(this.$route.params.page_path == '!') {
            return this.page_path
          }
          else {
            this.page_path = this.page_list['about']
          }
          return this.page_path
        }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  iframe {
    padding: 3px;
  }
</style>
