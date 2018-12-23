<template>
	<view>
		<view class="pr">
			<image src="../../static/img/bito_bg.jpg" class="w100 df_kj_dertxc" mode=""></image>

			<view class="sd_kh_detxr">
				<image src="../../static/img/qiu_bg.png" class="qiu_bg"></image>
				<view class="f_jh_ddf_ertx pr cen pt60 cf fz26">
					<text class="ljddrttxrt">30</text> /50
					<view class="mt20 cf fz26">
						今日目标
					</view>

				</view>

				<text class="fz26 cf dsf_jh_deet">题</text>

			</view>

		</view>
		<view class="pd pt15 pm20 fz24 z3 ln">
			<image src="../../static/img/df_a.png" class="time_dert" mode=""></image>
			<text class="cz ml5">学习计划执行周期：</text>
			<view class="ssd_kjh_ddf z9 fz24">
				2018年11月2日~ 2018年11月12日
			</view>
		</view>
		
		
		<view class="btm pd bgff pr">
			<image src="../../static/img/df_e.png" class="df_e_errt"></image>
			<view class="dx_row ds_jh_drrtxe fz28">
				<view class="dx_col_10">
					<image src="../../static/img/df_b.png" class="eeerxrt_de cz" mode=""></image>
					<text class="ml10 cz z3">11月2日</text>
				</view>
				<view class="dx_col_10">
					<text class="lser">正确25</text>
					<text class="red ml10">错误6</text>
				</view>
				
				<view class="dx_col_4">
					完成31题
				</view>
				
			</view>
			<view class="dx_row ds_jh_drrtxe fz28">
				<view class="dx_col_10">
					<image src="../../static/img/df_c.png" class="eeerxrt_de cz" mode=""></image>
					<text class="ml10 cz z3">11月2日</text>
				</view>
				<view class="dx_col_10">
					<text class="lser">正确25</text>
					<text class="red ml10">错误6</text>
				</view>
				
				<view class="dx_col_4">
					完成31题
				</view>
				
			</view>
			
			
			<view class="dx_row ds_jh_drrtxe fz28" v-for="sd in 20">
				<view class="dx_col_10">
					<image src="../../static/img/df_d.png" class="eeerxrt_de cz" mode=""></image>
					<text class="ml10 cz z3">11月2日</text>
				</view>
				<view class="dx_col_10">
					<text class="z9">待完成</text>
				</view>
				
				<view class="dx_col_4 z9">
					待完成
				</view>
				
			</view>
			
			
		</view>


	</view>
</template>
<script>
	export default {
		data() {
			return {}
		},
		components: {},
		methods: {},
		mounted() {},
	}
</script>
<style scoped>
	.df_kj_dertxc {
		height: 480upx;
	}

	.sd_kh_detxr {
		width: 258upx;
		height: 258upx;
		border-radius: 50%;
		position: absolute;
		left: 0;
		right: 0;
		margin: auto;
		bottom: 60upx;

	}

	.sd_kh_detxr .qiu_bg {
		position: absolute;
		left: 0;
		top: 0;
		width: 100%;
		height: 100%;
	}

	.ljddrttxrt {
		font-size: 80upx;
		color: #48fb09;
	}

	.dsf_jh_deet {
		position: absolute;
		bottom: 0;
		right: 0;
	}

	.time_dert {
		width: 28upx;
		height: 28upx;
		position: relative;
		top: 6upx;
	}

	.ssd_kjh_ddf {
		padding-left: 35upx;
	}
	.eeerxrt_de{
		width: 36upx;
		height: 36upx;
	}
	.ds_jh_drrtxe{
		line-height: 65upx;
		border-bottom: 1px dashed #D8D8D8; 
	}
	.df_e_errt{
		width: 28upx;
		height: 15upx;
		position: absolute;
		left: 60upx;
		top: -13upx;
	}
</style>
