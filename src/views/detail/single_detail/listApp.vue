<template>
	<div id="app">
        <div class="bg">
            <div class="detail">
                <div class="plane_com">
                    <img src="./assets/ticket_tab_shijianpaixu@2x.png" alt="">
                    <span>东方航空MU2845</span>
                </div>
                <div class="time">
                    <div class="from_time">
                        <p>12:30</p>
                        <span>禄口机场T2</span>
                    </div>
                    <div class="pic"><img src="./assets/ticket_query_result_arrow@2x.png" alt=""></div>
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
</template>

<script>
import 'assets/js/rem.js';
import 'assets/css/common.css'
export default {
  data() {
    return {}

  }
}
</script>

<style lang="less" scoped>
    #app{
        font-family: PingFangSC-Regular;
        letter-spacing: 0;
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
                    img{
                        width:.12rem;
                        height:.12rem;
                        margin-left:.12rem;
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
                    .pic{
                        float:left;
                        margin:.16rem 0 0 .25rem;
                        img{
                            width:.65rem;
                            height:.05rem;
                        }
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
    }
</style>
