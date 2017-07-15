<template>
  <div id='tmpl'>
             <mt-swipe :auto="1000">
                <mt-swipe-item v-for="item in list">
                    <img :src="item.img" id="img">
                </mt-swipe-item>  
            </mt-swipe>

            <!--九宫格-->
            <div class="mui-slider-item">
						<ul class="mui-table-view mui-grid-view mui-grid-9">
							<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">
								<router-link to="/news/newslist">
									<span class="mui-icon mui-icon-home"></span>
									<div class="mui-media-body">新闻资讯</div>
								</router-link>
							</li>
							<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">
								<router-link to="/photo/photolist">
									<span class="mui-icon mui-icon-email"></span>
									<div class="mui-media-body">图片分享</div>
								</router-link>
							</li>
							<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">
								<router-link to="/goods/goodslist">
									<span class="mui-icon mui-icon-chatbubble"></span>
									<div class="mui-media-body">商品购买</div>
								</router-link>
							</li>
							<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">
								<router-link to="/feedback">
									<span class="mui-icon mui-icon-location"></span>
									<div class="mui-media-body">留言反馈</div>
								</router-link>
							</li>
							<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">
								<router-link to="/video">
									<span class="mui-icon mui-icon-search"></span>
									<div class="mui-media-body">视频专区</div>
								</router-link>
							</li>
							<li class="mui-table-view-cell mui-media mui-col-xs-4 mui-col-sm-3">
								<router-link to="/callme">
									<span class="mui-icon mui-icon-phone"></span>
									<div class="mui-media-body">联系我们</div>
								</router-link>
							</li>
						</ul>
					</div>
  </div>
</template>
<script>
import { Toast } from 'mint-ui';
export default {
  name: "component_name",
  data () {
    return {
        list:[

        ]
    }
  },
  created(){
    this.getImg()
  },
  methods:{
      getImg(){
          var url = 'http://182.254.146.100:8899/api/getlunbo';
          this.$http.get(url).then(function(res){
              if(res.body.status!=0){
                    Toast(res.body.message)
                    return;
              }
              
            this.list=res.body.message
       })
     }
   }
}
</script>
<style lang="css" scoped>
.mint-swipe{
    height: 240px;
    width: 100%;
}
    .mint-swipe-item{
        height: 100%;
        width: 100%;
        background-color: greenyellow;
    }
    #img{
        height: 100%;
        width: 100%;
    }

    .mui-icon-home:before,
.mui-icon-email:before,
.mui-icon-chatbubble:before,
.mui-icon-location:before,
.mui-icon-search:before,
.mui-icon-phone:before {
    content: '';
    display: inline-block;
    width: 50px;
    height: 50px;
    background-repeat: round;
}
.mui-icon-home:before{
    background-image: url("../statics/imgs/1.png")
}
.mui-icon-email:before{
    background-image: url("../statics/imgs/2.png")
}
.mui-icon-chatbubble:before{
    background-image: url("../statics/imgs/3.png")
}
.mui-icon-location:before{
    background-image: url("../statics/imgs/4.png")
}
.mui-icon-search:before{
    background-image: url("../statics/imgs/5.png")
}
.mui-icon-phone:before{
    background-image: url("../statics/imgs/6.png")
}
.mui-grid-view.mui-grid-9{
    background-color: #fff;
}
.mui-grid-view.mui-grid-9 .mui-table-view-cell{
    border:none;
}
</style>