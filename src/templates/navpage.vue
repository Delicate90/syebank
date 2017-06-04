<template>
    <div class="container header">
        <text class="header-left"></text>
        <text class="header-title">{{title}}</text>
        <text class="header-right">&#xe711;</text>
    </div>
</template>
<link href="css/main.css" type="text/css" rel="stylesheet" />
<style scoped>
    .header {
        position: absolute;
        top: 0;
        flex-direction: row;
        align-items: center;
        justify-content: center;
        height: 88px;
        background-color: #fd7507;
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

    .banner{
        height:
    }
</style>
<script>

    export default{
        props:{
            title : {
                default:""
            }
        },
        data:{

        },
        methods:{

        }
    }
</script>