<template>
    <div class="container">
        <scroller class="scroller" show-scrollbar="false" loadmoreoffset="400" @loadmore="onloadmore">
            <refresh class="refresh" @refresh="onrefresh" @pullingdown="onpullingdown"
                     :display="refreshing ? 'show' : 'hide'">
                <text class="indicator">Refreshing ...</text>
            </refresh>
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
                            <div class="field-progress">
                                <svg style="width:94px;height:94px;">
                                    <circle cx="47" cy="47" r="45" stroke="red" stroke-width="4" fill="white"/>
                                </svg>
                            </div>
                            <text class="cell-field-content">剩999万/{{item.max_finance_money / 10000 }}万</text>
                        </div>
                    </div>
                </div>
        </scroller>
        <div class="header" :style="{opacity: headerOpacity, backgroundColor: headerBackgroundColor}">
            <text class="header-left">&#xe711;</text>
            <text class="header-title">{{title}}</text>
            <text class="header-right"></text>
        </div>
    </div>
</template>
<link href="../css/main.css" type="text/css" rel="stylesheet"/>
<style scoped>
    .invest-list {
    }

    .invest-list-cell {
        height: 258px;
        background-color: #fff;
        margin-bottom: 14px;
    }

    .cell-title {
        margin-top: 42px;
        flex-direction: row;
        align-items: center;
    }

    .cell-title-icon {
        height: 40px;
        width: 40px;
        background-color: #0088fb;
        margin-left: 20px;
        margin-right: 10px;
    }

    .cell-title-content {
        width: 350px;
        font-size: 30px;
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
        width: 250px;
        height:146px;
        justify-content: center;
    }

    .field-rate,.field-time,.field-progress{
        width:250px;
        height:120px;
    }

    .field-rate {
        flex-direction: row;
        justify-content: center;
        align-items: center;
    }

    .field-rate-num {
        font-size: 48px;
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
        align-items: center;
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
        text-align: center;
        font-size: 24px;
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
    var stream = weex.requireModule('stream');

    export default{
        data: {
            title: '投资列表',
            refreshing: false,
            lists: [],
            pageNumber: 1
        },
        methods: {
            onrefresh: function (event) {
                console.log('is refreshing');
                modal.toast({message: 'refresh', duration: 1});
                this.refreshing = true;
                setTimeout(function () {
                    modal.toast({message: 'refresh ok!', duration: 1});
                    this.pageNumber = 1;
                    this.loadListFunc(this.pageNumber, res => {
                        this.lists = res.data.response.page.list
                    })
                    this.refreshing = false;
                }.bind(this), 2000)
            },
//            onpullingdown: function (event) {
//
//            },
//            onloadmore: function (event) {
//                modal.toast({message: 'loading', duration: 1})
//                setTimeout(function () {
//                    this.pageNumber++;
//                    this.loadListFunc(this.pageNumber, res => this.lists.push(res.data.response.page.list))
//                    dom.resetLoadmore(el, {});
//                }.bind(this), 1500)
//            },
            loadListFunc: function (pageNum, callback) {
                return stream.fetch({
                    method: 'POST',
                    type: 'json',
                    url: 'http://192.168.10.13:85/api/product/item/findAllInvestItemsList?pageNumber=' + pageNum + '&pageSize=' + 10
                }, callback)
            }
        },
        created (){
            this.loadListFunc(this.pageNumber, res => {
                this.lists = res.data.response.page.list
            })
        }
    }
</script>