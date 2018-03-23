<template>
	<div id="app">
        <p>儿童票购买说明<span>(按航班起飞的当日实际你年龄计算)</span></p>
        <ul>
            <li>1.2周岁（含）-12周岁（不含）可购买儿童票</li>
            <li>2.儿童购票可使用身份证、户口簿、护照等，具体以航班和舱位要求为准</li>
            <li>3.儿童乘机须有成人陪同，1名成人最多携带2名儿童</li>
            <li>4.儿童单独乘机请联系航空公司购票</li>
        </ul>
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
        padding:0 0.15rem;
        letter-spacing: 0;
    }
	p{
        line-height: 0.5rem;
        font-size: 0.16rem;
        color: #222222;
        letter-spacing: 0;
        span{
            font-size: 0.14rem;
            color: #2A2A2A;
            line-height: 0.5rem;
        }
    }
    ul{
        li{
            font-size: 0.14rem;
            color: #666666;
            letter-spacing: 0;
            line-height: 0.2rem;
            margin-bottom: .1rem;
        }
    }
	
</style>
