<template>
    <div>
        <topline></topline>
        <navibar></navibar>
        <div class="findpassword_main">
            <div class="findpassword_main_div">
                <div class="findpassword_main_div_top">
                    <div class="breadcrumb">
                        <!-- <a href="">首页 > </a>找回密码 -->
                        <el-breadcrumb separator-class="el-icon-arrow-right">
                            <el-breadcrumb-item :to="{ path: '/' }">首页</el-breadcrumb-item>
                            <el-breadcrumb-item>找回密码</el-breadcrumb-item>
                        </el-breadcrumb>
                    </div>
                </div>
                <div class="step1" v-if="curStep == 1">
                    <div class="findpassword_main_div_img1"></div>
                    <div class="findpassword_main_div_email">
                        <div class="findpassword_main_div_email_left">电子邮箱</div>
                        <el-input class="findpassword_main_div_email_right" v-model="email" placeholder="请输入内容"></el-input>
                        <!-- <div class="findpassword_main_div_email_right">
                            
                        </div> -->
                        <div class="findpassword_error"></div>

                    </div>
                    <div class="findpassword_main_div_code">
                        <div class="findpassword_main_div_code_left">验证码</div>
                        <div class="findpassword_main_div_code_right">
                            <input type="text">
                        </div> 
                        <img src="">
                        <a href="javascript:void(0);">换一张</a>
                        <div class="findpassword_error findpassword_error_3">不许有空格不许有空格不许有空格不许有空格不许有空格不许有空格不许有空格</div>
                    </div>
                    <a class="findpassword_main_div_btn" @click="toStep2">下一步</a>
                </div>
                <div class="step2"  v-if="curStep == 2">
                    <div class="findpasswordtwo_main_div_img2"></div>
                    <div class="findpasswordtwo_main_ts">为了您的账号安全，请完成身份认证</div>
                    <div class="findpassword_main_div_email findpasswordtwo_email">
                        <div class="findpassword_main_div_email_left">电子邮箱</div>
                        <div class="findpasswordtwo_email_right">masjd@yodn.com</div>
                    </div>
                    <div class="findpassword_main_div_code findpasswordtwo_code">
                        <div class="findpassword_main_div_code_left">验证码</div>
                        <div class="findpassword_main_div_email_right">
                            <input type="text">
                        </div>
                    </div>
                    <a class="findpassword_main_div_btn" @click="toStep3">下一步</a>
                </div>
                <div class="step3"  v-if="curStep == 3">
                    <div class="findpasswordtwo_main_div_img3"></div>
                    <div class="findpasswordthree_desc"></div>
                    <a class="findpassword_main_div_btn findpasswordsuccess_btn">登录</a>
                </div>
            </div>
        </div>
        <foot></foot>
    </div> 
</template>

<script>
import Topline from '@/components/Topline'
import Navibar from '@/components/Navibar'
import Foot from '@/components/Foot'

export default {
    name:'FindPwd',
    props:{
        
    },
    data(){
        return{
            curStep:1,
            email:''
        }
    },
    components:{
      Topline:Topline,
      Navibar:Navibar,
      Foot:Foot
    },
    created(){
        
    },
    mounted () {
       
    },
    watch:{
        
    },
    methods:{
        toStep2(){
            this.curStep = 2
        },
        toStep3(){
            this.curStep = 3
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style  rel='stylesheet/scss' scoped>
.findpassword_main{width:100%;background:#1b1720;overflow:hidden}
.findpassword_main_div{background:#191f27;width:1200px;overflow:hidden;margin-top:40px;padding:0px 50px 50px 0px;}
.findpassword_main_div_top{width:100%;height:50px;line-height:50px;border-bottom:1px solid #202234;text-align:left;font-size:14px;color:#adaeb6;padding-top:14px;}
.findpassword_main_div_top a{color:#3a4556;}
.findpassword_main_div_img1,
.findpasswordtwo_main_div_img,
.findpasswordsuccess_img{margin-left:140px;background:url('~@/assets/img/findpassword1.png') no-repeat center;width:770px;margin-top:76px;height:100px;}

.findpassword_main_div_email,.findpassword_main_div_code{width:1000px;line-height:50px;height:50px;margin-top:70px}
.findpassword_main_div_email_left,.findpassword_main_div_code_left{width:95px;float:left;text-align:left;color:#a2b2c8;line-height:50px;height:50px;}
.findpassword_main_div_email_right,.findpassword_main_div_code_right{height:50px;width:510px;border:1px solid #384658;box-sizing:border-box;float:left;color:white;background-color:#191f27;}
.findpassword_main_div_email_right input,.findpassword_main_div_code_right input{width:100%;height:50px;line-height:50px;border:none;background:none;text-align:left;color:#c2c3ca;font-size:20px}
.findpassword_main_div_code_right{width:300px !important;}
.findpasswordsuccess_main_div_code_right{width:510px;}
.findpassword_main_div_code img{float:left;margin-left:10px;height:50px;width:125px;}
.findpassword_main_div_code a{float:left;height:50px;width: 60px;float:left;margin-left:15px;color:#4c54f9;font-size:14px}
.findpassword_main_div_btn{width:510px;height:50px;line-height:50px;color:white;display:block;background:#4c54f9;margin-top:50px;margin-left:145px;}

.findpasswordtwo_main_div_img2{background:url('~@/assets/img/findpassword2.png') no-repeat center;margin-left:140px;width:770px;margin-top:76px;height:100px;}
.findpasswordtwo_main_div_img3{background:url('~@/assets/img/findpassword3.png') no-repeat center;margin-left:140px;width:770px;margin-top:76px;height:100px;}
.findpasswordtwo_main_ts{width:100%;padding-left:155px;color:#708bb0;text-align: left;margin-top: 40px;font-size:14px}
.findpasswordtwo_email{margin-top:50px}
.findpasswordtwo_code{margin-top:30px}
.findpasswordtwo_email_right{width:360px;color:#c2c3ca;height:50px;line-height:50px;text-align:left;font-size:14px;float:left}

.findpasswordthree_desc{width:100%;height:55px;background:url('~@/assets/img/findpassword4.png') no-repeat center;margin-top: 175px;}
.findpasswordsuccess_btn{margin-left:auto;margin-top: 90px}
.findpasswordsuccess_img{background:url('~@/assets/img/findpassword3.png') no-repeat center;}
.findpassword_error{text-align:left;color:#8faacc;font-size:12px;padding:13px 16px;padding-left:25px;box-sizing:border-box;border-radius:2px;width:230px;position:relative;min-height:50px;height:auto;margin-left:30px;background:#3a4a5e;float: left;line-height:20px;}
.findpassword_error::after{
	content: "";
	width:0px;
    height:0px;
    border-top:6px solid rgba(0,0,0,0);
    border-right:6px solid #3a4a5e;
    border-bottom:6px solid rgba(0,0,0,0);
    border-left:6px solid rgba(0,0,0,0);
    position:absolute;
    left:0px;
    margin-left:-12px;
    top:10px;
}
.findpassword_error_1{background:#3a4a5e url('~@/assets/img/findpassword5.png') no-repeat  10px 20px;}
.findpassword_error_2{background:#3a4a5e url('~@/assets/img/findpassword6.png') no-repeat  10px 20px;}
.findpassword_error_3{background:#3a4a5e url('~@/assets/img/findpassword7.png') no-repeat  10px 20px;}
</style>