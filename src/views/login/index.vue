<template>
  <div class="login">
    <div class="leftbox">
      <div class="title">
        <img class="titleimg" src="../../assets/title-logo.png" alt="">
        <span class="titlename">黑马面面</span>
        <span class="titleline"></span>
        <span class="titlelogin">用户登录</span>
      </div>
      <el-form :rules="rules" class="myform" ref="form" :model="form">
        <el-form-item prop="phone">
          <el-input placeholder="请输入手机号" v-model="form.phone"></el-input>
        </el-form-item>
        <el-form-item>
          <el-input placeholder="请输入密码" v-model="form.password"></el-input>
        </el-form-item>
        <el-form-item>
          <el-row>
            <el-col :span="16">
              <div class="grid-content bg-purple-dark">
                <el-input v-model="form.loginCode"></el-input>
              </div>
            </el-col>
            <el-col :span="8">
              <div class="grid-content bg-purple-dark">
                <img class="myimg" src="../../assets/login_captcha.png" alt="">
              </div>
            </el-col>
          </el-row>
        </el-form-item>
        <el-form-item class="myitem">
          <el-checkbox-group v-model="form.isCheck">
            <el-checkbox name="type">
              我已阅读并同意
              <a href="#">用户协议</a>和
              <a href="#">隐私条款</a>
            </el-checkbox>
          </el-checkbox-group>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" class="mybtn" @click="onSubmit">登录</el-button>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" class="mybtn" @click="register">注册</el-button>
        </el-form-item>
      </el-form>
    </div>
    <img class="rightimg" src="../../assets/login_banner_ele.png" alt="">
    <register ref="myreg" />
  </div>
</template>

<script>
import register from './coms/register.vue'
export default {
  data() {
    return {
      form: {
        phone: '',
        password: '',
        loginCode: '',
        isCheck: ''
      },
      rules: {
        phone: [
          { required: true, message: '请输入手机号', trigger: 'blur' },
          { min: 11, max: 11, message: '长度是11个字符', trigger: 'blur' }
        ],
      }
    }
  },
  methods: {
    onSubmit() {
      this.$refs['form'].validate((valid) => {
        if (valid) {
          alert('submit!');
        } else {
          console.log('error submit!!');
          return false;
        }
      });
    },
    register () {
      this.$refs.myreg.dialogFormVisible = true
    }
  },
  components: {
    register
  }
}
</script>

<style lang="less">
.login {
  height: 100%;
  background: linear-gradient(225deg, rgba(20, 147, 250, 1), rgba(1, 198, 250, 1));
  /* 使用 flex 布局 */
  display: flex;
  /* 让两者左右间隔相等 */
  justify-content: space-around;
  /* 设置上下居中 */
  align-items: center;
  .leftbox {
    width: 478px;
    height: 550px;
    background: rgba(245, 245, 245, 1);
    padding: 48px 42px 86px;
    /* padding 不会计入盒子的宽高中 */
    box-sizing: border-box;
    .title {
      display: flex;
      /* 上下对齐 */
      align-items: center;
      .titleimg {
        width: 22px;
        height: 17px;
      }
      .titlename {
        font-size: 24px;
        font-family: SourceHanSansCN;
        font-weight: 400;
        color: rgba(12, 12, 12, 1);
        margin-left: 16px;
        margin-right: 14px;
      }
      .titleline {
        width: 1px;
        height: 28px;
        background: rgba(199, 199, 199, 1);
        margin-right: 12px;
      }
      .titlelogin {
        font-size: 22px;
        font-family: PingFangSC;
        font-weight: 400;
        color: rgba(12, 12, 12, 1);
      }
    }
    .myform {
      margin-top: 29px;
      .el-checkbox-group {
        line-height: 20px;
      }
      .myimg {
        width: 100%;
        height: 40px;
      }
      .mybtn {
        width: 100%;
      }
    }
  }
  .rightimg {
    width: 633px;
    height: 435px;
  }
}
</style>
