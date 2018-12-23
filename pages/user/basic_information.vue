<!-- 完善基本信息 -->
<template>
	<view class="pt50">
		<view class="cen pm30">
			<image :src="paSdr" class="yj user_iconr" @click="pai_sdf"></image>
			<view class="ls fz28 mt20" @click="pai_sdf">
				上传头像
			</view>
			<view class="fz28 z6 mt10">
				18688888886
			</view>
		</view>

		<view class="sd_jh_df bgff">
			<view class="sdii_rows pr">
				<image src="../../static/img/dsf_a.png" class="phone_der" mode=""></image>
				<input type="text" placeholder="中文姓名" class="fz28" />
			</view>

			<view class="sdii_rows pr">
				<image src="../../static/img/dsf_b.png" class="phone_der bb" mode=""></image>
				<input type="text" placeholder="性别" class="fz28" />
			</view>
			<view class="sdii_rows pr">
				<image src="../../static/img/dsf_c.png" class="phone_der bc" mode=""></image>
				<input type="text" placeholder="院校" class="fz28" />
			</view>
			<view class="sdii_rows pr">
				<image src="../../static/img/dsf_d.png" class="phone_der bd" mode=""></image>
				<input type="text" placeholder="班级" class="fz28" />
			</view>
			<view class="sdii_rows pr">
				<image src="../../static/img/dsf_e.png" class="phone_der be" mode=""></image>
				<input type="text" placeholder="学号" class="fz28" />
			</view>
			<view class="sdii_rows pr">
				<image src="../../static/img/dsf_f.png" class="phone_der bf" mode=""></image>
				<input type="text" placeholder="所在地区" class="fz28" />
			</view>
			
			<view class="sdii_rows pr ab">
				<image src="../../static/img/dsf_g.png" class="phone_der bg" mode=""></image>
				<input type="text" placeholder="邮箱" class="fz28" />
			</view>
		

		</view>
		
		<view class="sd_jh_df mt50">
			<view class="sd_jh_drert_btn fz30 cf" @click="tijiao_r">
				提 交
			</view>
			
			<navigator url="/pages/user/privacy_policy" class="pt30 fz26 z9 cen dsf_xdertx pm30">
				*点击提交代表您同意<text class="ls f_b">《新用户注册协议》</text>
			</navigator>
		</view>



	</view>
</template>
<script>
	export default {
		data() {
			return {
				paSdr:"../../static/img/user_icon_e.png"
			}
		},
		components: {},
		methods: {
			tijiao_r(){
				uni.showToast({
					title: "提交成功！",
					mask:true,
					duration: 3000
				})
				setTimeout(function() {
					uni.reLaunch({
						url: '/pages/index'
					});
				}, 3000)
			},
			pai_sdf(){
				let th=this
				this.yjpz(function(data){
					th.paSdr=data
				})
			}
		},
		mounted() {},
	}
</script>
<style scoped>
	.user_iconr {
		width: 163upx;
		height: 163upx;
	}

	.sd_jh_df {
		padding-left: 60upx;
		padding-right: 60upx;
	}


	.sdii_rows {
		height: 100upx;
		line-height: 100upx;
		padding-top: 26upx;
		border-bottom: 1px solid #E1E1E1;
		position: relative;
		overflow: hidden;
	}
	.sdii_rows.ab{
		border-bottom: 0px;
	}

	.sdii_rows input {
		padding-left: 80upx !important;
	}

	.phone_der {
		width: 40upx;
		height: 39upx;
		position: absolute;
		left: 10upx;
		top: 30upx;
	}
	.phone_der.be{
		height: 30upx;
		top: 39upx;
	}
	.phone_der.bg{
		width: 35upx;
		height: 28upx;
		top: 41upx;
	}
	.sd_jh_drert_btn{
		line-height: 72upx;
		height: 72upx;
		text-align: center;
		border-radius: 72upx;
		background: #4FA9FF;
	}
	.dsf_xdertx {
			background: #F4F4F4 !important;
		}
	
</style>
