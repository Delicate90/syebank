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
            <div class="">
                <div class="">
                    <text class="">投资期限</text>
                    <text class="">160天</text>
                </div>
                <div class="">
                    <text class="">起投金额</text>
                    <text class="">1000元</text>
                </div>
            </div>
            <div class="">
                <div>
                    <img />
                    <div>
                        <text>结束时间: </text>
                        <div class="">01</div>
                        <div class="">天</div>
                        <div class="">01</div>
                        <div class="">小时</div>
                        <div class="">01</div>
                        <div class="">分</div>
                        <div class="">01</div>
                        <div class="">秒</div>
                    </div>
                </div>
                <div class="">
                    <img />
                    <div>
                        <text>结算方式:</text>
                        <text>一次性还本付息</text>
                    </div>
                </div>
            </div>
            <div class="">
                <div class="">
                    <text>募集日</text>
                    <img/>
                    <text></text>
                </div>
                <div class="">
                    <text>起息日</text>
                    <img/>
                    <text></text>
                </div>
                <div class="">
                    <text>到期日</text>
                    <img/>
                    <text></text>
                </div>
                <div class="line"></div>
                <div class="line"></div>
            </div>
            <div class="">
                <div>
                    <div>
                        <text>可投金额(元)</text>
                        <text></text>
                    </div>
                    <div>
                        <text>预期收益(元)</text>
                        <text></text>
                    </div>
                </div>
                <div>
                    <div></div>
                    <input />
                    <div></div>
                </div>
            </div>
            <div>
                <div>
                    <text>专属码:</text>
                    <input />
                </div>
                <text>专属项目仅供指定客户购买，需输入专属码</text>
            </div>
            <div>
                <div>
                    <img />
                    <text>产品详情</text>
                    <img />
                </div>
                <div>
                    <img />
                    <text>投资记录</text>
                    <img />
                </div>
                <div>
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

    .container {
        background-color: #eee;
    }

    .scroller {
        min-height: 1334px;
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
        margin-top:88px;
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