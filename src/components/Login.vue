<template>
  <div class="wrap">
    <el-container>
      <el-header height="100px">{{role}}</el-header>
      <el-main>
        <div class="login">
          <el-form :label-position="labelPosition" label-width="60px" v-model="form">
            <el-form-item label="用户名">
              <el-input v-model="form.username"></el-input>
            </el-form-item>
            <el-form-item label="密码">
              <el-input type="password" v-model="form.pwd"></el-input>
            </el-form-item>
            <el-form-item>
              <el-input v-model="form.validatecode" placeholder="请输入验证码" size="medium"></el-input>
              <el-popover ref="a" placement="right-end" trigger="hover">
								<img alt="验证码图片" width="200px">
							</el-popover>
            </el-form-item>
          </el-form>
          <el-button>登录</el-button>
        </div>
      </el-main>
    </el-container>
  </div>
</template>

<script>
export default {
  data () {
    return {
      labelPosition: 'left',
      role: 'student',
      form: {
        username: '',
        pwd: '',
        validatecode: ''
      }
    }
  },
  methods: {
    login () {

    }
  },
  mounted () {
    var url = location.href.split('?')
    this.role = url[1]
    console.log(this.role)
  }
}
</script>

<style scoped>
.el-header {
  background-color: #f0a44a;
  color: #333;
  text-align: center;
  line-height: 60px;
}
.el-main {
  background-color: #E9EEF3;
  color: #333;
  text-align: center;
  line-height: 160px;
}
.login {
  padding: 30px 20px;
  width: 400px;
  height: 300px;
  background-color: #fcd4a4;
  margin-left: 1000px;
  margin-top: 250px;
  margin-bottom: 250px;
}
.el-button {
  background-color: #ffa53b;
}
</style>


