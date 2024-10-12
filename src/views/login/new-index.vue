<template>
    <div>
        <div class="login-container">
            <div class="left">
                <div class="system-title">{{ systemTitle }}管理系统</div>
                <div class="image">
                    <img class="login-img" src="@/assets/login_images/login_page.jpg">
                </div>
            </div>
            <div class="right">
                <el-form :model="loginForm" :rules="loginRules" ref="loginForm" label-width="auto" class="login-form">
                    <el-form-item>
                        <div class="single-line">
                            <div class="login-text">登录</div>
                            <span>没有账号？<span class="blue underline">点此注册</span></span>
                        </div>
                    </el-form-item>
                    <el-form-item prop="userName">
                        <el-input type="text" v-model="loginForm.userName" placeholder="请输入账号"></el-input>
                    </el-form-item>
                    <el-form-item prop="passWord">
                        <el-input :type="eyeFlag ? 'password' : 'text'" v-model="loginForm.passWord" placeholder="请输入密码">
                            <i v-if="eyeFlag" slot="suffix" @click="eyeFlag = !eyeFlag" class="iconfont icon-eye"></i>
                            <i v-else slot="suffix" @click="eyeFlag = !eyeFlag" class="iconfont icon-eye-close"></i>
                        </el-input>
                    </el-form-item>
                    <el-form-item>
                        <div class="single-line">
                            <el-checkbox v-model="remember">记住我</el-checkbox>
                            <span class="underline">短信验证登录</span>
                        </div>
                    </el-form-item>
                    <el-form-item>
                        <el-button type="success" plain class="login-btn">登录</el-button>
                    </el-form-item>
                    <div class="forget-pwd underline">忘记密码？</div>
                </el-form>
            </div>
        </div>
    </div>
</template>

<script>
const defaultSettings = require('@/settings.js')
export default {
  name: 'Login',
  components: {
  },
  data() {
    const validateUserName = (rule, value, callback) => {
      if (!value) {
        callback(new Error('请输入账号'))
      } else {
        callback()
      }
    }
    const validatePassWord = (rule, value, callback) => {
      if (!value) {
        callback(new Error('请输入密码'))
      } else if (value.length < 6) {
        callback(new Error('密码不少于6位，请重新输入'))
      } else {
        callback()
      }
    }
    return {
        loginForm: {
            userName: '',
            passWord: ''
        },
        loginRules: {
            userName: [{ required: true, trigger: 'blur', validator: validateUserName }],
            passWord: [{ required: true, trigger: 'blur', validator: validatePassWord }]
        },
        eyeFlag: true,
        remember: false,
    }
  },
  computed: {
    systemTitle() {
      return defaultSettings.title
    }
  },
  methods: {
  }
}

</script>

<style lang="scss">
$bg:#e1ede1;
$system_title: #6a645c;
$input_height: 50px;
$input_width: 400px;
$blue_font: #409EFF;

.login-container {
    height: 100vh;
    display: flex;
    background-color: $bg;
    .left, .right {
        height: 100%;
    }
    .left {
        width: 45%;
        border-right: 2px solid #e2e2e2;
        display: flex;
        justify-content:center;
        flex-direction: column;
        align-items: center;
        .system-title {
            font-size: clamp(1.8rem, 3.2vw, 3.8rem);
            font-weight: 600;
            color: $system_title;
            align-items: center;
            margin-bottom: 8%;
        }
        .image {
            text-align:center;
            height: 60%;
            .login-img {
                width: 95%;
                height: 95%;
            }
        }
    }
    .right {
        flex: 1;
        display: flex;
        justify-content: center;
        align-items: center;
        .login-form {
            width: $input_width;
            .el-input__inner {
                height: $input_height;
            }
            .iconfont {
                font-size: 20px;
                margin-right: 5px;
                line-height: $input_height;
            }
            .iconfont:hover {
                cursor: pointer;
                color: #515151;
            }
            .single-line {
                line-height: $input_height;
                display: flex;
                justify-content: space-between;
                font-size: 15px;
                color: $system_title;
            }
            .login-text {
                font-size: clamp(1.8rem, 2.6vw, 2.8rem);
                font-weight: 600;
            }
            .forget-pwd {
                text-align: center;
                font-size: 15px;
                color: $system_title;
            }
            .login-btn {
                width: $input_width;
                height: $input_height;
                font-size: 20px;
                font-weight: 600;
            }
        }
    }
    .blue {
        color: $blue_font;
    }
    .underline:hover {
        color: $blue_font;
        cursor: pointer;
        text-decoration: underline;
    }
}
</style>