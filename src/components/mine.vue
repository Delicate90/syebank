<template>
    <div class="container">
        <div class="scroller">
            <div class="block-1">
                <div class="banner-rate">
                    <text class="banner-rate-number">111</text>
                </div>
                <div class="">
                    <text class="banner-text">我的资产(元)</text>
                    <text></text>
                </div>
            </div>
            <div class="block-2 white-block border-bottom">
                <div class="block-col border-right">
                    <text class="block-col-content">111</text>
                    <text class="block-col-title">昨日收益(元)</text>
                </div>
                <div class="block-col">
                    <text class="block-col-content">111</text>
                    <text class="block-col-title">预期总收益(元)</text>
                </div>
            </div>
            <div class="block-3 white-block margin-top padding-left">
                <div class="block-row border-bottom">
                    <image class="block-row-icon"></image>
                    <text class="block-row-cell">产品详情</text>
                    <image class="block-row-push"></image>
                </div>
                <div class="block-row border-bottom">
                    <image class="block-row-icon"></image>
                    <text class="block-row-cell">投资记录</text>
                    <image class="block-row-push"></image>
                </div>
                <div class="block-row border-bottom">
                    <image class="block-row-icon"></image>
                    <text class="block-row-cell">相关协议</text>
                    <image class="block-row-push"></image>
                </div>
                <div class="block-row border-bottom">
                    <image class="block-row-icon"></image>
                    <text class="block-row-cell">投资记录</text>
                    <image class="block-row-push"></image>
                </div>
                <div class="block-row">
                    <image class="block-row-icon"></image>
                    <text class="block-row-cell">相关协议</text>
                    <image class="block-row-push"></image>
                </div>
            </div>
        </div>
        <com_navpage :title="title"></com_navpage>
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

    .white-block{
        position: relative;
        width:750px;
        background-color: #fff;
    }

    .container {
        background-color: #eee;
    }

    .scroller {
        padding-top:88px;
        padding-bottom:107px;
    }
    .block-1{
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height:200px;
        background-color: #fd7507;
    }
    .banner-rate{
        margin-bottom:10px;
        flex-direction: row;
        align-items: flex-end;
        justify-content: center;
    }
    .banner-rate-number{
        color:#fff;
        font-size: 80px;
    }
    .banner-text{
        margin-bottom:20px;
        color:#fff;
        font-size: 30px;
    }

    .block-2{
        height:121px;
        flex-direction: row;
        padding-top:20px;
        padding-bottom:20px;
    }
    .block-col{
        flex:1;
        align-items: center;
        justify-content: center;
    }
    .block-col-title,.block-col-content{
        text-align: center;
        font-size:25px;
        color: #333;
    }
    .block-col-content{
        margin-bottom: 15px;
    }
    .block-3{

    }
    .block-row{
        flex-direction: row;
        align-items: center;
        justify-content: flex-start;
        height: 88px;
    }
    .block-row-icon{
        margin-right: 10px;
        width: 36px;
        height: 36px;
        background-color: #0088fb;
    }
    .block-row-cell{
        flex: 1;
        font-size: 28px;
    }
    .block-row-push{
        margin-right: 43px;
        width: 36px;
        height: 36px;
        background-color: #0088fb;
    }
</style>
<script>
    import com_navpage from "../templates/navpage.vue"
    import icon from "../templates/v-icon.vue"

    export default{
        data:{
            title: ""
        },
        methods:{

        },
        components:{
            com_navpage
        },
        filters: {
            money:function(s){
                s = parseFloat((s + "").replace(/[^\d\.-]/g, "")).toFixed(2) + "";
                var l = s.split(".")[0].split("").reverse(),
                    r = s.split(".")[1],
                    t = "";
                for (var i = 0; i < l.length; i++) {
                    t += l[i] + ((i + 1) % 3 == 0 && (i + 1) != l.length ? "," : "");
                }
                return t.split("").reverse().join("") + "." + r;
            }
        }
    }
</script>