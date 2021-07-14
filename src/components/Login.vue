<template>
  <div>
    <div id="content">
      <a>欢迎登录</a>
      <br>
      <input type="text" class="srl" placeholder="请输入帐号" :rules="formRules" v-model="from_sub.username">
      <br>
      <input type="text" class="srl" placeholder="请输入密码" :rules="formRules" v-model="from_sub.password">
      <br>
      <input type="submit" @click="onsubmit()" class="srl" value="登录">
    </div>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Login',
  data () {
    return {
      from_sub: {
        'username': '',
        'password': ''
      },
      formRules: {
        username: [
          {required: true, message: '请输入用户名', trigger: 'blur'},
          {min: 2, max: 10, message: '长度在 2 到 10 个字符', trigger: 'blur'}
        ],
        password: [
          {required: true, message: '请输入密码', trigger: 'blur'},
          {min: 2, max: 10, message: '长度在 2 到 10 个字符', trigger: 'blur'}
        ]
      }
    }
  },
  methods: {
    onsubmit () {
      var formData = JSON.stringify(this.from_sub)
      // console.log(this.from_sub)
      console.log(111, formData)
      axios({
        method: 'post',
        url: 'http://127.0.0.1:5000/login',
        headers: {
          'Content-Type': 'text/json'
        },
        withCredentials: true,
        data: formData
      }).then((res) => {
        alert(res.data)
      })
    }
  }
}
</script>

<style scoped>
#content {
  height: 500px;
  width: 700px;
  background-color: antiquewhite;
  margin: 200px auto auto auto;
}

.srl {
  width: 200px;
  height: 30px;
  margin: auto auto 10px auto;
}
</style>
