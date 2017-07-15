<template>
  <div id='tmpl'>
        <ul class="mui-table-view">
				<li class="mui-table-view-cell mui-media" v-for="item in list">
					<router-link to="/news/newslist/:id">
						<img class="mui-media-object mui-pull-left" :src="item.img_url">
						<div class="mui-media-body">
							    <h5>{{item.title}}</h5>
							    <p class='mui-ellipsis'>{{item.zhaiyao}}</p>
                                <span>发表时间：{{item.add_time | datefmt('YYYY-MM-DD HH:mm:ss')}}</span><span class="span">点击数：{{item.click}}</span>
						</div>
                        
					</router-link>
				</li>			
			</ul>
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
    };
  },
  created(){
    this.getList()
  },
  methods:{
      getList(){
        var url="http://182.254.146.100:8899/api/getnewslist"
        this.$http.get(url).then(function(res){
            if(res.body.status!=0){
                Toast(res.body.message)
            }
            this.list=res.body.message
        })

      }
  }
}
</script>
<style lang="css" scoped>
.mui-media img{
   max-width:80px;
   width: 80px;
   height: 80px;
}
.mui-media-body>h5{
    color: #000;
    font-size: 17px;
}
.mui-media-body>p{
    margin-bottom: 10px;
}
.mui-media-body>span{
    font-size: 14px;
    color:royalblue;
    
}
.span{
margin-left: 10px;
}
</style>