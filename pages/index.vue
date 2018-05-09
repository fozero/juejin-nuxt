<template>
  <section class="container">
    <!-- <h1 class="title">
      hello boy~
    </h1>
    <nuxt-link class="button" to="/about">
      ABOUT
    </nuxt-link> -->
    <div class="container__left">
    	主体内容
    </div>
    <div class="container__right">
    	<ul>
    		<li v-for="(item,index) in list">
    			<div class="title" v-text="item.title"></div>
    			<div class="content" v-text="item.content"></div>
    		</li>
    	</ul>
    </div>
  </section>
</template>

<script>
// import TopicListChalk from '~/components/TopicListChalk'
import api from '../static/js/api.js'

export default {
  async asyncData ({}) {
  	return api.getLatestTopics()
  		.then((res)=>{
  			console.log(res)
  			return {list:res}
  		})
  },
  data(){
  	return {

  	}
  }

}
</script>

<style scoped>
.container__left{
	display: inline-block;
}
.container__right{
	display: inline-block;
}
ul{list-style: none;width: 400px;text-align: left;}
ul li{border-bottom: 1px solid #eee;}
ul li .title{font-size: 16px;font-weight: bold;}
ul li .content{}
/*.title
{
  margin: 50px 0;
}*/
</style>
