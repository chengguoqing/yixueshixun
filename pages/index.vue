<template>
	<view>

		<view class="lunbo_tusd">
			<lunbotu :imgUrls="imgUrls"></lunbotu>
		</view>

		<view class="mt20 bgff df_h_drert">
			<tab_qh :sd_dfg="sd_dfg" :is_sdf="1"></tab_qh>
		</view>

		<view class="sd_jh_ddf bgff">

			<view class="sd_jh_drrx dx_row pt20 pm20 bbm pd" v-for="(sd,idx) in 10">
				<image src="../static/img/fenm.jpg" class="femghm_sdet"></image>
				<view class="ov pl20">
					<view class="fz30 z3 dian">
						<text class="yj dainsd_dert cz"></text>
						<text class="cz ml5">商务英语练考赛一体化平台</text>
					</view>
					<view class="fz24 z9 dian pl20 mt10">
						多种习题模式，海量题型，专注知识技能训练。
					</view>
					<view class="mt10 z9 fz24 pr">
						<view class="f_b sd_h_Deerttx">


							<icon class="dx icon-yanjing fz24 "></icon> <text class="ml5">15230</text>
						</view>

						<icon class="dx icon-dianzan fz24 "></icon> <text class="ml5">88</text>

						<view class="sd_jh_derrxre  fz22" :class="idx%2==0?'act':''">
							立即体验
						</view>

					</view>


				</view>

			</view>

		</view>

	</view>
</template>
<script>
	import lunbotu from "../components/lunbotu.vue"
	import tab_qh from "../components/tab_qh.vue"

	export default {
		data() {
			return {
				"imgUrls": [
					"/static/img/lunbotu.jpg",
					"/static/img/lunbotu.jpg",
					"/static/img/lunbotu.jpg"
				],
				sd_dfg: [{
					name: "商务英语系列",
					cls: "act"
				}, {
					name: "商务日语系列",
					cls: ""
				}, {
					name: "连锁经营系列",
					cls: ""
				}]
			}
		},
		components: {
			lunbotu,
			tab_qh
		},
		methods: {},
		mounted() {},
	}
</script>
<style scoped>
	.lunbo_tusd {
		height: 245upx;
	}

	.df_h_drert {
		position: sticky;
		left: 0;
		top: 0;
		z-index: 1000;
	}

	.femghm_sdet {
		width: 180upx;
		height: 120upx;
		float: left;
	}

	.dainsd_dert {
		width: 10upx;
		height: 10upx;
		background: #000;
		display: inline-block;
	}

	.sd_h_Deerttx {
		width: 180upx;
	}

	.sd_jh_derrxre {
		background: #D6D6D6;
		color: #fff;
		width: 112upx;
		height: 36upx;
		text-align: center;
		line-height: 40upx;
		border-radius: 36upx;
		position: absolute;
		right: 0;
		top: 20upx;

	}


	.sd_jh_derrxre.act {
		background: #4FA9FF;
	}
</style>
