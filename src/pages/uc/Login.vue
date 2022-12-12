<template>
  <div class="login_form">
    <div class="login_right">
      <Form ref="formInline" :model="formInline" :rules="ruleInline" inline>
        <div class="login_title">{{$t('uc.login.login')}}</div>
        <FormItem prop="user">
          <Input name="user" type="text" v-model="formInline.user" :placeholder="$t('uc.login.usertip')" class="user">
          </Input>
        </FormItem>
        <FormItem prop="password" class="password">
          <Input type="password" v-model="formInline.password" :placeholder="$t('uc.login.pwdtip')" @on-keyup="onKeyup">
          </Input>
        </FormItem>
        <p id="notice" class="hide">{{$t('uc.login.validatemsg')}}</p>
        <p style="height:30px;">
          <router-link to="/findPwd" style="color:#979797;float:right;padding-right:10px;font-size:12px;">
            {{$t('uc.login.forget')}}
          </router-link>
        </p>
        <FormItem style="margin-bottom:15px;">
          <Button class="login_btn">{{$t('uc.login.login')}}</Button>
          
           <Button v-if="!isSignIn" @click="handleClickSignIn" class="logingoogle_btn" style="margin-top:10px;">
               <div style="display:flex;justify-content:center;align-items:center;">
                 <svg viewBox="0 0 24 24" width="24" height="24" xmlns="http://www.w3.org/2000/svg"  style="margin-right:5px;">
                 <g transform="matrix(1, 0, 0, 1, 27.009001, -39.238998)">
                  <path fill="#4285F4" d="M -3.264 51.509 C -3.264 50.719 -3.334 49.969 -3.454 49.239 L -14.754 49.239 L -14.754 53.749 L -8.284 53.749 C -8.574 55.229 -9.424 56.479 -10.684 57.329 L -10.684 60.329 L -6.824 60.329 C -4.564 58.239 -3.264 55.159 -3.264 51.509 Z"/>
                  <path fill="#34A853" d="M -14.754 63.239 C -11.514 63.239 -8.804 62.159 -6.824 60.329 L -10.684 57.329 C -11.764 58.049 -13.134 58.489 -14.754 58.489 C -17.884 58.489 -20.534 56.379 -21.484 53.529 L -25.464 53.529 L -25.464 56.619 C -23.494 60.539 -19.444 63.239 -14.754 63.239 Z"/>
                  <path fill="#FBBC05" d="M -21.484 53.529 C -21.734 52.809 -21.864 52.039 -21.864 51.239 C -21.864 50.439 -21.724 49.669 -21.484 48.949 L -21.484 45.859 L -25.464 45.859 C -26.284 47.479 -26.754 49.299 -26.754 51.239 C -26.754 53.179 -26.284 54.999 -25.464 56.619 L -21.484 53.529 Z"/>
                  <path fill="#EA4335" d="M -14.754 43.989 C -12.984 43.989 -11.404 44.599 -10.154 45.789 L -6.734 42.369 C -8.804 40.429 -11.514 39.239 -14.754 39.239 C -19.444 39.239 -23.494 41.939 -25.464 45.859 L -21.484 48.949 C -20.534 46.099 -17.884 43.989 -14.754 43.989 Z"/>
                </g>
              </svg>
         <span> Sign in with Google</span>
               </div>
               
              
         </Button> 
             <GoogleLogin :params="params" :renderParams="renderParams" :onSuccess="onSuccess" :onFailure="onFailure"></GoogleLogin>


        </FormItem>
        <div class='to_register'>
          <span>{{$t('uc.login.noaccount')}}</span>
          <router-link to="/register">{{$t('uc.login.goregister')}}</router-link>
        </div>
      </Form>

    </div>
  </div>
</template>
<style scoped lang="scss">
/* 验证码 */
.login_form {
  background: #0b1520 url(../../assets/images/login_bg.png) no-repeat center center;
  height: 760px;
  position: relative;
  overflow: hidden;
  .login_right {
    padding: 20px 30px 20px 30px;
    position: absolute;
    background: #17212e;
    width: 350px;
    height: 380px;
    left: 50%;
    top: 50%;
    margin-left: -175px;
    margin-top: -165px;
    border-top: 4px solid #ffec03;
    border-radius: 5px;
    form.ivu-form.ivu-form-label-right.ivu-form-inline {
      .login_title{
        height: 70px;
        color: #fff;
      }
      .ivu-form-item {
        .ivu-form-item-content {
          .login_btn.ivu-btn {
            width: 100%;
            background-color: #ffec03;
            outline: none;
            border-color: #ffec03;
            color: #5c5b59;
            font-size: 18px;
            border-radius: 5px;
            &:focus {
              -moz-box-shadow: 0px 0px 0px #fff, 0px 0px 0px #fff;
              -webkit-box-shadow: 0px 0px 0px #fff, 0px 0px 0px #fff;
              box-shadow: 0px 0px 0px #fff, 0px 0px 0px #fff;
            }
          }
           .logingoogle_btn.ivu-btn {
            width: 100%;
            
            background-color: #fafafa;
            outline: none;
            border-color: #fdfdfd;
            color: #5c5b59;
            font-size: 18px;
            border-radius: 5px;
            &:focus {
              -moz-box-shadow: 0px 0px 0px #fff, 0px 0px 0px #fff;
              -webkit-box-shadow: 0px 0px 0px #fff, 0px 0px 0px #fff;
              box-shadow: 0px 0px 0px #fff, 0px 0px 0px #fff;
            }
          }
        }
      }
    }
  }
  .to_register {
    overflow: hidden;
    font-size: 12px;
    span {
      float: left;
    }
    a {
      float: right;
      color: #ffec03;
    }
  }
}
#captcha {
  width: 100%;
  display: inline-block;
}
.show {
  display: block;
}
.hide {
  display: none;
}
#notice {
  color: red;
}
#wait {
  text-align: left;
  color: #666;
  margin: 0;
}
.geetest_wait_dot geetest_dot_1 {
  color: red;
}
.user .ivu-btn,
.ivu-btn:active,
.ivu-btn:focus {
  border-color: #d7dde4;
  box-shadow: none;
}
/*  */
</style>
<script>
import gtInit from "../../assets/js/gt.js";
import GoogleLogin from 'vue-google-login';

import $ from "jquery";
export default {
   components: {
            GoogleLogin
        },
  data() {
    return {
      isInit: false,
      isSignIn: false,
      country: "+86",
      captchaObj: null,
      _captchaResult: null,
      formInline: {
        user: "",
        password: ""
      },
      ruleInline: {
        user: [
          {
            required: true,
            message: this.$t("uc.login.loginvalidate"),
            trigger: "blur"
          }
        ],
        password: [
          {
            required: true,
            message: this.$t("uc.login.pwdvalidate1"),
            trigger: "blur"
          },
          {
            type: "string",
            min: 6,
            message: this.$t("uc.login.pwdvalidate2"),
            trigger: "blur"
          }
        ]
      },
       // client_id is the only required property but you can add several more params, full list down bellow on the Auth api section
                params: {
                    client_id: "368561368788-boggv1vi6bmtbnrmcneik17sf9ita876.apps.googleusercontent.com"
                },
                // only needed if you want to render the button with the google ui
                renderParams: {
                    width: 250,
                    height: 50,
                    longtitle: true
                }
    };
  },
  created: function() {
    this.init();
   
  },
  computed: {
    isLogin: function() {
      return this.$store.getters.isLogin;
    }
  },
  methods: {
    async handleClickSignIn(){
     const googleUser=await this.$gAuth.signIn();
     console.log("userFromGoogle:",googleUser);
    },
   
    init() {
      this.$store.commit("navigate", "nav-other");
      this.$store.state.HeaderActiveName = "0";

      if (this.isLogin) {
        this.$router.push("/uc/safe");
      } else {
        this.initGtCaptcha();
      }
    },
    onKeyup(ev) {
      if (ev.keyCode == 13) {
        $(".login_btn").click();
      }
    },
    initGtCaptcha() {
      var that = this;
      this.$http.get(this.host + this.api.uc.captcha).then(function(res) {
        window.initGeetest(
          {
            // 以下配置参数来自服务端 SDK
            gt: res.body.gt,
            challenge: res.body.challenge,
            offline: !res.body.success, //表示用户后台检测极验服务器是否宕机
            new_captcha: res.body.new_captcha, //用于宕机时表示是新验证码的宕机
            product: "bind",
            width: "100%"
          },
          this.handler
        );
      });
    },
    handler(captchaObj) {
      captchaObj.onReady(() => {
          $("#wait").hide();
        }).onSuccess(() => {
          let result = (this._captchaResult = captchaObj.getValidate());
          if (!result) {
            this.$Message.error("请完成验证");
          } else {
            this.handleSubmit("formInline");
          }
        });
      $(".login_btn").click(() => {
        // let reg = /^[1][3,4,5,6,7,8,9][0-9]{9}$/,
          // tel = this.formInline.user,
         let flagtel = this.formInline.user.length>=4 ? true : false,
          flagpass = this.formInline.password.length >= 6 ? true : false;
        flagtel && flagpass; // && captchaObj.verify();
        (!flagtel || !flagpass) && this.$Message.error(this.$t("common.fillComplete"));
        this.handleSubmit("formInline"); // 屏蔽了验证
      });
    },
    logout() {
      this.$http.post(this.host + "/uc/logout", {}).then(response => {
        var resp = response.body;
        if (resp.code == 0) {
          localStorage.setItem("MEMBER", JSON.stringify(null));
          localStorage.setItem("TOKEN", null);
          localStorage.removeItem("USERKEY", null);
        } else {
          // this.$Message.error(resp.message);
        }
      });
    },
    handleSubmit(name) {
      // 不带验证
      this.$refs[name].validate(valid => {
        if (valid) {
          var params = {};
          params["username"] = this.formInline.user;
          params["password"] = this.formInline.password;
          this.$http.post(this.host + this.api.uc.login, params).then(response => {
              var resp = response.body;
              if (resp.code == 0) {
                this.$Message.success(this.$t("uc.login.success"));
                this.$store.commit("setMember", response.body.data);
                if (this.$route.query.key != null && this.$route.query.key != "") {
                  localStorage.setItem("USERKEY", this.$route.query.key);
                }
                 this.$router.push("/");
              } else {
                this.$Message.error(resp.message);
              }
            });
        } else {

        }
      });
      /* 带验证*/
      var result = this._captchaResult;
      if (!result) {
        $("#notice").show();
        setTimeout(function() {
          $("#notice").hide();
        }, 2000);
      } else {
        this.$refs[name].validate(valid => {
          if (valid) {
            var params = {};
            params["username"] = this.formInline.user;
            params["password"] = this.formInline.password;
            this.$http.post(this.host + this.api.uc.login, params).then(response => {
                var resp = response.body;
                if (resp.code == 0) {
                  this.$Message.success(this.$t("uc.login.success"));
                  this.$store.commit("setMember", response.body.data);
                  if (this.$route.query.key != null && this.$route.query.key != "") {
                    localStorage.setItem("USERKEY", this.$route.query.key);
                  }
                  this.$router.push("/uc/safe");
                } else {
                  this.$Message.error(resp.message);
                }
              });
          } else {

          }
        });
      }
      
    }
  }
};
</script>
<style lang="scss">
.login_form {
  .login_right {
    form.ivu-form.ivu-form-label-right.ivu-form-inline {
      .ivu-form-item {
        .ivu-form-item-content {
          .ivu-input-wrapper.ivu-input-type {
            .ivu-input {
              background-color:transparent;
              font-size: 14px;
              border: none;
              border-bottom: 1px solid #27313e;
              border-radius:0;
              // color:#fff;
              &:focus {
                border: none;
                border-bottom: 1px solid #27313e;
                -moz-box-shadow: 2px 2px 5px transparent, -2px -2px 4px transparent;
                -webkit-box-shadow: 2px 2px 5px transparent, -2px -2px 4px transparent;
                box-shadow: 2px 2px 5px transparent, -2px -2px 4px transparent;
              }
            }
          }
        }
      }
    }
  }
}

.ivu-select-single .ivu-select-selection .ivu-select-placeholder, .ivu-select-single .ivu-select-selection .ivu-select-selected-value{
  padding-right: 10px;
  padding-left: 3px;
}
.ivu-select-single .ivu-select-selection .ivu-select-arrow{
  right: 2px;
}

.ivu-form-item-error .ivu-input-group-append, .ivu-form-item-error .ivu-input-group-prepend{
  background-color: #17212e;
  border-color: transparent;
}
.ivu-form-item-error .ivu-select-arrow{
  color: #808695;
}

.login_right .ivu-select-dropdown{
  background: #1c2a32;
}
</style>
<style>
  .ivu-select-single .ivu-select-selection .ivu-select-placeholder, .ivu-select-single .ivu-select-selection .ivu-select-selected-value{
    padding-right: 20px;
  }
  .ivu-select-arrow{
    right: 4px;
  }

  .ivu-select-item span:first-child{
    display: inline-block;
    width: 30px;
    text-align: left;
  }
</style>
