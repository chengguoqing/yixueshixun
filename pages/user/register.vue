<!-- 登录 -->
<template>
	<view>
		<image src="../../static/img/logo_top.jpg" class="bg_derertt"></image>
		<view class="pr pt100">
			<view class="cen">
				<image src="../../static/img/logo.png" class="ogo_klkjeer"></image>
			</view>

			<view class="yj4 bgff bk sdf_jh_r_drrt ov mt60">

				<view class="dx_row">
					<view class="dx_col_12 df_jh_ddrtt" :class="sd.cls" v-for="(sd,idx) in tab_sd" @click="shddf_sd(sd,idx)">
						{{sd.name}}
					</view>
				</view>

				<!-- 手机登陆 -->
				<view class="sd_kj_box pt30 pm50" v-if="yuyddf==0">
					<view class="sdii_rows pr">
						<image src="../../static/img/phone.png" class="phone_der" mode=""></image>
						<input type="text" placeholder="请输入手机号" class="fz28" v-model="user_phone" />
					</view>

					<view class="sdii_rows pr">
						<image src="../../static/img/dunpai.png" class="phone_der ab" mode=""></image>
						<input type="text" value="" placeholder="请输入验证码" class="fz28" />
						<view class="dd_jh_sdf pd  fz28" @click="huoqu_ert">
							<text v-if="daojishi==60">获取验证码</text>
							<text v-else class="z9">{{daojishi}}秒后重送</text>
						</view>
					</view>
					<view class="z9 fz26 tr sd_jh_dertxdfr">

					</view>
					<view class="delj_ddf fz36" @click="denglu">
						登 录
					</view>

				</view>

				<!-- 账号登陆 -->
				<view class="sd_kj_box pt30 pm50" v-if="yuyddf==1">
					<view class="sdii_rows pr">
						<image src="../../static/img/user_icon.png" class="phone_der ac" mode=""></image>
						<input type="text" value="" placeholder="手机号/用户名" class="fz28" />
					</view>

					<view class="sdii_rows pr">
						<image src="../../static/img/mima.png" class="phone_der ad" mode=""></image>
						<input type="text" value="" placeholder="请输入密码" class="fz28" />

					</view>
					<view class="z9 fz26 tr sd_jh_dertxdfr">
						忘记密码？
					</view>
					<view class="delj_ddf fz36" @click="denglu">
						登 录
					</view>

				</view>


			</view>

			<view class="cen fz26 ls pt30">
				注册账号
			</view>



		</view>


		<view class="mt80 pd">
			<view class="sd_kjrtdee">
				<text class="zb fz28">合作账号登陆</text>
			</view>

			<view class="box cen mt40 df_crttxc">
				<view class="box_a">
					<image src="../../static/img/deng_a.png" class="sd_kjhj_deet"></image>
					<view class="fz24 z6 mt20">
						微信
					</view>
				</view>

				<view class="box_a">
					<image src="../../static/img/deng_b.png" class="sd_kjhj_deet"></image>
					<view class="fz24 z6 mt20">
						微博
					</view>
				</view>


				<view class="box_a">
					<image src="../../static/img/deng_c.png" class="sd_kjhj_deet"></image>
					<view class="fz24 z6 mt20">
						QQ
					</view>
				</view>


			</view>



		</view>

		<navigator url="/pages/user/privacy_policy" class="pt30 fz26 z9 cen dsf_xdertx pm30">
			*注册/登陆即表示你已阅读，并同意<text class="ls f_b">《用户协议》</text>
		</navigator>

	</view>
</template>
<script>
	export default {
		data() {
			return {
				tab_sd: [{
						name: "手机登陆",
						cls: "act"
					},
					{
						name: "账号登陆",
						cls: ""
					}
				],
				user_phone: "", //电话号码
				yuyddf: 0, //0手机登陆 1账号登陆
				daojishi: 60
			}
		},
		components: {},
		methods: {
			denglu() { //登录按钮触发

				uni.showToast({
					title: "登录成功！",
					mask:true,
					duration: 3000
				})
				setTimeout(function() {
					uni.navigateTo({
						url: '/pages/user/basic_information'
					});
				}, 3000)

			},
			huoqu_ert() { //获取验证码按钮点击
				if (this.daojishi != 60) {
					return
				}
				if (!this.yanza.phone(this.user_phone)) {
					uni.showToast({
						title: "手机号码输入错误",
						icon: "none"
					})
					return
				}
				let th = this
					--this.daojishi
				var timj_dr = setInterval(function() {
					if (--th.daojishi < 0) {
						th.daojishi = 60
						clearTimeout(timj_dr)
					}
				}, 1000)

			},
			shddf_sd(sd, idx) {
				this.tab_sd.map(a => {
					a.cls = ""
				})
				sd.cls = "act"
				this.yuyddf = idx
			}
		},
		mounted() {},
	}
</script>
<style scoped>
	.dsf_xdertx {
		background: #F4F4F4 !important;
	}

	.bg_derertt {
		position: absolute;
		width: 100%;
		height: 578upx;
	}

	.ogo_klkjeer {
		width: 369upx;
		height: 229upx;
	}

	.sdf_jh_r_drrt {
		width: 620upx;
		margin: auto;
	}

	.df_jh_ddrtt {
		height: 110upx;
		line-height: 110upx;
		text-align: center;
		color: #4da9ff;
		font-size: 30upx;
		background: #F5F5F5;
	}

	.df_jh_ddrtt.act {
		background: #fff;
	}

	.sd_kj_box {
		width: 500upx;
		margin: auto;
	}

	.sdii_rows {
		height: 100upx;
		line-height: 100upx;
		padding-top: 26upx;
		border-bottom: 1px solid #BDBDBD;
		position: relative;
		overflow: hidden;
	}

	.sdii_rows input {
		padding-left: 90upx !important;
	}

	.phone_der {
		width: 26upx;
		height: 43upx;
		position: absolute;
		left: 10upx;
		top: 30upx;
	}

	.phone_der.ab {
		width: 38upx;
		height: 42upx;
	}

	.phone_der.ac {
		width: 40upx;
		height: 40upx;
	}

	.phone_der.ad {
		width: 32upx;
		height: 47upx;
	}

	.dd_jh_sdf {
		background: #fff;
		position: absolute;
		right: 0;
		top: 0;
		height: 100upx;
		color: #4da9ff;

		z-index: 1000;
	}

	.delj_ddf {
		height: 80upx;
		line-height: 80upx;
		text-align: center;
		background: linear-gradient(to bottom, #81C2FE, #3689DB);
		border-radius: 80upx;
		box-shadow: 0 0px 20upx rgba(54, 137, 219, .5);
		color: #fff;
	}

	.sd_jh_dertxdfr {
		line-height: 60upx;
		height: 60upx;
	}

	.sd_kjrtdee {
		border-top: 1px solid #E1E1E1;
		text-align: center;
	}

	.sd_kjrtdee text {
		background: #f4f4f4;
		padding: 10px;
		position: relative;
		top: -20upx;
	}

	.sd_kjhj_deet {
		width: 62upx;
		height: 62upx;
	}

	.df_crttxc {
		width: 480upx;
		margin: auto;
	}
</style>
