 <template>
    <div class="container">

        <scroller class="scroller" show-scrollbar="false" >
            <refresh class="refresh" @refresh="onrefresh" @pullingdown="onpullingdown"
                     :display="refreshing ? 'show' : 'hide'">
                <text class="indicator">Refreshing ...</text>
            </refresh>
            <div class="banner">
                <div class="banner-rate">
                    <text class="banner-rate-number">6.00</text>
                    <text class="banner-rate-unit">%</text>
                </div>
                <text class="banner-text">预期年化收益率</text>
            </div>
            <div class="block-1 white-block padding-left padding-right border-top border-bottom">
                <div class="block-col border-right">
                    <text class="block-col-title">投资期限</text>
                    <text class="block-col-content">160天</text>
                </div>
                <div class="block-col">
                    <text class="block-col-title">起投金额</text>
                    <text class="block-col-content">1000元</text>
                </div>
            </div>
            <div class="block-2 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row border-bottom">
                    <img class="block-row-icon" />
                    <div class="block-row-content">
                        <text class="block-row-content-title">结束时间: </text>
                        <text class="block-row-content-text text-red">01</text>
                        <text class="block-row-content-text">天</text>
                        <text class="block-row-content-text text-red">01</text>
                        <text class="block-row-content-text">小时</text>
                        <text class="block-row-content-text text-red">01</text>
                        <text class="block-row-content-text">分</text>
                        <text class="block-row-content-text text-red">01</text>
                        <text class="block-row-content-text">秒</text>
                    </div>
                </div>
                <div class="block-row">
                    <img class="block-row-icon" />
                    <div class="block-row-content">
                        <text class="block-row-content-title">结算方式:</text>
                        <text class="block-row-content-text">一次性还本付息</text>
                    </div>
                </div>
            </div>
            <div class="block-3 white-block margin-top padding-left padding-right border-top border-bottom">
                <div class="block-progress-left">
                    <text class="block-progress-title">募集日</text>
                    <img class="block-progess-icon"/>
                    <text class="block-progress-date">2016.4.29</text>
                </div>
                <div class="block-progress-mid">
                    <text class="block-progress-title">起息日</text>
                    <img class="block-progess-icon"/>
                    <text class="block-progress-date">2016.4.29</text>
                </div>
                <div class="block-progress-right">
                    <text class="block-progress-title">到期日</text>
                    <img class="block-progess-icon"/>
                    <text class="block-progress-date">2016.4.29</text>
                </div>
                <div class="block-progress-line-left"></div>
                <div class="block-progress-line-right"></div>
            </div>
            <div class="block-4 white-block margin-top padding-left padding-right border-top border-bottom">
                <div class="block-4-mount">
                    <div class="block-4-text">
                        <text class="block-4-text-title">可投金额(元)</text>
                        <text class="block-4-text-content">750,000</text>
                    </div>
                    <div class="block-4-text" style="align-items: flex-end">
                        <text class="block-4-text-title">预期收益(元)</text>
                        <text class="block-4-text-content" style="color:#f00;">25.85</text>
                    </div>
                </div>
                <div class="block-4-input">
                    <div class="block-4-input-less">-</div>
                    <input type="number" class="block-4-input-content"/>
                    <div class="block-4-input-more">+</div>
                </div>
            </div>
            <div class="block-5 white-block margin-top padding-left padding-right border-top border-bottom">
                <div>
                    <text>专属码:</text>
                    <input />
                </div>
                <text>专属项目仅供指定客户购买，需输入专属码</text>
            </div>
            <div class="block-6 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row border-bottom">
                    <img />
                    <text>产品详情</text>
                    <img />
                </div>
                <div class="block-row border-bottom">
                    <img />
                    <text>投资记录</text>
                    <img />
                </div>
                <div class="block-row">
                    <img />
                    <text>相关协议</text>
                    <img />
                </div>
            </div>
        </scroller>
        <div class="footer border-top">
            <text>马上投标</text>
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

    .container {
        background-color: #eee;
    }

    .scroller {
        padding-top:88px;
        padding-bottom:107px;
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
    }
    .banner{
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
    .banner-rate-unit{
        color:#fff;
        font-size: 30px;
        line-height:60px;
    }
    .banner-text{
        margin-bottom:20px;
        color:#fff;
        font-size: 30px;
    }
    .white-block{
        position: relative;
        width:750px;
        background-color: #fff;
    }
    .block-1{
        height:92px;
        flex-direction: row;
        padding-top:10px;
        padding-bottom:10px;
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
    .block-col-title{
        margin-bottom:5px;
    }

    .block-2{
    }
    .block-row{
        flex-direction: row;
        height:80px;
        align-items: center;
    }
    .block-row-icon{
        width:50px;
        height:50px;
        background-color: #0088fb;
    }
    .block-row-content{
        flex-direction: row;
        align-items: center;
        margin-left: 17px;
    }
    .block-row-content-title{
        padding-right:5px;
        font-size: 28px;
        color: #333;
    }
    .block-row-content-text{
        font-size: 28px;
        color: #333;
    }
    .text-red{
        margin-right:3px;
        color: #f00;
        font-size:30px;
    }

    .block-3{
        position: relative;
        flex-direction: row;
        height:205px;
    }
    .block-progress-left{
        flex-direction: column;
        justify-content: center;
        align-items: flex-start;
        width:190px;
    }
    .block-progress-mid{
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width:190px;
    }
    .block-progress-right{
        flex-direction: column;
        justify-content: center;
        align-items: flex-end;
        width:304px;
    }
    .block-progress-title{
        margin-bottom:25px;
        font-size:26px;
    }
    .block-progess-icon{
        margin-bottom:25px;
        width:45px;
        height:45px;
        background-color: #0088fb;
    }
    .block-progress-date{
        font-size:24px;
        color: #666;
    }
    .block-progress-line-left{
        position: absolute;
        left:110px;
        top:100px;
        width: 175px;
        height: 2px;
        background-color: #f6b153;
    }
    .block-progress-line-right{
        position: absolute;
        right:90px;
        top:100px;
        width: 290px;
        height: 2px;
        background-color: #f6b153;
    }

    .block-4{
        padding-top:20px;
        padding-bottom:20px;
        height:222px;
    }
    .block-4-mount{
        flex-direction: row;
        justify-content: space-between;
    }
    .block-4-text{

    }
    .block-4-text-title{
        font-size:26px;
    }
    .block-4-text-content{
        margin-top:10px;
        font-size:34px;
    }
    .block-4-input{
        margin-top: 20px;
        flex-direction: row;
    }
    .block-4-input-less,.block-4-input-more{
        width:75px;
        height:75px;
        background-color: #dedede;
        font-size: 55px;
        text-align: center;
    }
    .block-4-input-less{
        margin-right: 4px;
        color: #666;
    }
    .block-4-input-more{
        margin-left: 4px;
        background-color: #f6ad4a;
        color: #fff;
        border-width:1px;
        border-style: solid;
        border-color: #dedede;
    }
    .block-4-input-content{
        flex: 1;
        border-width:1px;
        border-style: solid;
        border-color: #dedede;
    }


    .block-5{
        height:150px;
    }

    .block-6{
    }
</style>
<script>
    import com_navpage from "../templates/navpage.vue"

    export default{
        data:{
            title:"麦乐科1号 PRJ20170604"
        },
        components:{
            com_navpage
        },
        methods:{

        }
    }
</script>