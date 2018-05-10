<template>
  <!-- <div>
    <nuxt/>
    <my-footer/>
  </div> -->
    <div>
      <!-- 头部导航栏 -->
      <mu-appbar title="v2ex-nuxt">
        <mu-icon-button icon="menu" slot="left" @click="toggle(true)"/>
      </mu-appbar>

      <mu-drawer :open="open" :docked="docked" @close="toggle()">
        <!-- <mu-avatar  slot="left" src="/images/uicon.jpg" :size="40"/> -->
        <mu-list @itemClick="docked ? '' : toggle()">
          <mu-list-item title="最新" to="/new"/>
          <mu-list-item title="最热" to="/hot"/>
          <!-- <mu-list-item title="联系我" to="/about"/> -->
          <mu-list-item v-if="docked" @click.native="open = false" title="Close"/>
        </mu-list>
    </mu-drawer>



      <!-- 左侧弹框 -->
       <!-- <mu-popup position="left" popupClass="demo-popup-left" :open="leftPopup" @close="close('left')">
         <mu-list>
          <mu-list-item title="全部">
            <mu-icon slot="left" value="inbox"/>
          </mu-list-item>
          <mu-list-item title="联系我">
            <mu-icon slot="left" value="drafts"/>
          </mu-list-item>
        </mu-list>
      </mu-popup> -->
      <!-- 中间内容 -->
      <nuxt/>
      <!-- 底部栏 -->
      <my-footer/>
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
       open: false,
      docked: true,


      // bottomPopup: false,
      // topPopup: false,
      // leftPopup: false,
      // rightPopup: false
    }
  },
  methods: {
    toggle (flag) {
      this.open = !this.open
      this.docked = !flag
    },


    // open (position) {
    //   this[position + 'Popup'] = true
    // },
    // close (position) {
    //   this[position + 'Popup'] = false
    // }
  },
}
</script>

<style>
.demo-popup-left {
  display: flex;
  width: 85%;
  max-width: 375px;
  height: 100%;
  align-items: center;
  padding: 24px;
}

.container
{
  margin: 0;
  width: 100%;
  padding: 100px 0;
  text-align: center;
}

.button, .button:visited
{
  display: inline-block;
  color: #3B8070;
  letter-spacing: 1px;
  background-color: #fff;
  border: 2px solid #3B8070;
  text-decoration: none;
  text-transform: uppercase;
  padding: 15px 45px;
}

.button:hover, .button:focus
{
  color: #fff;
  background-color: #3B8070;
}

.title
{
  color: #505153;
  font-weight: 300;
  font-size: 2.5em;
  margin: 0;
}
</style>
