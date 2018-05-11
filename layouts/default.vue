<template>
  <el-container>
    <el-header>
      <el-menu
        :default-active="activeIndex"
        mode="horizontal"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b"
        router>
        <el-menu-item index="/">最热</el-menu-item>
        <el-menu-item index="/new">最新</el-menu-item>
        <el-menu-item index="/about">关于</el-menu-item>
      </el-menu>
    </el-header>
    <el-main> 
        <nuxt/>
    </el-main>
    <el-footer>
      copyright@diankr.cn
    </el-footer>
</el-container>
</template>

<script>
import MyFooter from '../components/Footer.vue'

export default {
  components: {
    MyFooter
  },
  data () {
    return {
      activeIndex: '/',
    }
  },
  methods: {
  },
}
</script>

<style>
.el-container {
  min-width: 960px;
}

.el-footer {
  display: flex;
  align-items: center;
  justify-content: space-between;
  background-color: #f7fbfd;
  line-height: 60px;
}

.container
{
  margin: 0;
  width: 100%;
  padding: 100px 0;
  text-align: center;
}
</style>
