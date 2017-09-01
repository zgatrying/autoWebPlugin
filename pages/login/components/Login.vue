<template>
<div class="login">
    <img class="logo" src="./assets/images/logo.jpg" alt="杭州佰凌智能">
		<el-row>
			<el-col>
				<el-form :model="form" ref="form">
					<el-form-item label="登录类型" :label-width="formLabelWidth">
						<el-radio-group v-model="accountType">
							<el-radio :label="0">权限管理员</el-radio>
							<el-radio :label="1">工程管理员</el-radio>
							<el-radio :label="2">超级账号</el-radio>
						</el-radio-group>
					</el-form-item>
					<el-form-item label="账号" :label-width="formLabelWidth" prop="account" :rules="{ required: true, message: '请输入账号', trigger: 'blur' }">
						<el-input ref="account" auto-complete="on" :autofocus="true" v-model="form.account" placeholder="请输入账号"></el-input>
					</el-form-item>
					<el-form-item label="密码" :label-width="formLabelWidth" prop="password" :rules="{ required: true, message: '请输入密码', trigger: 'blur' }">
						<el-input ref="password" type="password" v-model="form.password" placeholder="请输入密码"></el-input>
					</el-form-item>
					<el-form-item style="text-align: center;">
						<el-button type="primary" @click="handleSubmit" style="width: 50%;">登录</el-button>
					</el-form-item>
				</el-form>
			</el-col>
		</el-row>
</div>
</template>

<script>
import md5 from 'md5';
// import {superAccountActionLogin} from './util/api';
export default {
	mounted() {
		let user = localStorage.getItem('account');
		if (user !== null) {
				user = JSON.parse(user);
				this.form.account = user.account;
		}
		document.addEventListener('keydown', e => {
			if(e.key === 'Enter' || e.keyCode === 13) {
				this.handleSubmit();
			}
		});
	},
	data() {
		return {
			form: {
				account: '',
				password: '',
			},
			accountType: 2,
			formLabelWidth: '100px'
		}
	},
	methods: {
		handleSubmit() {
			this.$refs.form.validate(valid => {
				if(valid) {
					this.handleLogin();
				} else {
					return false;
				}
			})
		},
		handleLogin() {
			let data = {
				account: this.form.account,
				password: md5(this.form.password),
			};
			// superAccountActionLogin(data)
			// .then(res => {
			// 	if(res.errorcode === 0) {
			// 		var saveAccount = Object.assign({}, res.data.user, {account: this.form.account});
			// 		localStorage.setItem('account', JSON.stringify(saveAccount));
			// 		window.location.href = 'list.html';
			// 	} else {
			// 		this.$message.warning('用户名或密码错误');
			// 	}
			// })
			// .catch(() => {
			// 	this.$message({
			// 		type: 'error',
			// 		message: '请求失败',
			// 		showClose: true,
			// 	});
			// })
		}
	}
}
</script>

<style lang="sass">
	.login {
		width: 600px;
		margin: 0 auto;
		padding-top: 50px;
		img.logo{
			display: block;
			margin: 0 auto;
			margin-bottom: 12px;
		}
	}
</style>