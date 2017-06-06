 <template>
    <div class="container">

        <scroller class="scroller" show-scrollbar="false" >
            <refresh class="refresh" @refresh="onrefresh" @pullingdown="onpullingdown"
                     :display="refreshing ? 'show' : 'hide'">
                <text class="indicator">Refreshing ...</text>
            </refresh>
            <div class="banner">
                <div class="banner-rate">
                    <text class="banner-rate-number">{{invest.rate}}</text>
                    <text class="banner-rate-unit">%</text>
                </div>
                <text class="banner-text">预期年化收益率</text>
            </div>
            <div class="block-1 white-block padding-left padding-right border-top border-bottom">
                <div class="block-col border-right">
                    <text class="block-col-title">投资期限</text>
                    <text class="block-col-content">{{invest.days}}天</text>
                </div>
                <div class="block-col">
                    <text class="block-col-title">起投金额</text>
                    <text class="block-col-content">{{invest.start}}元</text>
                </div>
            </div>
            <div class="block-2 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row border-bottom">
                    <img class="block-row-icon" />
                    <div class="block-row-content">
                        <text class="block-row-content-title">结束时间: </text>
                        <text class="block-row-content-text text-red">{{end_day}}</text>
                        <text class="block-row-content-text">天</text>
                        <text class="block-row-content-text text-red">{{end_hour}}</text>
                        <text class="block-row-content-text">小时</text>
                        <text class="block-row-content-text text-red">{{end_minute}}</text>
                        <text class="block-row-content-text">分</text>
                        <text class="block-row-content-text text-red">{{end_second}}</text>
                        <text class="block-row-content-text">秒</text>
                    </div>
                </div>
                <div class="block-row">
                    <img class="block-row-icon" />
                    <div class="block-row-content">
                        <text class="block-row-content-title">结算方式:</text>
                        <text class="block-row-content-text">{{invest.type}}</text>
                    </div>
                </div>
            </div>
            <div class="block-3 white-block margin-top padding-left padding-right border-top border-bottom">
                <div class="block-progress-left">
                    <text class="block-progress-title">募集日</text>
                    <img class="block-progess-icon"/>
                    <text class="block-progress-date">{{invest.startDate}}</text>
                </div>
                <div class="block-progress-mid">
                    <text class="block-progress-title">起息日</text>
                    <img class="block-progess-icon"/>
                    <text class="block-progress-date">{{invest.inevestDate}}</text>
                </div>
                <div class="block-progress-right">
                    <text class="block-progress-title">到期日</text>
                    <img class="block-progess-icon"/>
                    <text class="block-progress-date">{{invest.endDate}}</text>
                </div>
                <div class="block-progress-line-left"></div>
                <div class="block-progress-line-right"></div>
            </div>
            <div class="block-4 white-block margin-top padding-left padding-right border-top border-bottom">
                <div class="block-4-mount">
                    <div class="block-4-text">
                        <text class="block-4-text-title">可投金额(元)</text>
                        <text class="block-4-text-content">{{invest.canBuy}}</text>
                    </div>
                    <div class="block-4-text" style="align-items: flex-end">
                        <text class="block-4-text-title">预期收益(元)</text>
                        <text class="block-4-text-content" style="color:#f00;">{{invest.res}}</text>
                    </div>
                </div>
                <div class="block-4-input">
                    <text @click="amountLess" class="block-4-input-less">-</text>
                    <input type="tel" class="block-4-input-content" :placeholder="invest.amount_placeholder" maxlength="9" return-key-type="done" :value="invest.amount" @blur="amountBlur" @input="oninput"/>
                    <text @click="amountMore" class="block-4-input-more">+</text>
                </div>
            </div>
            <div v-if="invest.item_type == '03'" class="block-5 white-block margin-top padding-left padding-right border-top border-bottom">
                <div class="block-row">
                    <text class="block-exclusive-title">专属码:</text>
                    <input class="block-exclusive-code" type="text" />
                </div>
                <text class="block-exclusive-summary block-row">专属项目仅供指定客户购买，需输入专属码</text>
            </div>
            <div class="block-6 white-block margin-top padding-left border-top border-bottom">
                <div class="block-row border-bottom">
                    <img class="block-row-icon" />
                    <text class="block-row-cell">产品详情</text>
                    <img class="block-row-push" />
                </div>
                <div class="block-row border-bottom">
                    <img class="block-row-icon" />
                    <text class="block-row-cell">投资记录</text>
                    <img class="block-row-push" />
                </div>
                <div class="block-row">
                    <img class="block-row-icon" />
                    <text class="block-row-cell">相关协议</text>
                    <img class="block-row-push" />
                </div>
            </div>
        </scroller>
        <div :class="['footer','border-top', 'footer-' + invest.item_status_css]">
            <text class="footer-text">{{invest.item_status}}</text>
        </div>
        <com_navpage :title="invest.title"></com_navpage>
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
    .refresh{
        flex-direction: row;
        align-items: center;
        justify-content: center;
        width:750px;
        height:60px;
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
    .footer-do{
        background-color: #fd7507;
    }
    .footer-text{
        font-size: 36px;
        color: #fff;
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
        height:85px;
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
        margin-right: 10px;
        color: #666;
    }
    .block-4-input-more{
        margin-left: 10px;
        background-color: #f6ad4a;
        color: #fff;
        border-width:1px;
        border-style: solid;
        border-color: #dedede;
    }
    .block-4-input-content{
        flex: 1;
        padding-left:10px;
        padding-right:10px;
        text-align: center;
        border-width:1px;
        border-style: solid;
        border-color: #dedede;
    }


    .block-5{
        padding-top:5px;
        height:150px;
    }
    .block-exclusive-title{
        margin-right:20px;
        font-size: 28px;
        color: #333;
    }
    .block-exclusive-code{
        flex: 1;
        height:58px;
        border-width:1px;
        border-style: solid;
        border-color: #dedede;
    }
    .block-exclusive-summary{
        padding-top:12px;
        font-size: 24px;
        color: #f00;
    }

    .block-6{
    }
    .block-row-cell{
        flex: 1;
        margin-left: 17px;
        font-size: 28px;
        color: #333;
    }
    .block-row-push{
        margin-right:20px;
        width:50px;
        height:50px;
        background-color: #0088fb;
    }
</style>
<script>
    import com_navpage from "../templates/navpage.vue"

    export default{
        data:{
            invest:{
                title:"麦乐科1号 PRJ20170604",
                rate:"6.00",
                days:"160",
                start:1000,
                type:"一次性还本付息",
                startDate:"2016.4.29",
                inevestDate:"2016.4.29",
                endDate:"2016.4.29",
                endTime:"2017-06-08 12:33:33",
                canBuy:750000,
                res:"25.85",
                amount:1000,
                amount_placeholder:"起投金额1000元",
                item_type:"01",
                item_status_css:"do",
                item_status:"马上投标"
            },
            end_day:"00",
            end_hour:"00",
            end_minute:"00",
            end_second:"00",
            amount_placeholder:function(){
                return "起投金额1000元";
            }
        },
        components:{
            com_navpage
        },
        methods:{
            amountLess:function(e){
                this.isAmount();
                if(this.invest.amount>this.invest.start){
                    this.invest.amount = this.invest.amount*1 - this.invest.start;
                }
                this.calculateIncome();
            },
            amountMore:function(e){
                this.isAmount();
                if(this.invest.amount > this.invest.canBuy){//是否超过可投金额
                    this.invest.amount = this.invest.canBuy;
                }else{
                    this.invest.amount = this.invest.amount*1 + this.invest.start;
                }
                this.calculateIncome();
            },
            oninput:function(e){
                this.invest.amount = e.value;
            },
            amountBlur:function(e){
                this.isAmount();
                this.calculateIncome();
            },
            isAmount:function(){
                var g = /^[1-9]*[1-9][0-9]*$/;
                if(g.test(this.invest.amount)){//是否为数字
                    if(this.invest.amount >= this.invest.start){//是否小于起投金额
                        var tempAmount;
                        if(this.invest.amount%this.invest.start === 0){//是否为起投金额的倍数
                            tempAmount = this.invest.amount;
                        }else{
                            tempAmount = Math.floor(this.invest.amount/this.invest.start)*this.invest.start;
                        }
                        if(this.invest.canBuy >= tempAmount){//是否超过可投金额
                            this.invest.amount = tempAmount;
                        }else{
                            this.invest.amount = this.invest.canBuy;
                        }
                    }else{
                        this.invest.amount = this.invest.start;
                    }
                }else{
                    this.invest.amount = this.invest.start;
                }
            },
            calculateIncome:function(){
                this.invest.res = (this.invest.amount*this.invest.rate/100)*this.invest.days/360;
            },
            showTime:function(){
                var time = setInterval(function(){
                    var time_now = new Date();  // 获取当前时间
                    time_now = time_now.getTime();
                    var time_end = new Date(this.invest.endTime).getTime();
                    var time_distance = time_end - time_now;  // 结束时间减去当前时间
                    var int_day, int_hour, int_minute, int_second;
                    if(time_distance >= 0){
                        // 天时分秒换算
                        int_day = Math.floor(time_distance/86400000)
                        time_distance -= int_day * 86400000;
                        int_hour = Math.floor(time_distance/3600000)
                        time_distance -= int_hour * 3600000;
                        int_minute = Math.floor(time_distance/60000)
                        time_distance -= int_minute * 60000;
                        int_second = Math.floor(time_distance/1000)

                        // 时分秒为单数时、前面加零站位
                        if(int_hour < 10)
                            int_hour = "0" + int_hour;
                        if(int_minute < 10)
                            int_minute = "0" + int_minute;
                        if(int_second < 10)
                            int_second = "0" + int_second;

                        // 显示时间
                        this.end_day = int_day;
                        this.end_hour = int_hour;
                        this.end_minute = int_minute;
                        this.end_second = int_second;
                    }else{
                        clearInterval(time);
                    }
                },1000);

            },
            loadDetailFunc: function(id,callback){
                callback
            }
        },
        created (){
            this.loadDetailFunc("123123123123123123123",() => {
                this.calculateIncome();
                this.showTime();
            })
        }
    }
</script>