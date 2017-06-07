<template>
    <div class="container">
        <div class="scroller">
            <div class="block-1">
                <div class="banner-rate">
                    <text class="banner-rate-number">{{invest.rate | money}}</text>
                </div>
                <text class="banner-text">预期年化收益率</text>
            </div>
            <div class="block-2">
                <div class="block-col border-right">
                    <text class="block-col-title">投资期限</text>
                    <text class="block-col-content">{{invest.days}}天</text>
                </div>
                <div class="block-col">
                    <text class="block-col-title">起投金额</text>
                    <text class="block-col-content">{{invest.start}}元</text>
                </div>
            </div>
            <div class="block-3">
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
                <div class="block-row">
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

</style>
<script>
    import com_navpage from "../templates/navpage.vue"
    import icon from "../templates/v-icon.vue"

    export default{
        data:{
            title: ""
        },
        methods:{

        }
    }
</script>