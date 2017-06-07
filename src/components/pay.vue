<template>
    <div class="container">
        <scroller class="scroller" show-scrollbar="false" >
            <div class="block-1 white-block padding-left border-bottom">
                <div class="block-row">
                    <text class="block-row-content-title">投资金额:</text>
                    <text class="block-row-content-text text-red">1000元</text>
                </div>
                <div class="block-row">
                    <text class="block-row-content-title">预期收益:</text>
                    <text class="block-row-content-text text-red">0.16元</text>
                </div>
            </div>
            <div class="block-2 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row">
                    <text class="block-row-content-title">真实姓名:</text>
                    <text class="block-row-content-text">*三</text>
                </div>
                <div class="block-row">
                    <text class="block-row-content-title">身份证号:</text>
                    <text class="block-row-content-text">**************5221</text>
                </div>
            </div>
            <div class="block-3 padding-left padding-right">
                <div class="block-3-round"></div>
                <text class="block-3-title">选择支付的银行卡</text>
            </div>
            <div class="block-4 white-block padding-left border-top border-bottom">
                <div class="block-row">
                    <image class="block-row-card-img"></image>
                    <text class="block-row-card-title">中国建设银行</text>
                    <text class="block-row-card-number">*******18888</text>
                </div>
                <div>
                    <div class="block-card-text border-bottom">
                        <text class="block-card-summary">单笔限额100万，日累积限额100万</text>
                        <div class="block-card-change">
                            <text class="block-card-change-text">更换银行卡</text>
                            <image class="block-card-change-img"></image>

                        </div>
                    </div>
                    <div class="block-card-text">
                        <text class="block-card-summary">资金同卡进出，安全又便捷</text>
                    </div>
                </div>
            </div>
            <div class="block-5 white-block margin-top padding-left padding-right border-top border-bottom">
                <text class="block-tip-text">温馨提示:</text>
                <text class="block-tip-text">1. 请仔细核对，本账户是未来投资收益的回款账号</text>
                <text class="block-tip-text">2. 若您尚未开通无卡支付，请到开卡行营业网点开通此功能</text>
            </div>
            <div class="block-6 padding-left padding-right">
                <div class="block-agree-row">
                    <text class="block-agree-icon iconfont">&#xe62f;</text>
                    <text class="block-agree-text">我已阅读并同意</text>
                    <text class="block-agree-link">《投资人服务协议》</text>
                </div>
                <div class="block-agree-row">
                    <image class="block-agree-icon"></image>
                    <text class="block-agree-text">我已阅读并同意</text>
                    <text class="block-agree-link">《快捷支付服务协议》</text>
                </div>
            </div>
        </scroller>
        <div class="footer border-top">
            <text class="footer-text">立即购买</text>
        </div>
        <com_navpage :title="title"></com_navpage>
        <div class="modal-box-bg"></div>
        <div class="modal-box">
            <div class="modal-box-title border-bottom">
                <text class="modal-box-title-content">认证支付</text>
            </div>
            <div class="modal-box-body">
                <text class="modal-box-body-text">本次交易需要短信认证，校验码已发送到您手机186****6025</text>
                <div class="modal-box-body-interactive">
                    <input class="modal-box-body-input" />
                    <text class="modal-box-body-btn border-top border-bottom border-right">获取</text>
                </div>
            </div>
            <div class="modal-box-bottom border-top">
                <text class="modal-box-bottom-btn-cancel border-right">取消</text>
                <text class="modal-box-bottom-btn-confirm">确认付款</text>
            </div>
        </div>
    </div>
</template>
<link href="../css/main.css" type="text/css" rel="stylesheet" />
<style scoped>
    .border-top {
        border-top-width: 1px;
        border-top-style: solid;
        border-top-color: #dedede;
    }
    .border-bottom {
        border-bottom-width: 1px;
        border-bottom-style: solid;
        border-bottom-color: #dedede;
    }
    .border-right {
        border-right-width: 1px;
        border-right-style: solid;
        border-right-color: #dedede;
    }
    .margin-top {
        margin-top:14px;
    }
    .padding-left {
        padding-left: 43px;
    }
    .padding-right {
        padding-right: 43px;
    }
    .container {
        background-color: #eee;
    }
    .scroller {
        padding-top:88px;
        padding-bottom:107px;
    }
    .white-block{
        position: relative;
        width:750px;
        background-color: #fff;
    }
    .footer {
        position: fixed;
        bottom: 0;
        justify-content: center;
        align-items: center;
        width: 750px;
        height: 93px;
        background-color: #6e6e6e;
    }
    .footer-text{
        font-size: 36px;
        color: #fff;
    }
    .block-row{
        flex-direction: row;
        height:70px;
        align-items: center;
    }
    .block-row-content-title{
        padding-right:15px;
        font-size: 28px;
        color: #333;
    }
    .block-row-content-text{
        font-size: 28px;
        color: #333;
    }
    .block-1,.block-2,.block-4,.block-5{
        justify-content: center;
        height: 188px;
    }
    .block-3{
        flex-direction: row;
        align-items: center;
        height: 55px;
    }
    .block-3-round{
        width:15px;
        height:15px;
        border-radius: 15px;
        background-color: #f00;
    }
    .block-3-title{
        margin-left:15px;
        font-size: 28px;
        color: #333;
    }
    .block-6{
        height: 160px;
    }
    .block-row-card-img{
        margin-right:30px;
        width: 50px;
        height: 50px;
        background-color: #0088fb;
    }
    .block-row-card-title{
        margin-right:35px;
        font-size: 28px;
        color: #333;
    }
    .block-row-card-number{
        font-size: 28px;
        color: #333;
    }
    .block-card-text{
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        padding-top:10px;
        padding-bottom:10px;
        margin-left:80px;
    }
    .block-card-summary{
        font-size: 24px;
        color: #999999;
    }
    .block-card-change{
        flex-direction: row;
        padding-right:43px;
    }
    .block-card-change-text{
        font-size: 24px;
        color: #0693fa;
    }
    .block-card-change-img{
        margin-left:10px;
        height:24px;
        width:24px;
        background-color: #0088fb;
    }
    .block-card-summary{
        font-size: 24px;
        color: #999999;
    }
    .block-tip-text{
        font-size: 24px;
        line-height:44px;
        color: #f00;
    }
    .block-agree-row{
        flex-direction: row;
        align-items: center;
        margin-top:30px;
        padding-left:100px;
    }
    .block-agree-icon{
        width: 22px;
        height: 22px;
    }
    .block-agree-text{
        font-size: 24px;
    }
    .block-agree-link{
        font-size: 24px;
        color: #0692fa;
    }
    .text-red{
        margin-right:3px;
        color: #f00;
        font-size:30px;
    }

    .modal-box-bg{
        position: absolute;
        top:0;
        left:0;
        width:750px;
        height:1334px;
        background-color: rgba(0,0,0,0.2)
    }
    .modal-box{
        position: absolute;
        width: 600px;
        height: 400px;
        top:375px;
        left:75px;
        background-color: #fff;
        border-radius: 20px;
        border-width: 1px;
        border-style: solid;
        border-color: #dedede;
    }
    .modal-box-title{
        justify-content: center;
        align-items: center;
        height: 85px;
    }
    .modal-box-title-content{
        font-size: 28px;
        color: #333;
    }
    .modal-box-body{
        flex: 1;
        justify-content: center;
        align-items: center;
        padding-left:30px;
        padding-right:30px;
    }
    .modal-box-body-text{
        font-size: 26px;
        line-height: 36px;
    }
    .modal-box-body-interactive{
        flex-direction: row;
        justify-content: center;
        margin-top: 10px;
    }
    .modal-box-body-input{
        width: 375px;
        height: 70px;
        border-width: 1px;
        border-style: solid;
        border-color: #dedede;
    }
    .modal-box-body-btn{
        padding-top: 20px;
        width: 140px;
        height: 70px;
        background-color: #f9752b;
        color: #fff;
        font-size: 26px;
        text-align: center;
    }
    .modal-box-bottom{
        flex-direction: row;
        justify-content: center;
        align-items: center;
        height: 100px;
    }
    .modal-box-bottom-btn-cancel,.modal-box-bottom-btn-confirm{
        padding-top: 18px;
        width:260px;
        height:70px;
        font-size: 30px;
        text-align: center;
        color: #333;
    }
    .modal-box-bottom-btn-confirm{
        color: #f9752b;
    }

    .iconfont {
        font-family:"fontFace" !important;
        font-size:16px;
        font-style:normal;
    }
</style>
<script>
    import com_navpage from "../templates/navpage.vue"
    var dom = weex.requireModule('dom')
    dom.addRule('fontFace', {
        'fontFamily': "iconfont",
        'src': "url('../css/iconfont.ttf')"
    });
    export default{
        data:{
            title:"确认支付"
        },
        methods:{
            addFont:function(){

            }
        },
        components:{
            com_navpage
        },
        created(){
            this.addFont();
        }
    }
</script>