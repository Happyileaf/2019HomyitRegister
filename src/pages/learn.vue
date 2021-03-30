<template>
  <div id="registerPage">
    <div class="header">
      <!-- <h1>{{ msg }}</h1> -->
      <!-- <img src alt /> -->
      <div class="pc-bg">
        <div class="banner">
          <img id="bannerLogo" src="../../static/images/pc/logo.png" alt />
          <p>
            <img id="bannerTitle" src="../../static/images/pc/title.png" alt />
          </p>

          <!-- <h2>Hello,this is Homyit Studio.</h2> -->
        </div>
      </div>
      <div class="mobile-bg"></div>
    </div>
    <div class="message">
      <div class="container">
        <el-row :gutter="30">
          <el-col :span="8">
            <div class="UIBox grid-content contentBox">
              <div class="groups">User Interface</div>
              <p>
                UI设计（或称界面设计）是指对软件的人机交互、操作逻辑、界面美观的整体设计。UI设计实体UI和虚拟UI。
                互联网说的UI设计是虚拟UI，UI即User Interface（用户界面）的简称。
              </p>
            </div>
          </el-col>
          <el-col :span="8">
            <div class="frontBox grid-content contentBox">
              <div class="groups">Front End</div>
              <p>
                前端即网站前台部分，运行在PC端，移动端等浏览器上展现给用户浏览的网页。
                前端技术一般分为前端设计和前端开发，前端设计一般可以理解为网站的视觉设计，
                前端开发则是网站的前台代码实现。
              </p>
            </div>
          </el-col>
          <el-col :span="8">
            <div class="backBox grid-content contentBox">
              <div class="groups">Back End</div>
              <p>后端是指网站的数据内容管理部分，通过后端数据管理决定前端用户浏览的内容，后端注重逻辑思维。</p>
            </div>
          </el-col>
        </el-row>
      </div>
      <hr />
    </div>
    <div class="content">
      <div class="formWrap">
        <form action @submit.prevent="onSubmit()">
          <el-row :gutter="75">
            <el-col :span="24" :lg="12">
              <div class="inputWrap">
                <div class="iconWrap">
                  <i class="el-icon-user"></i>
                </div>
                <input
                  placeholder="姓名"
                  autocomplete="off"
                  class="form-control"
                  id="userName"
                  v-model="form.userName"
                  @blur="userNameCheck()"
                />
                <div class="checkIconWrap" ref="userNameInputCorrect">
                  <i class="el-icon-circle-check correct"></i>
                </div>
                <div class="checkIconWrap" ref="userNameInputIncorrect">
                  <i class="el-icon-circle-close incorrect"></i>
                </div>
              </div>
            </el-col>
            <el-col :span="24" :lg="12">
              <div class="inputWrap">
                <div class="iconWrap">
                  <i class="el-icon-bank-card"></i>
                </div>
                <input
                  placeholder="学号"
                  autocomplete="off"
                  class="form-control"
                  id="schoolId"
                  v-model="form.schoolId"
                  @blur="schoolIdCheck()"
                />
                <div class="checkIconWrap" ref="schoolIdInputCorrect">
                  <i class="el-icon-circle-check correct"></i>
                </div>
                <div class="checkIconWrap" ref="schoolIdInputIncorrect">
                  <i class="el-icon-circle-close incorrect"></i>
                </div>
              </div>
            </el-col>
            <el-col :span="24">
              <div class="inputWrap">
                <div class="iconWrap">
                  <i class="el-icon-school"></i>
                </div>
                <input
                  placeholder="班级"
                  autocomplete="off"
                  class="form-control"
                  id="class"
                  v-model="form.class"
                  @blur="classCheck()"
                />
                <div class="checkIconWrap" ref="classInputCorrect">
                  <i class="el-icon-circle-check correct"></i>
                </div>
                <div class="checkIconWrap" ref="classInputIncorrect">
                  <i class="el-icon-circle-close incorrect"></i>
                </div>
              </div>
            </el-col>
            <el-col :span="24">
              <div class="inputWrap">
                <div class="iconWrap">
                  <i class="el-icon-eleme"></i>
                </div>
                <input
                  placeholder="Email"
                  autocomplete="off"
                  class="form-control"
                  id="email"
                  v-model="form.email"
                  @blur="emailCheck()"
                />
                <div class="checkIconWrap" ref="emailInputCorrect">
                  <i class="el-icon-circle-check correct"></i>
                </div>
                <div class="checkIconWrap" ref="emailInputIncorrect">
                  <i class="el-icon-circle-close incorrect"></i>
                </div>
              </div>
            </el-col>
            <el-col :span="24">
              <div class="inputWrap" ref="telInput">
                <div class="iconWrap">
                  <i class="el-icon-phone"></i>
                </div>
                <input
                  placeholder="TEL"
                  autocomplete="off"
                  class="form-control"
                  id="tel"
                  v-model="form.tel"
                  @blur="telCheck()"
                />
                <div class="checkIconWrap" ref="telInputCorrect">
                  <i class="el-icon-circle-check correct"></i>
                </div>
                <div class="checkIconWrap" ref="telInputIncorrect">
                  <i class="el-icon-circle-close incorrect"></i>
                </div>
              </div>
            </el-col>
            <el-col :span="24">
              <div class="inputWrap" id="editWrap" ref="messageInput">
                <div class="iconWrap" id="el-icon-editWrap">
                  <i class="el-icon-edit"></i>
                </div>
                <textarea
                  placeholder="有什么想和我们说的嘛？"
                  cols="30"
                  rows="10"
                  class="form-control"
                  id="message"
                  v-model="form.message"
                  @blur="messageCheck()"
                ></textarea>
              </div>
            </el-col>
            <el-col :span="24">
              <button class="btn" type="submit">Send Message</button>
            </el-col>
          </el-row>
        </form>
        <!-- <div class="blankBox"></div> -->
      </div>
      <img
        class="display-none"
        id="welcomeImg"
        src="../../static/images/pc/Welcome everyone.png"
        alt
      />
      <img class="display-none" id="ofyouImg" src="../../static/images/pc/of  you..png" alt />
    </div>

    <!-- <div class="footer">
      <div class="groups">
        <div class="container">
          <el-row :gutter="20">
            <el-col :span="6">
              <div class="grid-content contentBox">
                <div class="footer-title">
                  <h4>Homyit Studio</h4>
                </div>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Mauris velit arcu, scelerisque dignissim massa quis, mattis facilisis erat. Aliquam erat volutpat. Sed efficitur diam ut interdum ultricies.</p>
              </div>
            </el-col>
            <el-col :span="6">
              <div class="grid-content contentBox">
                <div class="footer-title">
                  <h4>User Interface</h4>
                </div>
                <ul>
                  <a href>Photoshop</a>
                  <a href>Premiere</a>
                  <a href>Adobe Illustrator</a>
                  <a href>After Effects</a>
                  <a href>3DMax</a>
                </ul>
              </div>
            </el-col>
            <el-col :span="6">
              <div class="grid-content contentBox">
                <div class="footer-title">
                  <h4>Front end</h4>
                </div>
                <ul>
                  <a href>React</a>
                  <a href>Angular</a>
                  <a href>Vue</a>
                  <a href>Typescript</a>
                  <a href>Node</a>
                </ul>
              </div>
            </el-col>
            <el-col :span="6">
              <div class="grid-content contentBox">
                <div class="footer-title">
                  <h4>Back end</h4>
                </div>
                <ul>
                  <a href>Spring+Mybatis</a>
                  <a href>Springboot</a>
                  <a href>Springmvc</a>
                  <a href>Docker</a>
                  <a href>Nosql</a>
                </ul>
              </div>
            </el-col>
          </el-row>
        </div>
      </div>
      <div class="copyRight">
        <div class="container">
          <el-row :gutter="20">
            <el-col :span="24" :lg="12" class="CR-Msg">
              <h5>
                Copyright © 2019.JXNU Homyit Studio All Rights Reserved.
                <br />有爱同行 踏实求新
              </h5>
            </el-col>
            <el-col :span="0" :lg="12" class="CR-Msg"></el-col>
          </el-row>
        </div>
      </div>
    </div>-->
  </div>
</template>

<script>
import axios from "axios";
import qs from "qs";
import { Decrypt, Encrypt } from "@/utils/Aes.js";

// import { Decrypt, Encrypt } from "@/assets/js/aes.js";
export default {
  // 定义页面名称，可以不要 ",
  name: "Register",
  data() {
    return {
      // 定义变量
      msg: "HOMYIT STUDIO",
      form: {
        userName: "",
        schoolId: "",
        class: "",
        email: "",
        tel: "",
        message: ""
      },
      shouldSend: [0, 0, 0, 0, 0],
      password:"",
    };
  },
  methods: {
    sendMessage() {
      axios({
        url: "http://39.106.65.18/homyitEnter/UseraddServlet",
        method: "post",
        data: {
          userName: Encrypt(this.form.userName),
          schoolId: Encrypt(this.form.schoolId),
          class: this.form.class,
          email: this.form.email,
          tel: this.form.tel,
          message: this.form.message,
          
        },
        transformRequest: [
          function(data) {
            console.log("aaa");
            console.log(data.userName);
            data.userName = Decrypt(data.userName);
            console.log(data.userName);
            console.log("bbb");
            data = qs.stringify(data);
            return data;
          }
        ],
        headers: {
          "Content-Type": "application/x-www-form-urlencoded;charset=utf-8"
        },
        dataType: "json"
      })
        .then(res => {
          console.log(res);
        })
        .catch(function(error) {
          console.log(error);
        });
    },

    onSubmit() {
      if (
        1
        // this.shouldSend[0] &&
        // this.shouldSend[1] &&
        // this.shouldSend[2] &&
        // this.shouldSend[3] &&
        // this.shouldSend[4] == 1
      ) {
        this.sendMessage();
        this.open1();

        // 表当提交成功 3s 后刷新当前页面

        // setTimeout(function() {
        //   window.location.reload();
        // }, 3000);

        let a = "Hello World!";
        console.log(a);
        // Encrypt 加密
        a = Encrypt(a);
        console.log(a);
        // Decrypt 解密
        a = Decrypt(a);
        console.log(a);
      }
      return false;
    },

    open1() {
      this.$notify({
        title: "发送成功",
        message: "宏奕工作室期待你的加入！",
        type: "success"
      });
    },
    userNameCheck() {
      var userName = this.form.userName;
      var userNameReg = /^([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2,4})$/;
      if (userName.replace(/(^\s*)|(\s*$)/g, "").length != 0) {
        this.$refs.userNameInputCorrect.style.display = "flex";
        this.$refs.userNameInputIncorrect.style.display = "none";
        this.shouldSend[0] = 1;
      } else {
        this.$refs.userNameInputCorrect.style.display = "none";
        this.$refs.userNameInputIncorrect.style.display = "flex";
        this.shouldSend[0] = 0;
      }
    },
    schoolIdCheck() {
      var schoolId = this.form.schoolId;
      var schoolIdReg = /^2019\d{8}$/;
      if (schoolIdReg.test(schoolId)) {
        this.$refs.schoolIdInputCorrect.style.display = "flex";
        this.$refs.schoolIdInputIncorrect.style.display = "none";
        this.shouldSend[1] = 1;
      } else {
        this.$refs.schoolIdInputCorrect.style.display = "none";
        this.$refs.schoolIdInputIncorrect.style.display = "flex";
        this.shouldSend[1] = 0;
      }
    },

    classCheck() {
      var Class = this.form.class;
      var ClassReg = /^([A-Za-z0-9_\-\.])+\@([A-Za-z0-9_\-\.])+\.([A-Za-z]{2,4})$/;
      if (Class.replace(/(^\s*)|(\s*$)/g, "").length != 0) {
        this.$refs.classInputCorrect.style.display = "flex";
        this.$refs.classInputIncorrect.style.display = "none";
        this.shouldSend[2] = 1;
      } else {
        this.$refs.classInputCorrect.style.display = "none";
        this.$refs.classInputIncorrect.style.display = "flex";
        this.shouldSend[2] = 0;
      }
    },
    emailCheck() {
      var email = this.form.email;
      var emailReg = /^\w+([-+.]\w+)*@\w+([-.]\w+)*\.\w+([-.]\w+)*$/;
      if (emailReg.test(email)) {
        this.$refs.emailInputCorrect.style.display = "flex";
        this.$refs.emailInputIncorrect.style.display = "none";
        this.shouldSend[3] = 1;
      } else {
        this.$refs.emailInputCorrect.style.display = "none";
        this.$refs.emailInputIncorrect.style.display = "flex";
        this.shouldSend[3] = 0;
      }
    },
    telCheck() {
      var tel = this.form.tel;
      var telReg = /^(13[0-9]|14[0-9]|15[0-9]|16[0-9]|17[0-9]|18[0-9]|19[0-9])\d{8}$/;
      if (telReg.test(tel)) {
        this.$refs.telInputCorrect.style.display = "flex";
        this.$refs.telInputIncorrect.style.display = "none";
        this.shouldSend[4] = 1;
      } else {
        this.$refs.telInputCorrect.style.display = "none";
        this.$refs.telInputIncorrect.style.display = "flex";
        this.shouldSend[4] = 0;
      }
    },
    messageCheck() {
      // this.$refs.userNameInputCorrect.style.display = "block";
    }
  }
};
</script>

<style scoped>
#registerPage {
  /* width: 65%; */
  margin: auto;
  font-size: 3vw;
}

.header {
  /* height: 20vh; */
  padding: 1vh 0;
  display: flex;
  justify-content: center;
  align-items: center;

  margin: 0 0 0 0;

  width: 100%;
  height: 70vh;
  background-image: url(../../static/images/pc/banner.png);
  background-size: cover;
}

.header .pc-bg img#bannerLogo {
  width: 10vw;
}

.header .pc-bg img#bannerTitle {
  width: 70vw;
}

.header .pc-bg p {
  margin: 0;
}
.header .pc-bg h2 {
  /* position: absolute; */
  /* width: 100%; */
  /* top: 0; */
  margin: 5vh 0;
  color: #ffffff;
  opacity: 1;
  font-size: 1.7em;
  font-weight: 700;
  font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
    "Lucida Sans", Arial, sans-serif;
}

.header .mobile-bg {
  display: none;
}

.message {
  width: 75%;
  margin: 13vh auto 1vh auto;
  padding: 1vh 0;
}

.message .contentBox {
  min-height: 30vh;
  text-align: left;
  box-sizing: border-box;
  overflow: hidden;
  /* margin: 0 0 10vh 0; */
}

.message .container {
  width: 100%;
  margin: auto 7vh 7vh 7vh;
}

.message .groups {
  font-size: 0.6em;
  border-left: 5px solid rgb(235, 200, 235);
  padding: 0 0 0 1vw;
}
.message p {
  width: 70%;
  font-size: 0.3em;
  padding: 0 0 0 1vw;
  line-height: 25px;
}

.formWrap {
  width: 55%;
  margin: auto;
  padding: 1vh 0;
}

.content {
  position: relative;
}

#welcomeImg {
  width: 4vw;
  position: absolute;
  top: 9vh;
  right: 5vw;
}

#ofyouImg {
  width: 4vw;
  position: absolute;
  top: 45vh;
  right: 12vw;
}

h1 {
  font-size: 35px;
  font-weight: normal;
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
  /* margin: auto auto; */
}

form {
  width: 100%;
  margin: 2vh 0;
}

.blankBox {
  width: 100%;
  height: 55vh;
  margin: 2vh 0;
}

.el-col {
  border-radius: 0px;
}
.bg-purple-dark {
  background: #99a9bf;
}
.bg-purple {
  background: #d3dce6;
}
.bg-purple-light {
  background: #e5e9f2;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
.inputWrap {
  background-color: #eff4f9;
  width: 100%;
  /* height: 100%; */
  /* padding: 15px 30px; */
  margin-bottom: 15px;
  display: flex;
  align-items: center;
  border: none;
}

.iconWrap {
  /* height: 45px; */
  width: 3vw;
  /* min-width: 50px; */
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 2vw 0 0;
}
.checkIconWrap {
  height: 35px;
  /* width: 3vw; */
  box-sizing: border-box;
  display: none;
  /* vertical-align: middle; */
  margin: 0 1vw 0 0;
  /* padding: 15px 0; */
  align-items: center;
  border: none;
}

#el-icon-editWrap {
  /* height: 45px; */
  width: 3vw;
  /* min-width: 50px; */
  height: 100%;
  display: flex;
  align-items: unset;
}

#editWrap {
  align-items: unset;
}

.correct {
  color: rgb(10, 163, 112);
  font-size: 25px;
  transition: 0.5s;
}

.incorrect {
  color: rgb(255, 0, 0);
  font-size: 25px;
  transition: 0.5s;
}

.form-control {
  box-sizing: border-box;

  position: relative;
  z-index: 2;
  height: 35px;
  width: 100%;
  background-color: #eff4f9;
  font-size: 12px;
  /* margin-bottom: 30px; */
  border-radius: 0;
  padding: 15px 30px 15px 0px;
  font-weight: 500;
  font-style: italic;
  color: #7c7c7c;
  -webkit-transition-duration: 500ms;
  transition-duration: 500ms;
  border: none;
  /* border-width: 1px;
  border-color: #20d8da;
  border-style: solid; */
  /* border: 1px #20d8da solid; */
}

.form-control:focus {
  box-shadow: none;
  outline: none;
}
textarea.form-control {
  height: 190px;
  font-family: Arial, Helvetica, sans-serif;
  resize: vertical;
}

.btn {
  width: 100%;
  background-color: rgb(122, 73, 122);
  -webkit-transition-duration: 500ms;
  transition-duration: 500ms;
  position: relative;
  z-index: 1;
  display: inline-block;
  min-width: 160px;
  height: 50px;
  color: #ffffff;
  border-radius: 0;
  padding: 0 30px;
  font-size: 14px;
  line-height: 50px;
  font-weight: 500;
  text-transform: capitalize;
  border: 0;
}

.btn:hover {
  font-size: 14px;
  font-weight: 500;
  background-color: #000000;
  color: #ffffff;
}

@media screen and (max-width: 1000px) {
  #registerPage {
    width: 100%;
    min-height: 100vh;
    margin: auto;
    background-image: url(../../static/images/mobile/背景.jpg);
    background-size: cover;
    /* padding: 30vh 0 0 0; */
  }

  .header {
    background-image: none;
    height: auto;
    padding: 0;
  }
  .message {
    display: none;
  }

  .header .mobile-bg {
    display: block;
    width: 100%;
    height: 25vh;
    background-image: url(../../static/images/mobile/mobile-bg.png);
    background-size: contain;
    background-repeat: no-repeat;
    /* z-index: 1000; */
  }

  .pc-bg {
    display: none;
  }
  .flexBox {
    display: flex;
  }

  .display-none {
    display: none;
  }
  .blankBox {
    height: 15vh;
  }
  .message,
  .formWrap {
    width: 75%;
  }

  .message {
    margin: 1vh auto;
  }

  .formWrap .form-title h1 {
    margin: 0 0 5vh 0;
    text-align: left;
    font-weight: 500;
    font-size: 25px;
  }

  .form-control {
    height: 35px;
    width: 100%;

    font-size: 12px;
    /* margin-bottom: 20px; */
    font-style: italic;
    padding: 15px 20px 15px 0px;
    font-weight: 500;
  }

  .btn {
    background-color: rgb(0, 127, 231);
  }

  #el-icon-editWrap {
    /* height: 45px; */
    padding: 16px 0px 0px 0px;

    /* min-width: 50px; */
  }

  textarea.form-control {
    height: 130px;
  }

  .message .contentBox {
    min-height: 15vh;
    margin: 0 0;
  }

  .message .about-usBtn {
    min-width: 75px;
  }
}
</style>