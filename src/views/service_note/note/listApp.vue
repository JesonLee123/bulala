<template>
	<div id="app">
        <div class="notice">
            <p><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> &nbsp;预计支付成功后20分钟内出票</p>
            <p><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> &nbsp;免费托运行李额限30KG</p>
        </div>
        <div class="main">
            <div class="adult title">
                <h3>成人退改签说明</h3>
                <table>
                    <tr>
                        <td class="first">退票费</td>
                        <td>
                            <p><span><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> 起飞前2小时外</span><i>￥370/人</i></p>
                            <p><span><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> 起飞前2小时内</span><i>￥555/人</i></p>
                        </td>
                    </tr>
                    <tr>
                        <td class="first">同舱更改条件</td>
                        <td>
                            <p><span><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> 起飞前2小时外</span><i>￥370/人</i></p>
                            <p><span><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> 起飞前2小时内</span><i>￥555/人</i></p>                            
                        </td>
                    </tr>
                    <tr>
                        <td class="first">签转条件</td>
                        <td>不支持套餐签转</td>
                    </tr>
                </table>
            </div>
            <div class="child title">
                <h3>儿童退改签说明</h3>
                <table>
                    <tr>
                        <td class="first">退票费</td>
                        <td>
                            <p><span><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> 起飞前2小时外</span><i>￥139/人</i></p>
                            <p><span><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> 起飞前2小时内</span><i>￥277/人</i></p>
                        </td>
                    </tr>
                    <tr>
                        <td class="first">同舱更改条件</td>
                        <td>
                            <p><span><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> 起飞前2小时外</span><i>免费</i></p>
                            <p><span><img src="./assets/ticket_tab_shijianpaixu@2x.png" alt=""> 起飞前2小时内</span><i>￥139/人</i></p>                            
                        </td>
                    </tr>
                    <tr>
                        <td class="first">签转条件</td>
                        <td>可以转签</td>
                    </tr>
                </table>
            </div>
            <div class="supplier title">
                <h3>供应商</h3>
                <div class="supplier_name">德玛西亚有限公司</div>
            </div>
        </div>
        <div class="order">
            <div class="bg"></div>
            <p>
                <span>月供<b><i>￥</i>200</b>起</span>
                <em>&nbsp; 原价￥900 &nbsp; &nbsp;儿童票￥500</em>
            </p>
            <div class="btn">
                <a>预订</a>
            </div>
        </div>
    </div>
</template>

<script>
import 'assets/js/common.js';
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
        .notice{
            padding:0.07rem 0.15rem;
            background-image: linear-gradient(90deg, #FCE105 0%, #FECD15 100%);
            p{
                font-size: .16rem;
                color: #1D0F00;
                line-height: .31rem; 
                img{
                    width:.162rem;
                    height:.162rem;
                    margin-top: -.03rem
                }
            }
        }
        .main{
            padding:0 .15rem;
            .title{
                padding-top:0.06rem;
                h3{
                    font-weight: 500;
                    font-size: .16rem;
                    color: #222222;
                    line-height: .34rem;
                }
                table{
                    border:0.01rem solid #ddd;
                    width:3.45rem;
                    height:1.9rem;
                    tr{
                        border:0.01rem solid #ddd;
                        td{
                            border:0.01rem solid #ddd;
                            font-size: .14rem;
                            color: #666666;
                            line-height: .14rem; 
                            p{
                                overflow: hidden;
                                margin:0.1rem .1rem .1rem .15rem;
                                span{
                                    float:left;
                                    img{
                                        width:0.12rem;
                                        height:0.12rem;
                                        margin-top:-.03rem
                                    }
                                }
                                i{
                                    float:right;
                                }
                            }                          
                        }
                        .first{
                            width:.87rem;
                            padding-left:.1rem;
                        }
                    }
                    tr:nth-child(3){
                        height:.5rem;
                        td:nth-child(2){
                            padding-left:.15rem;
                        }
                    }
                }
                .supplier_name{
                    font-size: .14rem;
                    color: #666666;
                    line-height: .14rem;
                    margin-bottom: .18rem
                }
            }
        }
        .order{
            height:0.51rem;
            border-top:.01rem solid #ddd;
            .bg{
                // background:url("./assets/Group.png") no-repeat;
                width:100%;
                height:0.02rem;
            }
            p{
                padding:0.08rem 0 0 .15rem;
                float:left;
                width:2.58rem;
                span{
                    font-size: 0.14rem;
                    color: #222222;
                    line-height: 0.38rem;
                    b{
                        font-size: .2rem;
                        color: #eb5640;
                        line-height: .38rem; 
                        font-weight: 600;
                        i{
                            font-size: 0.12rem;
                        }
                    }
                }
                em{
                    font-size: .12rem;
                    color: #999999;
                    line-height: .38rem;
                }
            }
            .btn{
                float:right;
                padding:0.08rem;
                a{
                    display: inline-block;
                    width:.85rem;
                    height:.35rem;
                    background-image: linear-gradient(90deg, #FCE105 0%, #FECD15 100%);
                    border-radius: 1rem;
                    text-align: center;
                    line-height: .35rem;
                    font-size: .14rem;
                    color: #1D0F00;
                }
            }
        }
    }
</style>
