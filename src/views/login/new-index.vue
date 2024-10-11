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

            </div>
        </div>
    </div>
</template>

<script>
const defaultSettings = require('@/settings.js')
export default {
  components: {
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
    }
}
</style>