<template>
    <div class="beijing">
        <!-- 登陆 -->
         <div class="kapian" v-show="pm==true">
            <div class="ka1">
                <a @click="ma" href="javascript:;"><img src="../../assets/login-1.jpg" alt=""></a>
                <a @click="xin" href="javascript:;">新用户注册</a>
            </div>
            <div class="ka2">
                <div>
                账户:<input v-model="uname"  type="text" name="uname" placeholder="请输入用户名">
                </div>
                <span v-show="yin==true">用户名3~12位</span>
            </div>
            <div class="ka3">
                <div>
                密码:<input v-model="upwd"  type="password" name="upwd" placeholder="请输入密码"> 
                </div>
                  <span v-show="cang==true">密码3~8位</span>
            </div>
            <div class="ka4">
                <div>
                <input type="checkbox">自动登陆
                </div>
                <a href="javascript:;">忘记密码</a>
            </div>
            <div class="ka5">
                <button @click="login">登陆</button>
            </div>
        </div>
        <!-- 二维码 -->
         <div class="ma" v-show="am==true">
            <img src="../../assets/login-1.jpg" alt="">
            <a @click="hui" href="javascript:;">账号登陆</a>
        </div>
        <!-- 注册 -->
        <div class="zhu" v-show="cm==true">
            <div class="zhu1">
                <a @click="hui" href="javascript:;">登陆</a>
                <div></div>
            </div>
            <div class="zhu2">
                <div>用户名:</div>
                <div>
                <input type="text" name="uname" v-model="uname">
                </div>
                <span>用户名长度3~12位</span>
            </div>
            <div class="zhu3">
                <div>登录密码: <input type="password" name="upwd" v-model="upwd"></div>
                 <span>密码长度3~8位</span>
            </div>
            <div class="zhu4">
                <div>确认密码: <input type="password" name="upwd" v-model="upwd"></div>
                 <span>密码长度3~8位</span>
            </div>
            <div class="zhu5">
                <button>提交用户注册信息</button>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data(){
        return{
            yin:false,
            cang:false,
            uname:"",
            upwd:"" ,
            pm:true,
            am:false,
            cm:false
        }
    },
    methods:{
     login(){
         var n=this.uname;
         var p=this.upwd;
         var nreg=/^[a-zA-Z0-9]{3,10}$/;
         var preg=/^[a-zA-Z0-9]{3,8}$/;
            if(this.uname==""&&!nreg.test(n)){
                this.yin=true;
            }else{
                this.yin=false;
            }
            if(this.upwd==""&&!preg.test(p)){
                this.cang=true;
            }else{
                this.cang=false;
            }
            this.$router.push("/")
        },
        ma(){
            this.pm=false;
            this.am=true;
            this.cm=false;
        },
        hui(){
            this.pm=true;
            this.cm=false;
            this.am=false;
        },
        xin(){
            this.pm=false;
            this.cm=true;
            this.am=false; 
        }
    },
    wacth(){
        this.login();
    }
}
</script>
<style scoped>
/*背景图片*/
.beijing{
    width: 1200px;
    height: 600px;
    background-image: url(../../assets/login-2.jpg);
    background-repeat: no-repeat;
    background-size: 1200px 600px;
    margin: 0 auto;
    position: relative;
}
/*登陆*/
.ma>img{
    width: 200px;
    height: 200px;
    position: absolute;
    top:200px;
    left: 150px;
}
.ma>a{
  position: relative;
  left: -280px;
  top: 150px;
  text-decoration: none;
  color: #fff
}
.kapian{
    width: 250px;
    height: 200px;
    line-height: 40px;
	background-color:rgba(0,0,0,0);
	padding:5px;
    position: absolute;
    top:120px;
    left:100px;
}
/*ka1*/
.ka1{
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: #fff;
}
.ka1>a{
    text-decoration: none;
    color: #fff;
}
.ka1>a>img{
    width: 40px;
    height: 40px;
}
/*ka2,ka3,ka4*/
.ka2>div>input,.ka3>div>input{
    width:210px;height:38px;
	border:0;outline:0;
    background:#fff url(../../assets/login-3.jpg) no-repeat 97% center;
	font-size:13.333px;
	box-sizing:border-box;
	padding:10px 0;
	margin:18px 0;
	padding-left:15px;

}
.ka3>div>input{
    background-image:url(../../assets/login-4.jpg);		
}
.ka2,.ka3,.ka4{
    display: flex;
    align-items: center;
    justify-content: space-between;
    color:#fff;
    font-weight: 700;
}
.ka2{
    width: 340px;
}
.ka3{
    width: 330px;
}
.ka2>span,.ka3>span{
    font-size: 10px;
    color: red;
}
/*ka4*/
.ka4>a{
    text-decoration: none;
    color: #fff;
}
/*ka5*/
.ka5>button{
    width: 250px;
    height: 35px;
    background-color:#0aa1ed;
    border:0;
    font-size: 18px;
    color: #fff;
}
/*注册*/
.zhu{
    width: 440px;
    height: 400px;
    line-height: 50px;
	background-color:rgba(0,0,0,0);
	padding:5px;
    position: absolute;
    top:120px;
    left:100px;
}
.zhu1,.zhu2,.zhu3,.zhu4{
    display: flex;
    align-items: center;
    justify-content: space-between;
    color:#fff;
    font-weight: 700;
}
.zhu2>div>input,.zhu3>div>input,.zhu4>div>input{
    width:210px;height:30px;
	border:0;outline:0;
	font-size:13.333px;
	box-sizing:border-box;
	padding:10px 0;
	margin:18px 0;
	padding-left:15px;
}
.zhu2>span,.zhu3>span,.zhu4>span{
    color: red;
}
.zhu1>a>img{
    width: 40px;
    height: 40px;
}
.zhu1>a{
    text-decoration: none;
    color: #fff;
}
.zhu5>button{
    width: 210px;
    height: 35px;
    background-color:#0aa1ed;
    border:0;
    font-size: 18px;
    color: #fff;
    margin-right: 80px;
}
</style>
