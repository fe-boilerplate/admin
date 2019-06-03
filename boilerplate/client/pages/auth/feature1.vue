<template>
  <div>123</div>
</template>
<style>
.el-container {
  display: flex;
  flex: 1;
}
#__layout > .el-container {
  height: 100vh;
}
.el-container {
}
.el-header,
.el-footer {
  background-color: #b3c0d1;
  color: #333;
  line-height: 60px;
}

.el-aside {
  color: #333;
}
</style>
<script>
export default {
  meta: {
    icon: 1,
    title: '123'
  },
  head: {
    title: 'Feature1 page 🚀'
  },
  data() {
    // console.log(this.$router.options.routes)
    setTimeout(() => {
      // console.log(123, this.$route)
    }, 500)
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    }
    return {
      tableData: Array(20).fill(item)
    }
  },
  components: {}
}
</script>
