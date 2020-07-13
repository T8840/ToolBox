<template>
  <div class="modal dark">
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <span>角色名称</span>
        <el-button style="float: right; padding: 3px 0" type="text"
          >操作按钮</el-button
        >
      </div>
      <div v-for="o in 4" :key="o" class="text item">
        {{ "角色： " + o }}
      </div>
    </el-card>
    <input
      id="account"
      type="email"
      class="input"
      placeholder="邮箱帐号"
      v-model.trim="account"
    />
    <input
      id="pwd"
      type="password"
      class="input"
      placeholder="登录密码"
      v-model="password"
    />
    <p></p>
    <button @click="login"><span>登录 / 注册 </span></button>
    <span class="tip" v-show="error">{{ error }}</span>
  </div>
</template>

<style>
.box-card {
  width: 300px;
}

.input {
  font-size: 18px;
  color: black;
  background: #efeff4;
  border-radius: 5px;
  border: none;
  width: 232px;
  height: 39px;
  padding: 0 10px;
}
#account {
  margin-top: 148px;
}
#pwd {
  margin-top: 17px;
}
</style>

<script type="text/babel">
export default {
  name: "login",
  props: {
    dismiss: Function
  },

  data() {
    return {
      account: "",
      password: "",
      error: ""
      // bottom: {
      //   icons: {
      //     left: require('../assets/images/logout.png')
      //   }
      // }
    };
  },
  methods: {
    async login() {
      if (this.account.length < 5) {
        this.error = "帐号至少5位";
        return;
      }
      if (this.password.length < 6) {
        this.error = "密码至少6位";
        return;
      }
    }
  }
};
</script>
