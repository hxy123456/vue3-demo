<template>
  <div class="login-page">
    <!-- Header -->
    <div class="header">
      <van-icon name="cross" size="24" color="#333" class="close-icon" />
    </div>

    <!-- Logo -->
    <div class="logo-container">
      <div class="logo">
        <div class="shape shape-left"></div>
        <div class="shape shape-right"></div>
      </div>
    </div>

    <!-- Title -->
    <h1 class="title">欢迎来到行销平台</h1>

    <!-- Form -->
    <div class="form-container">
      <div class="input-wrapper">
        <van-icon name="manager-o" size="20" color="#999" class="input-icon" />
        <input type="text" placeholder="请输入账号" class="custom-input" v-model="form.account" />
      </div>

      <div class="input-wrapper">
        <van-icon name="closed-eye" size="20" color="#999" class="input-icon" />
        <input type="password" placeholder="请输入密码" class="custom-input" v-model="form.password" />
        <span class="forgot-text">忘记？</span>
      </div>

      <button class="login-btn" @click="handleLogin">登录</button>
      
      <div class="register-link">
        <span>注册</span>
      </div>
    </div>

    <!-- Footer Agreement -->
    <div class="footer">
      <van-checkbox v-model="form.agreed" icon-size="16px" checked-color="#4A8BFF" class="agreement-checkbox">
        <template #icon="props">
          <div class="custom-radio" :class="{ 'is-checked': props.checked }">
            <div class="radio-inner" v-if="props.checked"></div>
          </div>
        </template>
        <span class="agreement-text">阅读并同意 <a href="#">《用户协议》</a>和<a href="#">《隐私政策》</a></span>
      </van-checkbox>
    </div>
  </div>
</template>

<script setup>
import { reactive } from 'vue';
import { showToast } from 'vant';

const form = reactive({
  account: '',
  password: '',
  agreed: false,
});

const handleLogin = () => {
  if (!form.account) {
    showToast('请输入账号');
    return;
  }
  if (!form.password) {
    showToast('请输入密码');
    return;
  }
  if (!form.agreed) {
    showToast('请先阅读并同意用户协议和隐私政策');
    return;
  }
  showToast('登录成功');
};
</script>

<style scoped>
.login-page {
  min-height: 100vh;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  padding: 0 32px;
  position: relative;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
  box-sizing: border-box;
}

/* Header */
.header {
  padding-top: 54px; /* Account for status bar */
  display: flex;
  align-items: center;
}

.close-icon {
  cursor: pointer;
  margin-left: -8px;
  padding: 8px;
}

/* Logo */
.logo-container {
  display: flex;
  justify-content: center;
  margin-top: 40px;
}

.logo {
  position: relative;
  width: 80px;
  height: 80px;
  background: #f8fbff;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: inset 0 0 20px rgba(74, 139, 255, 0.05);
}

.shape {
  position: absolute;
  width: 24px;
  height: 40px;
  border-radius: 12px;
  transform: skew(-15deg);
}

.shape-left {
  background: linear-gradient(135deg, #3b82f6 0%, #2563eb 100%);
  left: 20px;
  z-index: 2;
  box-shadow: 2px 4px 10px rgba(37, 99, 235, 0.3);
}

.shape-right {
  background: linear-gradient(135deg, #60a5fa 0%, #3b82f6 100%);
  right: 20px;
  top: 24px;
  z-index: 1;
}

/* Title */
.title {
  text-align: center;
  font-size: 22px;
  font-weight: 600;
  color: #1a1a1a;
  margin-top: 24px;
  margin-bottom: 48px;
  letter-spacing: 0.5px;
}

/* Form */
.form-container {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.input-wrapper {
  display: flex;
  align-items: center;
  background-color: #f7f8fc;
  border-radius: 100px;
  padding: 0 24px;
  height: 56px;
  position: relative;
  transition: all 0.3s ease;
}

.input-wrapper:focus-within {
  background-color: #f0f4ff;
  box-shadow: 0 0 0 1px rgba(74, 139, 255, 0.2);
}

.input-icon {
  margin-right: 12px;
  flex-shrink: 0;
}

.custom-input {
  flex: 1;
  background: transparent;
  border: none;
  outline: none;
  font-size: 15px;
  color: #333;
  height: 100%;
}

.custom-input::placeholder {
  color: #b3b3b3;
}

.forgot-text {
  font-size: 14px;
  color: #999;
  cursor: pointer;
  flex-shrink: 0;
}

/* Buttons */
.login-btn {
  margin-top: 16px;
  width: 100%;
  height: 56px;
  border-radius: 100px;
  background: linear-gradient(90deg, #5b9dff 0%, #3b82f6 100%);
  color: #ffffff;
  font-size: 16px;
  font-weight: 500;
  border: none;
  outline: none;
  cursor: pointer;
  box-shadow: 0 8px 20px rgba(59, 130, 246, 0.3);
  transition: all 0.3s ease;
}

.login-btn:active {
  transform: scale(0.98);
  box-shadow: 0 4px 10px rgba(74, 139, 255, 0.2);
}

.register-link {
  text-align: center;
  margin-top: 8px;
}

.register-link span {
  font-size: 14px;
  color: #999;
  cursor: pointer;
}

/* Footer Agreement */
.footer {
  margin-top: auto;
  padding-bottom: 40px;
  display: flex;
  justify-content: center;
}

.agreement-checkbox {
  align-items: center;
}

.custom-radio {
  width: 14px;
  height: 14px;
  border-radius: 50%;
  border: 1px solid #ccc;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.2s;
}

.custom-radio.is-checked {
  border-color: #4a8bff;
}

.radio-inner {
  width: 8px;
  height: 8px;
  background-color: #4a8bff;
  border-radius: 50%;
}

.agreement-text {
  font-size: 12px;
  color: #999;
}

.agreement-text a {
  color: #4a8bff;
  text-decoration: none;
}
</style>
