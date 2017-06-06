<template>
    <div class="container">
        <scroller class="scroller" show-scrollbar="false" >
            <div class="block-1 white-block padding-left border-bottom">
                <div class="block-row border-bottom">
                    <text class="block-row-text">麦乐科1号 PRJ20170607</text>
                </div>
                <div class="block-row">
                    <text class="block-row-text">交易成功</text>
                </div>
            </div>
            <div class="block-2 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row border-bottom">
                    <text class="block-row-text">投资信息</text>
                </div>
                <div class="block-content">
                    <div class="block-content-cell">
                        <text class="block-content-title">投资金额:</text>
                        <text class="block-content-text">10,000.00元</text>
                    </div>
                    <div class="block-content-cell">
                        <text class="block-content-title">预期收益:</text>
                        <text class="block-content-text">210.00元</text>
                    </div>
                    <div class="block-content-cell">
                        <text class="block-content-title">产品起息日:</text>
                        <text class="block-content-text">2017年04月20日</text>
                    </div>
                    <div class="block-content-cell">
                        <text class="block-content-title">产品到期日:</text>
                        <text class="block-content-text">2017年04月20日</text>
                    </div>
                </div>
            </div>
            <div class="block-3 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row border-bottom">
                    <text class="block-row-text">产品信息</text>
                </div>
                <div class="block-content">
                    <div class="block-content-cell">
                        <text class="block-content-title">发行规模:</text>
                        <text class="block-content-text">500,000.00元</text>
                    </div>
                    <div class="block-content-cell">
                        <text class="block-content-title">预计年化:</text>
                        <text class="block-content-text">6.00%</text>
                    </div>
                    <div class="block-content-cell">
                        <text class="block-content-title">产品期限:</text>
                        <text class="block-content-text">60天</text>
                    </div>
                </div>
            </div>
            <div class="block-4 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row border-bottom">
                    <text class="block-row-text">回款银行卡</text>
                </div>
                <div class="block-content block-content-row padding-right">
                    <text class="block-content-card">中国建设银行</text>
                    <text class="block-content-card">****0188</text>
                    <text class="block-content-card">储蓄卡</text>
                    <text class="block-content-card">*静</text>
                </div>
            </div>
            <div class="block-5 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row border-bottom">
                    <text class="block-row-text">相关协议</text>
                </div>
                <div class="block-content">
                    <div class="block-content-cell">
                        <text class="block-content-text agress-blue">借款协议</text>
                    </div>
                    <div class="block-content-cell">
                        <text class="block-content-text agress-blue">融资服务协议</text>
                    </div>
                </div>
            </div>
        </scroller>
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
        padding-bottom:20px;
    }
    .white-block{
        position: relative;
        width:750px;
        background-color: #fff;
    }
    .block-1{

    }
    .block-row{
        justify-content: center;
        height:80px;
    }
    .block-row-text{
        font-size: 30px;
    }
    .block-content{
        margin-top: 20px;
    }
    .block-content-cell{
        flex-direction: row;
        align-items: center;
        margin-bottom: 20px;
    }
    .block-content-title{
        width: 180px;
        font-size: 26px;
        color: #666;
    }
    .block-content-text{
        font-size: 26px;
        color: #666;
    }
    .block-content-row{
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        margin-top: 0;
        height: 80px;
    }
    .block-content-card{
        font-size: 26px;
        color: #666;
    }
    .agress-blue{
        color: #4685fa;
    }
</style>
<script>
    import com_navpage from "../templates/navpage.vue"

    export default{
        data:{
            title:"资产详情"
        },
        methods:{

        },
        components:{
            com_navpage
        }
    }
</script>