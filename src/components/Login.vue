<template>
  <div>
    <div id="content">
      <a>欢迎登录</a>
      <br>
      <input type="text" class="srl" placeholder="请输入帐号">
      <br>
      <input type="text" class="srl" placeholder="请输入密码">
      <br>
      <button type="submit" class="srl">登录</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login'
}
</script>

<style scoped>
#content {
  height: 500px;
  width: 700px;
  background-color: #42b983;
  margin: 200px auto auto auto;
}
.srl{
  width: 200px;
  height: 30px;
  margin: auto auto 10px auto;
}
</style>
