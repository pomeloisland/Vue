<template>
  <!--所有的元素必须在根节点下-->
  <div>
    <h1>个人信息页</h1>
    {{id}}
  </div>

</template>

<script>
export default {
  name: "UserProfile",
  props: ['id'],
  //过滤器
  beforeRouteEnter:(to,from,next)=>{
    next(vm => {
      vm.getData();//进入路由执行getData;
    });
  },
  beforeRouteLeave:(to, from, next)=>{
    next();
  },
  methods: {
    getData: function () {
      this.axios({
        method: 'get',
        url: 'http://localhost:8080/static/mock/data.json'
      }).then(function (response) {
          console.log(response);
      });
    }
  }
}
</script>

<style scoped>

</style>
