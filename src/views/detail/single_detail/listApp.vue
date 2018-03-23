<template>
	<div id="app">
        <header>
            <div class="back_icon"></div>
            <div class="air_line">
                <p><span>北京</span>&nbsp;&nbsp;<span></span>&nbsp;&nbsp;<span>杭州</span></p>
                <div class="date">03月21日</div>
            </div>
        </header>
        <div class="main" v-if="showMain">
            <div class="bg">
                <div class="detail">
                    <div class="plane_com">
                        <div class="logo"></div>
                        <span>东方航空MU2845</span>
                    </div>
                    <div class="time">
                        <div class="from_time">
                            <p>12:30</p>
                            <span>禄口机场T2</span>
                        </div>
                        <div class="to_pic"></div>
                        <div class="to_time">
                            <p>00:20</p>
                            <span>白云T1</span>
                        </div>
                    </div>
                    <div class="spacing_time">
                        <span>无餐食 <i>|</i> 约9小时5分钟</span>
                    </div>
                </div>
            </div>
            <ul class="list">
                <li>
                    <div class="price">
                        <p><span>月供<i>￥</i><b>200</b>起</span><a>&nbsp;&nbsp;成人票 ￥900</a><a>&nbsp;&nbsp;儿童票 ￥500</a></p>
                        <div><a>经济舱 &nbsp;&nbsp;|&nbsp;&nbsp;退改￥300起&nbsp;&nbsp;|&nbsp;&nbsp;免费行李额30KG &nbsp;&gt;</a> </div>
                    </div>
                    <div class="btn">
                        <a>预订</a>
                        <p>剩3张</p>
                    </div>
                </li>
                <li>
                    <div class="price">
                        <p><span>月供<i>￥</i><b>200</b>起</span><a>&nbsp;&nbsp;成人票 ￥900</a><a>&nbsp;&nbsp;儿童票 ￥500</a></p>
                        <div><a>经济舱 &nbsp;&nbsp;|&nbsp;&nbsp;退改￥300起&nbsp;&nbsp;|&nbsp;&nbsp;免费行李额30KG &nbsp;&gt;</a> </div>
                    </div>
                    <div class="btn">
                        <a>预订</a>
                    </div>
                </li>
            </ul>
        </div>
        <div class="nothing" v-if="showNoting">
            <div class="pic"></div>
            <p>抱歉，没有查询到结果</p>
            <div class="research">重新搜索</div>
        </div>
    </div>
</template>

<script>

export default {
  data() {
    return {
        showMain:true,
        showNoting:false
    }

  }
}
</script>

<style lang="less" scoped>
    .bg-image(@url){
        background-image:~"url(@{url}@2x.png)";
        @media (-webkit-min-device-pixel-ratio: 3),(min-device-pixel-ratio: 3){
        background-image:~"url(@{url}@3x.png)";
        }
    }
    #app{
        font-family: PingFangSC-Regular;
        letter-spacing: 0;
        header{
            background-image: linear-gradient(90deg, #FCE105 0%, #FECD15 100%);   
            height:.44rem;
            overflow: hidden;
            .back_icon{
                float:left;
                height:.44rem;
                width:.39rem;
                .bg-image('./assets/global_nav_back');
                background-size: .39rem .44rem;
            }
            .air_line{
                width:.96rem;
                margin:0.08rem auto 0;
                color: #222222;
                p{
                    font-size: .16rem;
                    line-height: .16rem;
                    span:nth-child(2){
                        .bg-image("./assets/ticket_query_to");
                        background-size:.12rem .1rem;
                        display: inline-block;
                        width:.12rem;
                        height:.1rem
                    }
                }
                .date{
                    font-size: .1rem;
                    line-height: .2rem;
                    color: #222222;
                    text-align: center;
                }
            }         
        }
        .bg{
            width:3.59rem;
            height:1.3rem;
            background-image: linear-gradient(90deg, #FCE105 0%, #FECD15 100%);
            padding:.03rem .08rem .08rem;
            .detail{
                background:#fff;
                width:3.59rem;
                height:1.3rem;
                .plane_com{
                    .logo{
                        .bg-image('./assets/ticket_tab_shijianpaixu');
                        display: inline-block;
                        width:.12rem;
                        height:.12rem;
                        margin-left:.12rem;
                        background-size: .12rem .12rem
                    }
                    span{
                        font-size: .12rem;
                        color: #666666;
                        line-height: .36rem;
                    }
                }
                .time{
                    margin-top: .05rem;
                    height:.55rem;
                    text-align: center;
                    .from_time{
                        float:left;
                        margin-left:.46rem;
                        width:.78rem;
                    }
                    p{
                        font-size: .3rem;
                        color: #222222;
                        line-height: .3rem; 
                    }
                    span{
                        font-size: .12rem;
                        color: #666666;
                        line-height: .25rem;
                    }
                    .to_pic{
                        float:left;
                        margin:.16rem 0 0 .25rem;
                        .bg-image('./assets/ticket_query_result_arrow');
                        width:.65rem;
                        height:.05rem;
                        background-size: .65rem .05rem;
                    }
                    .to_time{
                        float:right;
                        margin-right:.4rem
                    }
                }
                .spacing_time{
                    font-size: .12rem;
                    color: #666666;
                    line-height: .36rem;
                    text-align: center;
                    i{
                        color: #ddd;
                    }
                }
            }
        }
        .list{
            li{
                border-bottom: 0.01rem solid #ddd;
                height:.99rem;
                padding:0.26rem .08rem 0 .15rem;
                box-sizing: border-box;
                .price{
                    float:left;
                    a{
                        color:#999;
                        font-size: .12rem;
                        line-height:.2rem;
                    }
                    p{
                        span{
                            font-size: .14rem;
                            color: #00261C;
                            line-height: .2rem;
                            i{
                                color:#eb5640;
                                font-size: .12rem; 
                            }
                            b{
                                font-size: .2rem;
                                color:#eb5640;
                                font-weight: 600;
                            }
                        }
                    }
                    div{
                        a{
                            line-height: .24rem;
                        }
                    }
                }
                .btn{
                    float:right;
                    text-align: center;
                    margin-top:.08rem;
                    width:.85rem;
                    a{
                        display: inline-block;
                        width:.85rem;
                        height:.35rem;
                        background-image: linear-gradient(90deg, #FCE105 0%, #FECD15 100%);
                        border-radius: 1rem;
                        line-height: .35rem;
                        font-size: .14rem;
                        color: #1D0F00;
                    }
                    p{
                        font-size:.12rem;
                        line-height: .22rem;
                        color:#eb5640;
                    }
                }
            }
        }
        .nothing{
            width:1.6rem;
            margin:1.18rem auto 0;
            text-align: center;
            .pic{
                width:1.05rem;
                height:1.05rem;
                margin:0 auto;
                .bg-image('./assets/ticket_query_nothing');
                width:1.05rem;
                height:1.05rem;
                background-size: 1.05rem 1.05rem;
            }
            p{
                font-size: 0.16rem;
                line-height: .54rem;
                color:#666666;
            }
            .research{
                width:1.4rem;
                height:.4rem;
                margin:.5rem auto;
                border:.01rem solid #ddd;
                border-radius: 1rem;
                line-height: .4rem;
                font-size: .14rem;
                color:#666;
            }
        }
    }
</style>
