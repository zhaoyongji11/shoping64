<template>
  <div class="login-wrap">
    <el-form
      class="login-from"
      label-position="top"
      label-width="80px"
      :model="formdata"
    >
      <h2>用户登录</h2>
      <el-form-item label="用户名">
        <el-input v-model="formdata.username"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input v-model="formdata.password"></el-input>
      </el-form-item>
      <el-button
        @click.prevent="handleLogin()"
        type="success"
        class="login-btn"
      >登录</el-button>
    </el-form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      formdata: {
        username: "",
        password: ""
      }
    };
  },
  methods: {
    async handleLogin() {
      const res = await this.$http.post(`login`, this.formdata);
      const {
        data: {
          data:{token},
          meta: { msg, status }
        }
      } = res;
      // console.log(res)
      if (status === 200) {
        localStorage.setItem('token',token)
        this.$router.push({
          name: "home"
        });
      } else {
        this.$message.error(msg);
      }
      /*
         .then(res => {
          const {data:{data,meta:{msg,status}}} =res
          if(status===200){
          this.$router.push({
            name:'home'
          })
          }else{
             this.$message.error(msg);
          }
        })
        .catch(err=>{

        })
        */
    }
  }
};
</script>

<style>
.login-wrap {
  height: 100%;
  background-color: #324152;
  display: flex;
  justify-content: center;
  align-items: center;
}
.login-from {
  background-color: #fff;
  border-radius: 5px;
  width: 400px;
  padding: 20px;
}
.login-btn {
  width: 100%;
}
</style>
