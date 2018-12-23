<template>
	<view>
		<view class="lunbo_tusd">
			<lunbotu :imgUrls="imgUrls"></lunbotu>
		</view>

		<view class="pd pt20 pm20">
			<view class="sd_dfdfd dx_row ov">
				<view class="dx_col_12 df_kj_detc" :class="sd.cls" v-for="sd in sd_dsdf" @click="tab_sdf(sd)">
					{{sd.name}}
				</view>
			</view>
		</view>

		<view class="pd mt20 dx_row f_df_dff_row">
			<view class="dx_col_12 sd_hj_deerxc mb20">
				<image src="../../static/img/ssd_sdf_a.png"></image>
			</view>
			<view class="dx_col_12 sd_hj_deerxc mb20">
				<image src="../../static/img/ssd_sdf_b.png"></image>
			</view>
			<view class="dx_col_12 sd_hj_deerxc mb20">
				<image src="../../static/img/ssd_sdf_c.png"></image>
			</view>

			<view class="dx_col_12 sd_hj_deerxc mb20">
				<image src="../../static/img/ssd_sdf_d.png"></image>
			</view>

		</view>

		<view class="pd">
			<view class="dx_row pt20 pm20 bgff bk yj4 cen fz30 z6 ">
				<view class="dx_col_12 brm">
					<image src="../../static/img/ssdas_a.png" class="sd_jh_fertx cz"></image>
					<text class="cz">我的错题</text>
				</view>
				<view class="dx_col_12 ">
					<image src="../../static/img/ssdas_b.png" class="sd_jh_fertx cz ab"></image>
					<text class="cz">我的收藏</text>
				</view>
			</view>


			<view class="mt20">
				<image src="../../static/img/monikaos.png" class="w100" mode="widthFix"></image>
			</view>
		</view>
	</view>
</template>
<script>
	import lunbotu from "@/components/lunbotu.vue"
	export default {
		data() {
			return {
				"imgUrls": [
					"/static/img/lunbotu_b.jpg",
					"/static/img/lunbotu_b.jpg",
					"/static/img/lunbotu_b.jpg"
				],
				sd_dsdf: [{
					name: "线上平台竞赛",
					cls: "act"
				}, {
					name: "线下平台竞赛",
					cls: ""
				}]
			}
		},
		components: {
			lunbotu
		},
		methods: {
			tab_sdf(sd){
				this.sd_dsdf.map(a=>{
					a.cls=""
				})
				sd.cls="act"
			}
		},
		mounted() {},
	}
</script>
<style scoped>
	.lunbo_tusd {
		height: 245upx;
	}

	.sd_dfdfd {
		border-radius: 72upx;
		line-height: 72upx;
		text-align: center;
		border: 1px solid #4da9ff;
	}

	.df_kj_detc {
		color: #4da9ff;
		font-size: 30upx;
		text-align: center;

	}

	.df_kj_detc.act {
		background: #4da9ff;
		color: #fff;
	}

	.sd_hj_deerxc image {
		width: 100%;
		height: 154upx;
	}

	.f_df_dff_row {}

	.sd_hj_deerxc {
		padding-left: 8upx;
		padding-right: 8upx;
	}

	.sd_jh_fertx {
		width: 36upx;
		height: 40upx;
		margin-right: 10upx;
	}

	.sd_jh_fertx.ab {
		width: 42upx;
		height: 40upx;
	}
</style>
