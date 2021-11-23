<template>
  <div class="firstdemo">
    <el-form ref="form" :model="form" label-width="80px">
      <el-row type="flex" justify="center">
        <el-col :span="5">
          <el-form-item label="用户名">
            <el-input v-model="form.name"></el-input>
          </el-form-item>
        </el-col>
      </el-row>
      <el-row type="flex" justify="center">
        <el-col :span="5">
          <el-form-item label="密码">
            <el-input v-model="form.password"></el-input>
          </el-form-item>
        </el-col>
      </el-row>

      <el-row type="flex" justify="center">
        <el-col :span="5">
          <el-form-item>
            <el-button type="primary" @click="onSubmit">登陆</el-button>
            <el-button>注册</el-button>
          </el-form-item>
        </el-col>
      </el-row>
    </el-form>
  </div>
</template>
<script>
export default {
  name: "fisrtdemo",
  data() {
    return {
      form: {
        name: "",
        password: ""
      }
    };
  },
  methods: {
    onSubmit() {
      if (this.form.name == "admin" && this.form.password == "123456") {
        this.$message({
          message: '登陆成功',
          type: 'success'
        });
        this.$router.push({path: "/Home"});
      } else {
        this.$message.error('登陆失败');
      }
    }
  }
};
</script>
<style lang="stylus" scoped></style>