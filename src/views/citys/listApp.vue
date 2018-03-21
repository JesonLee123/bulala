<template>
	<div id="app">
		<div id="mask" class="mask" v-show="showMask" @touchmove="prevent($event)"></div>
		<div id="container">
			<header>
				<!-- <div class="icon"><img src="./assets/back.png" alt=""></div> -->
				<div class="cancel" style="float:right;float: right;font-size: 0.38rem;line-height: 1.33rem;margin-left: 0.15rem;" v-show="showCancle" @click="cancel">取消</div>
				<div class="text">
					<input type="text" placeholder="请输入城市名称（如北京/bj/beijing）" id="ipt" @focus="focus(searchCity)" @blur="blur(searchCity)" @input="search()" v-model="searchCity" :style="{width:iptWidth+'rem'}">
				</div>
			</header>
			<div style="height:1.33rem"></div>
			<ul class="textList">
				<li v-for="(item,index) in searchData" :key="index" @click="selectCity(item.name,$event,index)">{{item.name}}</li>					
			</ul>
			<section class="main" v-show="showMain">
				
				<div class="main-t">
					<div id="curCity">
						<h3>当前定位城市</h3>
						<ul class="list">
							<li class="curCity" @click="selectCity(obj.curPos,$event)" :class="{ active: className == 'curCity'}">{{obj.curPos}}</li>
						</ul>
					</div>
					<div id="hisCity">
						<h3>历史记录</h3>
						<ul class="list history">
							<li class="hisCity" v-for="(item,index) in obj.his" :key="index" @click="selectCity(item.name,$event,index)" :class="{ active: activeIndex == index && className == 'hisCity'}">{{item.name}}</li>
						</ul>
					</div>
					<div id="hotCity">
						<h3 >热门城市</h3>
						<ul class="list hot">
							<li class="hotCity" v-for="(item,index) in obj.topic" :key="index" @click="selectCity(item.name,$event,index)" :class="{ active: activeIndex == index && className == 'hotCity'}">{{item.name}}</li>
						</ul>
					</div>
				</div>
	
				<div class="main-b">
					<template v-for="(item,key,index) in obj.allCity" >
						<h2 :id="key" v-text="key" :key="index"></h2>
						<ul>
							<li v-for="(val,index) in item" :key="index" @click="selectCity(val.name,$event,index)">{{val.name}}</li>
						</ul>
					</template>	
				</div>
			</section>
			<div class="nav" v-show="showNav">
				<ul>
					<li><a href="#curCity">定位</a></li>
					<li><a href="#hisCity">历史</a></li>
					<li><a href="#hotCity">热门</a></li>
					<li><a href="#A">A</a></li>
					<li><a href="#B">B</a></li>
					<li><a href="#C">C</a></li>
					<li><a href="#D">D</a></li>
					<li><a href="#E">E</a></li>
					<li><a href="#F">F</a></li>
					<li><a href="#G">G</a></li>
					<li><a href="#H">H</a></li>
					<li><a href="#I">I</a></li>
					<li><a href="#J">J</a></li>
					<li><a href="#K">K</a></li>
					<li><a href="#L">L</a></li>
					<li><a href="#M">M</a></li>
					<li><a href="#N">N</a></li>
					<li><a href="#O">O</a></li>
					<li><a href="#P">P</a></li>
					<li><a href="#Q">Q</a></li>
					<li><a href="#R">R</a></li>
					<li><a href="#S">S</a></li>
					<li><a href="#T">T</a></li>
					<li><a href="#U">U</a></li>
					<li><a href="#V">V</a></li>
					<li><a href="#W">W</a></li>
					<li><a href="#X">X</a></li>
					<li><a href="#Y">Y</a></li>
					<li><a href="#Z">Z</a></li>
				</ul>
			</div>
		</div>
	</div>
</template>

<script>
import 'assets/js/rem.js'
export default {
  data() {
    return {
    	obj:{
            curPos: '南京',
            his: [
                {name:"上海",jianpin:"sh",pinyin:"shanghai"},
                {name: '南京',jianpin: 'nj',pinyin: 'nanjing'},
                {name: '北京','jianpin': 'bj','pinyin': 'beijing'}
            ],
            topic: [
                {name:"上海",jianpin:"sh",pinyin:"shanghai"},
                {name: '南京',jianpin: 'nj',pinyin: 'nanjing'},
                {name: '北京','jianpin': 'bj','pinyin': 'beijing'},
                {name:"上海",jianpin:"sh",pinyin:"shanghai"},
                {name: '南京',jianpin: 'nj',pinyin: 'nanjing'},
                {name: '北京','jianpin': 'bj','pinyin': 'beijing'},
                {name:"上海",jianpin:"sh",pinyin:"shanghai"},
                {name: '南京',jianpin: 'nj',pinyin: 'nanjing'},
                {name: '北京','jianpin': 'bj','pinyin': 'beijing'},
                {name:"上海",jianpin:"sh",pinyin:"shanghai"},
                {name: '南京',jianpin: 'nj',pinyin: 'nanjing'},
                {name: '北京','jianpin': 'bj','pinyin': 'beijing'},
                {name:"上海",jianpin:"sh",pinyin:"shanghai"},
                {name: '南京',jianpin: 'nj',pinyin: 'nanjing'},
                {name: '北京','jianpin': 'bj','pinyin': 'beijing'}
            ],
            allCity: {
                "A": [
                    {name: '鞍山','jianpin': 'as','pinyin': 'anshan'},
                    {name: '安阳','jianpin': 'ay','pinyin': 'anyang'},
                    {name: '安顺','jianpin': 'as','pinyin': 'anshun'},
                    {name: '安康','jianpin': 'ak','pinyin': 'ankang'},
                ],
                "B": [{name: '北京','jianpin': 'bj',pinyin: 'beijing'}],
                "C": [{name: '长春',jianpin: 'cc',pinyin: 'changchun'}],
                "D": [{name: '大连',jianpin: 'dl',pinyin: 'dalian'}],
			}
		},
		showMask:false,
		showMain:true,
		showNav:true,
		searchCity:"",
		searchData:[],
		activeIndex:0,
		className:'curCity',
		iptWidth:9.6,
		showCancle:false
    }
  },
 
  //相关操作事件
  methods: {
	selectCity(val,e,index){
		console.log(val)
		this.className = e.target.className;
		this.activeIndex = index;
	},
	getData(obj){
		this.obj = obj
	},
	//输入框聚焦
	focus(val){
		this.showCancle = true;
		this.iptWidth = 8.6
		if(val){
			this.showMask = false
		}else{
			this.showMask = true
		}
	},
	//失焦
	blur(val){
		if(val){
			this.showCancle = true;
			this.iptWidth = 8.6
		}else{
			this.showCancle = false;
			this.iptWidth = 9.6
		}
		this.showMask = false
	},
	//取消
	cancel(){
		this.searchCity = '';
		this.searchData = [];
		this.showMain = true;
		this.showNav = true;
		this.showCancle = false;
		this.iptWidth = 9.6
	},
	//输入框input事件
	search(){
		let self = this;
		self.showMask = false;
		self.showMain = false;
		self.showNav = false;
		let arr = [];
		let allCity = this.obj.allCity;
		let iptVal = this.searchCity;
        for(var key in allCity) {
            arr = arr.concat(allCity[key]);
		}
		this.searchData = arr.filter( function(item,index) {
			if(iptVal){
				self.showMask = false;
				self.showMain = false;
				self.showNav = false;
				let reg = new RegExp("^"+iptVal,'i');
				if(reg.test(item.name) || reg.test(item.jianpin) || reg.test(item.pinyin)) {
					return item;
				}
			}else{
				self.showMask = true;
				self.showMain = true;
				self.showNav = true;
				return;
			}
		})	
	},
	prevent(e){
		e.stopPropagation();
        e.preventDefault();
	}
  }
}
</script>

<style lang="less">
	*{
		margin:0;
		padding:0
	}
	body{font:12px  "宋体"; word-wrap:break-word;}
	a{
		text-decoration:none;
		color:#666
	}
	li{list-style:none;}
	input,textarea{outline:none;}
	// html{
	// 	font-size: 8.89vw;
	// }
   body{
       font-family: PingFangSC-Regular,"Open Sans","Helvetica Neue",Helvetica,Arial,STHeiti,"Microsoft Yahei",sans-serif;
       position:relative;
       -webkit-user-select: none;  /* Chrome all / Safari all /opera15+*/  
       -moz-user-select: none;     /* Firefox all */  
       -ms-user-select: none;      /* IE 10+ */  
       user-select: none; 
       -webkit-tap-highlight-color: rgba(255, 255, 255, 0); 
       -webkit-appearance:none; 
    }
    .mask {       
            position: absolute;
            top: 0px;
            filter: alpha(opacity=80); 
            background-color: #777;     
            z-index: 100; 
            left: 0px;     
            opacity:0.8; 
            -moz-opacity:0.8;  
			overflow:hidden;
			width:100%;
			height:100%   
        }    
    .active{border:0;background:#fece15}
   header{height:1.33rem;background:#fece15;position:fixed;top:0;left:0;width:100%;padding:0 0.45rem;box-sizing: border-box;z-index: 1000;}
   header .icon{float:left;width:0.72rem;height:1.33rem}
   header .icon img{display: block;width:100%;height:100%}
   header .text{float:right;}
   header .text input{padding:0.22rem 0.85rem;font-size: 0.38rem;height:0.84rem;margin-top:.24rem;border:0;border-radius: 0.42rem;color:#666;box-sizing: border-box;}
   .textList{padding-left:0.45rem;z-index:555;}
   .textList li{border-bottom:0.01rem solid #ddd;font-size: 0.40rem;line-height: 1.08rem;}
   .main .main-t{padding-left:0.45rem}
        h3{line-height: 1.08rem;font-size: .34rem;color:#999}
        .list{overflow: hidden;}
        .list li{width:3rem;height:.8rem;border:1px solid #ddd;border-radius: .4rem;font-size:.32rem;line-height: .8rem;color:#222;text-align: center;float:left;margin-right:0.24rem; }
        .history li{margin-bottom: 0.28rem}
        #hotCity{margin-top:-0.28rem}
        .hot{padding-bottom: 0.12rem}
        .hot li{margin-bottom: 0.28rem}
        .main-b{padding-right:1.2rem}
        .main-b h2{font-size:.3rem;line-height: .89rem;color:#222;background:#fcfcfc;border-top:0.01rem solid #ddd;
            border-bottom:0.01rem solid #ddd;padding-left:0.6rem}
        .main-b ul{
            padding-left: 0.45rem;
        }
        .main-b ul li{
            font-size: .38rem;
            line-height: 1.34rem;
            color:#222;
            padding-left:.15rem;
            border-bottom:0.01rem solid #ddd;
        }
        .main-b ul li:last-child{border:0}
    .nav{
        position: fixed;
		right: 0;
		bottom: 0;
		top: 0;
		margin: 0;
		text-align: center;
		display: flex;
		flex-direction: column;
		justify-content: center;
	}
    .nav ul{
        flex-direction: column;
        align-content: space-between;
    }
    .nav ul li{
		padding:0 0.24rem;
        font-size: 1.5vh; /*0.28rem;*/
        line-height: 2.8vh;/* .54rem;*/
        color:#666;
        text-align: center;
        user-select:none;
    }
</style>
