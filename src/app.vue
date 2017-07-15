<template>
  <div id='tmpl'>
      <mt-header fixed title="Vue商城系统"></mt-header>

			<!-- 2.0 利用vue-router的 <router-view>进行占位 -->
     <router-view></router-view>
      <!--轮播图-->
    

<!--底部选项卡-->
      <nav class="mui-bar mui-bar-tab">
			<router-link class="mui-tab-item mui-active" to="/home">
				<span class="mui-icon mui-icon-home"></span>
				<span class="mui-tab-label">首页</span>
			</router-link>
			<router-link class="mui-tab-item" to="#tabbar-with-chat">
				
				<span class="mui-tab-label">会员</span>
			</router-link>
			<router-link class="mui-tab-item" to="#tabbar-with-contact">
				<!--<span class="mui-icon mui-icon-contact"></span>-->
        <span class="mui-icon mui-icon-email"><span class="mui-badge">9</span></span>
				<span class="mui-tab-label">购物车</span>
			</router-link>
			<router-link class="mui-tab-item" to="#tabbar-with-map">
				<span class="mui-icon mui-icon-gear"></span>
				<span class="mui-tab-label">搜索</span>
			</router-link>
		</nav>


  </div>
  
</template>
<script>
export default {
   name: "component_name",
  data() {
    return {
    };
  }
}
</script>
<style lang="css" scoped>

</style>