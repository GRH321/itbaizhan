<template>
	<view class="course-nav-container">
		<view class="course-nav-info" v-for="(item,index) in list" :key="index" @click="courseClickItem(item.id,item.course)">
		<text class="icon iconfont course-info-icon" :class="item.icon"></text>	
		<view class="course-info-text">{{item.text}}</view>
			
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list:[]
			}
		},
		mounted(){
			uni.request({
				url:"http://html5.bjsxt.cn/api/index/nav",
				success:res =>{
					this.list = res.data.data
				}
			})
		},
		methods:{
			courseClickItem(id,course){
				uni.navigateTo({
					url: '/pages/course/courseIntroduce?id='+id+"&course="+course
				});
			}
		}
	}
</script>

<style lang="scss">
	.course-nav-container{
		/* 盒子模型 */
		display: flex;  
		/* 水平方向 */
		flex-direction: row;
		/* 左右空袭 */
		padding: 15px 10px;
		/* 必要的时候换行 */
		flex-wrap: wrap;
		.course-nav-info{
			width: 20%;
			flex-wrap: wrap;
			flex-direction: row;
			/* 居中 */
			text-align: center;
			margin-bottom: 15px;
			.course-info-icon{
				font-size: 30px;
			}
			.course-info-text{
				width: 100%;
				font-size: 13px;
				margin-top: 10px;
				// 省略效果
				white-space: nowrap;
				text-overflow: ellipsis;
				overflow: hidden;
			}
			.icon-java{
				color: #2a83fe;
			}
			.icon-icon--{
				color: #fd6012;
			}
			.icon-houduan{
				color: #fd4d72;
			}
			.icon-zidonghua{
				color: #00b478;
			}
			.icon-shujufenxi{
				color: #fe391f;
			}
			.icon-h{
				color: #00b478;
			}
			.icon-dashuju{
				color: #2a83fe;
			}
			.icon-rengongzhineng{
				color: #fe391f;
			}
			.icon-weifuwu{
				color: #fd3761;
			}
			.icon-zuzhijiagou{
				color: #2b91e2;
			}
			.icon-ruanjianceshi{
				color: #00b478;
			}
			.icon-huatong{
				color: #fea917;
			}
			.icon-bianchengshibaobiao_icon{
				color: #2a83fe;
			}
			.icon-chuangye1{
				color: #00b478;
			}
			.icon-jianmo{
				color: #ff0036;
			}
			
		}
	}
	
	

</style>
