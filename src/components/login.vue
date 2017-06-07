<template>
    <div class="container">
        <div class="scroller">
            <div class="block-top">
                <image class="block-top-logo"></image>
                <text class="block-top-title">山盈e财富</text>
                <text class="block-top-slogan">助力大众创业 实现财富梦想</text>
            </div>
            <div class="block-body padding-left">
                <div class="block-body-row border-bottom">
                    <icon class="block-body-row-icon">&#xe64f;</icon>
                    <input class="block-body-row-input" placeholder="请输入手机号码"/>
                    <image class="block-body-row-tip"></image>
                </div>
                <div class="block-body-row border-bottom">
                    <image class="block-body-row-icon"></image>
                    <input class="block-body-row-input" placeholder="请输入登录密码"/>
                    <image class="block-body-row-tip"></image>
                </div>
                <div class="block-body-row padding-right">
                    <text class="block-body-row-text">忘记密码?</text>
                </div>
            </div>
            <div class="block-btn">
                <div class="block-btn-box block-btn-login">
                    <text class="block-btn-text block-btn-login-text">登录</text>
                </div>
                <div class="block-btn-box">
                    <text class="block-btn-text">快速注册</text>
                </div>
            </div>
        </div>
        <div class="block-bottom">
            <image src="../images/login-bg.png" class="block-bottom-img"></image>
        </div>
        <com_navpage :title="title"></com_navpage>
    </div>
</template>
<link href="../css/main.css" type="text/css" rel="stylesheet" />
<style scoped>
    .container{
        background-color: #fff;
    }
    .scroller {
        padding-top:88px;
    }
    .border-bottom {
        border-bottom-width: 1px;
        border-bottom-style: solid;
        border-bottom-color: #dedede;
    }
    .padding-left {
        padding-left: 43px;
    }
    .padding-right {
        padding-right: 43px;
    }
    .block-top{
        margin-top: 45px;
        justify-content: center;
        align-items: center;
    }
    .block-top-logo{
        width: 196px;
        height: 196px;
        border-radius: 196px;
        background-color: #0088fb;
    }
    .block-top-title{
        margin-top: 20px;
        font-size: 36px;
        font-weight: 700;
        color: #333;
    }
    .block-top-slogan{
        margin-top: 15px;
        font-size: 30px;
        color: #333;
    }
    .block-body{
        margin-top: 30px;
    }
    .block-body-row{
        flex-direction: row;
        align-items: center;
        justify-content: flex-end;
        height: 92px;
    }
    .block-body-row-icon{
        margin-right:20px;
        width: 38px;
        height: 38px;
        font-size: 40px;
        color: #0088fb;
    }
    .block-body-row-tip{
        margin-left:20px;
        margin-right:43px;
        width: 38px;
        height: 38px;
        background-color: #0088fb;
    }
    .block-body-row-input{
        flex: 1;
        height: 30px;
        font-size: 30px;
    }
    .block-body-row-text{
        font-size: 28px;
        color: #0889f6;
    }
    .block-btn{
        flex-direction: column;
        align-items: center;
        margin-top:10px;
    }
    .block-btn-box{
        flex-direction: row;
        justify-content: center;
        align-items: center;
        margin-bottom: 38px;
        width: 495px;
        height: 85px;
        border-color: #dedede;
        border-width: 1px;
        border-style: solid;
        border-radius: 10px;
        background-color: #fff;
    }
    .block-btn-text{
        font-size: 36px;
        color: #666;
    }
    .block-btn-login{
        background-color: #f9752b;
    }
    .block-btn-login:active{
        background-color: #f35613;
    }
    .block-btn-login-text{
        color: #fff;
    }
    .block-bottom{
        position: fixed;
        bottom:0;
        left:0;
    }
    .block-bottom-img{
        width:750px;
    }
</style>
<script>
    import com_navpage from "../templates/navpage.vue"
    import icon from "../templates/v-icon.vue"

    export default{
        data:{
            title: "登录"
        },
        methods:{

        },
        components:{
            com_navpage,icon
        }
    }
</script>