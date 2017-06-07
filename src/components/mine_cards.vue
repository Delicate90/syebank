<template>
    <div class="container">
        <scroller class="scroller" show-scrollbar="false" >
            <div class="block-list white-block padding-left border-bottom">
                <div class="block-list-cell border-bottom">
                    <image class="block-cell-icon"></image>
                    <div class="block-cell-text">
                        <text class="block-cell-title">中国建设银行（****8188）</text>
                        <text class="block-cell-summary">单笔限额100万，日累积限额100万</text>
                    </div>
                </div>
                <div class="block-list-cell">
                    <image class="block-cell-icon"></image>
                    <div class="block-cell-text">
                        <text class="block-cell-title">中国建设银行（****8188）</text>
                        <text class="block-cell-summary">单笔限额100万，日累积限额100万</text>
                    </div>
                </div>
            </div>
            <div class="block-add white-block margin-top border-top border-bottom">
                <div class="block-add-border">
                    <image class="block-add-icon"></image>
                    <text class="block-add-text">添加银行卡</text>
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
        padding-left: 63px;
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
    .block-list{
        flex-direction: column;
    }
    .block-list-cell{
        flex-direction: row;
        align-items: center;
        height: 140px;
    }
    .block-cell-icon{
        width: 65px;
        height: 65px;
        background-color: #0088fb;
    }
    .block-cell-text{
        flex: 1;
        flex-direction: column;
        margin-left: 30px;
    }
    .block-cell-title{

        font-size: 26px;
    }
    .block-cell-summary{
        margin-top: 15px;
        font-size: 24px;
        color: #999999;
    }

    .block-add{
        justify-content: center;
        align-items: center;
        padding-left: 43px;
        padding-right: 43px;
        padding-top: 47px;
        padding-bottom: 47px;
        height:207px;
    }
    .block-add-border{
        flex-direction: row;
        align-items: center;
        width: 664px;
        height: 113px;
        padding-left: 20px;
        border-width: 1px;
        border-style: dashed;
        border-color: #4a4a4a;
        border-radius: 20px;
    }
    .block-add-icon{
        width: 65px;
        height: 65px;
        border-radius: 65px;
        background-color: #0088fb;
    }
    .block-add-text{
        margin-left:30px;
        font-size: 28px;
        color: #333;
    }
</style>
<script>
    import com_navpage from "../templates/navpage.vue"

    export default{
        data:{
            title:"选择银行卡"
        },
        methods:{

        },
        components:{
            com_navpage
        }
    }
</script>