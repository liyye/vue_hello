<template>
    <div class="login-container">
        <el-form ref="form" :model="form" label-width="80px" class="login-form">
            <h2 class="login-title">请出示山门令牌</h2>
            <el-form-item label="令牌号">
                <el-input v-model="form.username" clearable></el-input>
            </el-form-item>
            <el-form-item label="令牌密码">
                <el-input v-model="form.password" type="password" show-password></el-input>
            </el-form-item>

            <el-form-item>
                <el-button type="primary" @click="onSubmit" icon="el-icon-loading">登录</el-button>
                <el-button type="primary" plain @click="registered">注册</el-button>
            </el-form-item>
        </el-form>
    </div>
</template>
<script>
    export default {
        name: 'Login',
        props: {
            msg: String,
        },
        data() {//页面定义字段
            return {
                form: {
                    username: "",
                    password: ""
                },
                items: [
                    { message: 'Foo' },
                    { message: 'Bar' }
                ],
            }
        },
        mounted() {//页面加载

        },
        methods: {//页面方法
            onSubmit() {
                if (!this.form.username || !this.form.password) {
                    alert("你的令牌呢？");
                } else {
                    this.$router.push({ name: "Home", query: { msg: '欢迎来到东临宗' } });//利用路由跳转页面，path为你定义的路由配置中要跳转页面的path
                    //const new1 = this.$router.resolve({ name: "Home", query: { msg: '欢迎来到东临宗' } });
                    //window.open(new1.href, '_blank')
                }
            }
        }
    }
</script>

<style acoped>
    .login-form {
        width: 350px;
        margin: 160px auto; /* 上下间距160px，左右自动居中*/
        background-color: rgb(255, 255, 255, 0.8); /* 透明背景色 */
        padding: 30px;
        border-radius: 20px; /* 圆角 */
    }

    /* 背景 */
    .login-container {
        position: absolute;
        width: 100%;
        height: 100%;
        background: url("../assets/syc.jpg");
    }

    /* 标题 */
    .login-title {
        color: #303133;
        text-align: center;
    }
</style>
