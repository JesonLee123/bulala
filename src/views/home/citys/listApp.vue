<template>
	<div id="app">
		<div id="mask" class="mask" v-show="showMask" @touchmove="prevent($event)"></div>
		<div id="container">
			<header>
				<div class="back-icon"><img src="" alt=""></div>
				<div class="cancel" v-show="showCancle" @click="cancel">取消</div>
				<div class="text">
					<div class="search-icon"><img src="./assets/ticket_query_search.png" alt=""></div>
					<div class="clean-icon" v-show="showClean" @click="clean()"><img src="./assets/ticket_query_clean.png" alt=""></div>
					<input type="text" placeholder="请输入城市名称（如北京/bj/beijing）" id="ipt" @focus="focus(searchCity)" @blur="blur(searchCity)" @input="search()" v-model="searchCity" :style="{width:iptWidth+'rem'}">
				</div>
			</header>
			<div style="height:0.44rem"></div>
			<ul class="textList">
				<li v-for="(item,index) in searchData" :key="index" @click="selectCity(item.name,$event,index)">
					<span>城市</span>
					<span>{{item.name}}</span>
					<span>中国&nbsp;{{item.jianpin}}</span>
				</li>					
			</ul>
			<section class="main" v-show="showMain">
				<div class="main-t">
					<div id="curCity">
						<h3>当前定位城市</h3>
						<ul class="list">
							<li class="curCity" @click="selectCity(obj.curPos,$event)" :class="{ active: className.includes('curCity')||className.includes('img')}">
								<img src="./assets/ticket_query_location.png" alt="" class="img">
								&nbsp;&nbsp;&nbsp;{{obj.curPos}}
							</li>
						</ul>
					</div>
					<div id="hisCity">
						<h3>历史记录</h3>
						<ul class="list history">
							<li class="hisCity" v-for="(item,index) in obj.his" :key="index" @click="selectCity(item.name,$event,index)" :class="{ active: activeIndex == index && className.includes('hisCity')}">{{item.name}}</li>
						</ul>
					</div>
					<div id="hotCity">
						<h3 >热门城市</h3>
						<ul class="list hot">
							<li class="hotCity" v-for="(item,index) in obj.topic" :key="index" @click="selectCity(item.name,$event,index)" :class="{ active: activeIndex == index && className.includes('hotCity')}">{{item.name}}</li>
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
					<li class="font"><a href="#curCity">定位</a></li>
					<li class="font"><a href="#hisCity">历史</a></li>
					<li class="font"><a href="#hotCity">热门</a></li>
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
			<div class="nothing" v-show="showNothing">
				<div class="pic">
					<img src="./assets/ticket_query_nothing.png" alt="">
				</div>
				<p>未搜索到相关城市</p>
			</div>
		</div>
	</div>
</template>

<script>
import 'assets/js/rem.js';
import 'assets/css/common.css'
export default {
  data() {
    return {
    	obj:{
            curPos: '南京',
            his: [
                {name:"上海",jianpin:"sh",pinyin:"shanghai"},
                {name: '南京',jianpin: 'nj',pinyin: 'nanjing'},
                {name: '北京','jianpin': 'bj','pinyin': 'beijing'},
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
		showCancle:false,
		showClean:false,
		showNothing:false,
		searchCity:"",
		searchData:[],
		activeIndex:0,
		className:'curCity',
		iptWidth:3.21,
    }
  },
 
  //相关操作事件
  methods: {
	selectCity(val,e,index){
		console.log(val)
		index =index||0;
		this.className = e.target.className;
		this.activeIndex = index;
		console.log(this.className,index)
	},
	getData(obj){
		this.obj = obj
	},
	//输入框聚焦
	focus(val){
		this.showCancle = true;
		this.iptWidth = 2.8
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
			this.iptWidth = 2.8
		}else{
			this.showCancle = false;
			this.iptWidth = 3.21
		}
		this.showMask = false
	},
	//清除
	clean(){
		this.searchCity='';
		this.searchData=[];
		this.showMask = true;
		this.showMain = true;
		this.showNav = true;
		this.showClean = false;
	},
	//取消
	cancel(){
		this.searchCity = '';
		this.searchData = [];
		this.showMain = true;
		this.showNav = true;
		this.showCancle = false;
		this.showClean = false;
		this.showMask=false;
		this.iptWidth = 3.21
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
		self.searchData = arr.filter( function(item,index) {
			if(iptVal){
				self.showMask = false;
				self.showMain = false;
				self.showNav = false;
				self.showClean = true;
				let reg = new RegExp("^"+iptVal,'i');
				if(reg.test(item.name) || reg.test(item.jianpin) || reg.test(item.pinyin)) {
					return item;
				}else{
					return;
				}
			}else{
				self.showMask = true;
				self.showMain = true;
				self.showNav = true;
				self.showClean = false;
				self.showNothing = false;								
				return;
			}
		})
		console.log(self.searchData)
		if(self.searchData.length!=0)	{
			self.showNothing = false;
		}else{
			self.showNothing = true;
		}
	},
	prevent(e){
		e.stopPropagation();
        e.preventDefault();
	}
  }
}
</script>

<style lang="less" scoped>
    .mask {       
		position: absolute;
		top: 0;
		filter: alpha(opacity=80); 
		background-color: #777;     
		z-index: 100; 
		left: 0;     
		opacity:0.8; 
		-moz-opacity:0.8;  
		overflow:hidden;
		width:100%;
		height:100%   
    }    
    header{
	   height:0.44rem;
	   background-image: linear-gradient(-90deg, #FCE105 0%, #FECD15 100%);
	   position:fixed;
	   top:0;
	   left:0;
	   width:100%;
	   padding:0.08rem 0.15rem;
	   box-sizing: border-box;
	   z-index: 1000;
	   .back-icon{
		   float:left;
		   width:0.2rem;
		   height:0.44rem;
		   padding:0.05rem 0;
		   box-sizing: border-box;
		   img{
			   width:0.08rem;
			   height:0.18rem;
		   }
		}
		.cancel{
			font-family: PingFangSC-Regular;
			font-size: 0.14rem;
			color: #222222;
			letter-spacing: 0;
			float:right;
			font-size: 0.14rem;
			line-height: 0.28rem;
			margin-left: 0.14rem;
		}
		.text{
			float:right;
			position: relative;
			.search-icon{
				position:absolute;
				top:0.05rem;
				left:0.08rem;
				img{
					width:0.14rem;
					height:0.14rem;
				}
			}
			.clean-icon{
				position: absolute;
				top:0.06rem;
				left:2.56rem;
				img{
					width:.12rem;
					height:.12rem;
				}
			}
			input{
				background:#fff;
				padding:0.08rem 0.27rem;
				height:0.28rem;
				border:0;
				border-radius: 1rem;
				box-sizing: border-box;
			}
			::-webkit-input-placeholder{
				color: #CCCCCC;
				letter-spacing: 0;
				font-size: 0.12rem;
			}
		}
	}
   .textList{
	   padding-left:0.15rem;
	   li{
		   	font-family: PingFangSC-Regular;
			font-size: .14rem;
			color: #101010;
			letter-spacing: 0;
			line-height: 0.4rem;
			border-bottom:0.01rem solid #ddd;
			span:nth-child(1){
				display:inline-block;
				width:0.3rem;
				height:.15rem;
				border-radius:1rem;
				font-size:0.1rem;
				line-height:0.15rem;
				text-align:center;
				color:#222;
				background:#FECD15
			}
			span:nth-child(3){
				color:#999;
				font-size:0.12rem;

			}
		}
	}
   .main {
	   	.main-t{
		   	padding-left:0.15rem;
		  	h3{
				font-family: PingFangSC-Regular;
				line-height: .38rem;
				font-size: .12rem;
				color:#999;
				font-weight: 500;
			}
			.list{
				overflow: hidden;
				.curCity{
					position: relative;
					img{
						position:absolute;
						width:0.09rem;
						height:0.12rem;
						left:0.31rem;
						top:0.07rem;
					}
					span{
						margin-left:0.08rem;
					}
				}
				li{
					width:1rem;
					height:.27rem;
					border:0.01rem solid #ddd;
					border-radius: 1rem;
					font-size:.12rem;
					line-height: 0.27rem;
					color:#222;
					text-align: center;
					float:left;
					margin-right:0.09rem;
					box-sizing: border-box;
				}
				li.active{
					border:0;
					background:#FECD15;
				}
			}
			.history li{margin-bottom: 0.09rem}
			#hotCity{margin-top:-0.09rem}
			.hot{padding-bottom: 0.04rem}
			.hot li{margin-bottom: 0.09rem}
		}
		.main-b{
			width:3.32rem;
			h2{
				font-family: SFNSText;
				font-size: 0.14rem;
				color: #222222;
				line-height: .3rem;
				background:#fcfcfc;
				border-top:0.01rem solid #ddd;
				border-bottom:0.01rem solid #ddd;
				padding-left:0.2rem;
				font-weight: 500;				
			}
			ul{
				padding-left: 0.15rem;
				li{
					padding-left:0.05rem;
					line-height: 0.45rem;
					border-bottom:0.01rem solid #ddd;
					font-family: PingFangSC-Light;
					font-size: .14rem;
					color: #222222;
				}
				li:last-child{border:0}
			}
		}
   }   
    .nav{
        position: fixed;
		// top: 0.79rem;
		// right: 0.07rem;
		right: 0;
		bottom: 0;
		top: 0;
		margin: 0;
		text-align: center;
		display: flex;
		flex-direction: column;
		justify-content: center;
		ul{
			display: flex;
			flex-direction: column;
			align-content: space-between;
			li{
				font-family: PingFangSC-Medium;
				padding:0 0.08rem;
				// font-size: 0.1rem;
				font-size: 1.5vh;
				// line-height:0.18rem; 
				line-height:2.8vh;
				color:#666;
				text-align: center;
				user-select:none;
			}
			li.font{
				font-family: PingFangSC-Regular;
			}
		}
	}
	.nothing{
		width:1.28rem;
		margin:1.11rem auto;
		.pic{
			img{
				width:1.05rem;
				height:1.05rem;
			}
		}
		p{
			margin-top: .18rem;
			font-family: PingFangSC-Regular;
			font-size: 0.16rem;
			color: #999999;
		}
	}
</style>
