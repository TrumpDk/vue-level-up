<template>
  <div>
    <span>{{ userInfo.userName }}</span>
    <k-form :model="userInfo" :rules="rules" ref="longForm">
      <k-form-item label="用户名" prop="userName">
        <k-input
          v-model="userInfo.userName"
          placeholder="请输入用户名"
        ></k-input>
      </k-form-item>
      <k-form-item label="密码" prop="password">
        <k-input v-model="userInfo.password" placeholder="请输入密码"></k-input>
      </k-form-item>
      <k-form-item>
        <button @click="login">登录</button>
      </k-form-item>
    </k-form>
  </div>
</template>

<script>
import KForm from "@/components/KForm/KForm.vue";
import KFormItem from "@/components/KForm/KFormItem.vue";
import KInput from "@/components/KForm/KInput.vue";
export default {
  components: {
    KForm,
    KInput,
    KFormItem,
  },
  data() {
    return {
      userInfo: {
        userName: "test",
        password: "",
      },
      rules: {
        userName: [{ requird: true, message: "请输入用户名" }],
        password: [{ required: true, message: "请输入密码" }],
      },
    };
  },
  methods: {
    login() {},
  },
};
</script>

<style lang="scss" scoped></style>
