<template>
    <div class="layout">
      <div class="header">
        <div class="logo">
          掘金nuxt
        </div>
        <div class="nav">
          <mu-tabs :value="activeTab" @change="handleTabChange" class="tab">
            <mu-tab value="tab1" title="首页"/>
            <mu-tab value="tab2" title="沸点"/>
            <mu-tab value="tab3" title="小册"/>
            <mu-tab value="tab4" title="开源库"/>
            <mu-tab value="tab5" title="活动"/>
          </mu-tabs>
        </div>
      </div>
      <div class="content">
        <nuxt/>
      </div>
    </div>
</template>

<script>
import MyFooter from '../components/Footer.vue'

export default {
  components: {
    MyFooter
  },
  data () {
    return {
      activeTab: 'tab1'
    }
  },
  methods: {
    handleTabChange (val) {
      this.activeTab = val
    }
  }
}
</script>

<style scoped>
.layout{
  background-color: rgb(236, 236, 236);
}

.header{
  background-color: #7e57c2;
      position: fixed;
    width: 100%;
    left: 0;
    top: 0;
        z-index: 9999;
}

.logo{
  font-size: 24px;
  color: white;
  display: inline-block;
  padding: 10px 20px;
}

.nav{
  display: inline-block;
  width: calc(100% - 150px);
  margin: 0 auto;
}

.tab{
  margin: 0 auto;
  width: 400px;
  background-color: rgba(0, 0, 0, 0);
}

.content{
  width: 90%;
  margin: 0 auto;
  padding-top:50px;
}

.breadcrumb{
  margin: 10px 0;
}

.body{
  background-color: white;
  border-radius: 5px;
  min-height: 500px;
}

.footer{
  padding: 20px 0;
  text-align: center;
}
</style>
