<template>
    <div class="container">
        <scroller class="scroller" show-scrollbar="false" loadmoreoffset="400" @loadmore="onloadmore">
            <refresh class="refresh" @refresh="onrefresh" @pullingdown="onpullingdown"
                     :display="refreshing ? 'show' : 'hide'">
                <text class="indicator">Refreshing ...</text>
            </refresh>
            <slider class="slider border-bottom" interval="3000" auto-play="true">
                <div class="slider-frame" v-for="img in imageList">
                    <image class="slider-frame-image" resize="cover" :src="img.src"></image>
                </div>
            </slider>
            <div class="notice border-bottom">
                <text class="notice-icon">{{pullingDistanceStr}}</text>
                <text class="notice-content">3月25日上午10:00将准时推出新项目麦乐科2号，敬请关注！</text>
            </div>
            <div class="menu border-bottom border-top">
                <div class="menu-panel">
                    <image class="menu-panel-icon" src=""></image>
                    <text class="menu-panel-content">热门活动</text>
                </div>
                <div class="menu-panel">
                    <image class="menu-panel-icon" src=""></image>
                    <text class="menu-panel-content">惠贷款</text>
                </div>
                <div class="menu-panel">
                    <image class="menu-panel-icon" src=""></image>
                    <text class="menu-panel-content">投资指南</text>
                </div>
                <div class="menu-panel">
                    <image class="menu-panel-icon" src=""></image>
                    <text class="menu-panel-content">收益计算</text>
                </div>
            </div>
            <div class="invest">
                <div class="invest-title">
                    <text class="invest-title-icon">钻石</text>
                    <text class="invest-title-content">投资精选</text>
                </div>
                <div class="invest-list">
                    <div class="invest-list-cell border-bottom border-top" v-for="item in lists">
                        <div class="cell-title">
                            <image class="cell-title-icon"></image>
                            <text class="cell-title-content">{{item.item_prefix}} {{item.item_name}}</text>
                            <text class="cell-title-novice" v-if="item.invest_client_type == 04">新手专享</text>
                            <text class="cell-title-direction" v-if="item.invest_client_type == 02">定</text>
                            <text class="cell-title-exclusive" v-if="item.invest_client_type == 03">专</text>
                        </div>
                        <div class="cell-field">
                            <div class="cell-field-rate">
                                <div class="field-rate">
                                    <text class="field-rate-num">{{item.invester_year_rate}}</text>
                                    <text class="field-rate-unit">%</text>
                                </div>
                                <text class="cell-field-content">预期年化利率</text>
                            </div>
                            <div class="cell-field-time">
                                <div class="field-time">
                                    <text class="field-time-day">{{item.finance_period}}</text>
                                    <text class="field-time-unit">天</text>
                                </div>
                                <text class="cell-field-content">投资期限</text>
                            </div>
                            <div class="cell-field-progress">
                                <div class="">
                                    <svg style="width:94px;height:94px;">
                                        <circle cx="47" cy="47" r="45" stroke="red" stroke-width="4" fill="white"/>
                                    </svg>
                                </div>
                                <text class="cell-field-content">剩999万/{{item.max_finance_money/10000 }}万</text>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </scroller>
        <div class="footer border-top">
            <div class="footer-block">
                <image class="footer-block-image" src=""></image>
                <text class="footer-block-content">首页</text>
            </div>
            <div class="footer-block">
                <image src=""></image>
                <text>投资</text>
            </div>
            <div class="footer-block">
                <image src=""></image>
                <text>我的</text>
            </div>
        </div>
        <div class="header" :style="{opacity: headerOpacity, backgroundColor: headerBackgroundColor}">
            <text class="header-left"></text>
            <text class="header-title">{{title}}</text>
            <text class="header-right">&#xe711;</text>
        </div>
    </div>
</template>
<style scoped>
    .border-top{
        border-top-width:1px;
        border-top-style: solid;
        border-top-color: #dedede;
    }

    .border-bottom{
        border-bottom-width:1px;
        border-bottom-style: solid;
        border-bottom-color: #dedede;
    }

    .container {
        background-color: #eee;
    }
    .scroller{
        min-height: 1334px;
    }

    .header {
        position: absolute;
        top: 0;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        height: 88px;
        background-color: transparent;
    }

    .header-title {
        width: 560px;
        font-size: 32px;
        color: #fff;
        text-align: center;
    }

    .header-left, .header-right {
        width: 95px;
        color: #fff;
        font-family: iconfont2;
        font-size: 30px;
        text-align: center;
    }

    .footer {
        position: fixed;
        bottom: 0;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        width: 750px;
        height: 93px;
        background-color: white;
        border-top-color: #f00;
    }

    .footer-block {
        width:250px;
        height:92px;
        justify-content: center;
        align-items: center;
    }

    .footer-block-image{
        width:40px;
        height:40px;
        background-color: #0088fb;
    }

    .footer-block-content{
        margin-top:10px;
        font-size: 22px;
        color: #333;
        width:250px;
        text-align: center;
    }

    .slider {
        width: 750px;
        height: 288px;
    }

    .slider-frame {
        width: 750px;
        height: 288px;
        position: relative;
    }

    .slider-frame-image {
        width: 750px;
        height: 288px;
    }

    .notice {
        flex-direction: row;
        align-items: center;
        height: 64px;
        background-color: #fff;
    }

    .notice-icon {
        width: 64px;
        text-align: center;
        margin-left: 10px;
        font-size: 28px;
    }

    .notice-content {
        font-size: 22px;
    }

    .menu {
        margin-top: 14px;
        height: 198px;
        background-color: #fff;
        flex-direction: row;
        align-items: center;
    }

    .menu-panel {
        width: 187px;
        align-items: center;
    }

    .menu-panel-icon {
        height: 70px;
        width: 70px;
        margin-bottom: 10px;
        background-color: #0088fb;
    }

    .menu-panel-content {
        text-align: center;
        font-size: 25px;
        color: #333;
    }

    .invest {
        margin-bottom:92px;
    }

    .invest-title {
        flex-direction: row;
        align-items: center;
        height: 55px;
    }

    .invest-title-icon {
        width: 55px;
        margin-left: 10px;
        font-size: 30px;
    }

    .invest-title-content {
        font-size: 29px;
        color: #333;
    }

    .invest-list {
    }

    .invest-list-cell {
        height: 258px;
        background-color: #fff;
        margin-bottom: 14px;
    }

    .cell-title {
        margin-top: 35px;
        flex-direction: row;
        align-items: center;
    }

    .cell-title-icon {
        height: 30px;
        width: 30px;
        background-color: #0088fb;
        margin-left: 20px;
        margin-right: 10px;
    }

    .cell-title-content {
        width: 310px;
        font-size: 26px;
    }

    .cell-title-novice {
        width: 120px;
        text-align: center;
        background-color: #000000;
        color: #ffffff;
        font-size: 22px;
        height: 30px;
        line-height: 26px;
    }

    .cell-title-direction, .cell-title-exclusive {
        width: 50px;
        text-align: center;
        font-size: 22px;
        height: 30px;
        line-height: 24px;
        color: #ff0000;
        margin-left: 10px;
        border-width: 1px;
        border-style: solid;
        border-color: #ff0000;
    }

    .cell-field {
        flex-direction: row;
    }

    .cell-field-rate, .cell-field-time, .cell-field-progress {
        margin-top: 28px;
        width: 250px;
        justify-content: center;
    }

    .field-rate {
        flex-direction: row;
        justify-content: center;
        align-items: flex-end;
    }

    .field-rate-num {
        font-size: 50px;
        color: #ff0000;
    }

    .field-rate-unit {
        font-size: 24px;
        line-height: 43px;
        color: #ff0000;
    }

    .field-time {
        flex-direction: row;
        justify-content: center;
        align-items: flex-end;
    }

    .field-time-day {
        font-size: 50px;
        color: #ff0000;
    }

    .field-time-unit {
        font-size: 24px;
        line-height: 48px;
        color: #333;
    }

    .cell-field-content {
        margin-top: 28px;
        text-align: center;
        font-size: 22px;
        color: #000000;
    }

    .refresh {
        width: 750px;
        height: 100px;
    }

    .indicator {
        color: #888888;
        width: 750px;
        font-size: 42px;
        text-align: center;
    }
</style>
<script>
    var dom = weex.requireModule('dom')
    var modal = weex.requireModule('modal');
    var stream = weex.requireModule('stream')

    export default {
        data: {
            title: '山盈e财富',
            imageList: [
                {src: 'https://gd2.alicdn.com/bao/uploaded/i2/T14H1LFwBcXXXXXXXX_!!0-item_pic.jpg'},
                {src: 'https://gd1.alicdn.com/bao/uploaded/i1/TB1PXJCJFXXXXciXFXXXXXXXXXX_!!0-item_pic.jpg'},
                {src: 'https://gd3.alicdn.com/bao/uploaded/i3/TB1x6hYLXXXXXazXVXXXXXXXXXX_!!0-item_pic.jpg'}
            ],
            refreshing: false,
            showLoading: 'hide',
            lists: [],
            headerOpacity: 1,
            pullingDistanceStr: 0,
            headerBackgroundColor: "rgba(0,0,0,0)" //rgb头部
        },
        methods: {
            onrefresh: function (event) {
//                console.log('is refreshing');
//                modal.toast({message: 'refresh', duration: 1});
//                this.refreshing = true;
//                setTimeout(function () {
//                    modal.toast({message: 'refresh ok!', duration: 1});
//                    this.lists = [1, 2, 3, 4, 5, 6, 7];
//                    this.refreshing = false;
//                }.bind(this), 2000)
            },
            onpullingdown: function (event) {

            },
            onloadmore: function (event) {
//                modal.toast({ message: 'loading', duration: 1 })
//                var LOADMORE_COUNT = 7;
//                setTimeout(function () {
//                    var length = this.lists.length;
//                    for (let i = length; i < length + LOADMORE_COUNT; ++i) {
//                        this.lists.push(i + 1)
//                    }
//                    dom.resetLoadmore(el,{});
//                }.bind(this), 1500)
            },
            loadListFunc: function(pageNum,callback) {
                return stream.fetch({
                    method: 'POST',
                    type: 'json',
                    url: 'http://192.168.10.13:85/api/product/item/findAllInvestItemsList?pageNumber='+pageNum+'&pageSize='+10
                },callback)
            }
        },
        created (){
            this.loadListFunc(1,res =>{
                this.lists = res.data.response.page.list
            })
        }
    }
</script>