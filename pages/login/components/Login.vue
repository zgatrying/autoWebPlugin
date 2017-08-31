<template>
  <div class="login">
    <img src="../assets/logo.png">
    <el-form label-position="right" label-width="3em" :model="form">
      <el-form-item label="账号">
        <el-input v-model="form.account"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input v-model="form.password"></el-input>
      </el-form-item>
      <el-form-item label="">
        <el-button 
          type="primary" 
          style="width: 100%;"
          @click="handleSubmit">登录</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
      form: {
        account: '',
        password: ''
      }
    }
  },
  mounted () {
    document.title = '登录'
  },
  methods: {
    handleSubmit () {
      window.location.href = 'index.html'
    }
  }
}
</script>

<style scoped>
.login {
  padding: 40px;
}
</style>
