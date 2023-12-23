<script setup>
import { User, Lock } from '@element-plus/icons-vue'
import { ref } from 'vue'
//控制注册与登录表单的显示， 默认显示注册
const isRegister = ref(false)
//Define the user register Data Model
const registeData = ref({
    username:'',
    password:'',
    repassword:''
})
</script>

<template>
    <el-row class="login-page">
        <el-col :span="12" class="bg"></el-col>
        <el-col :span="6" :offset="3" class="form">
            <!-- 注册表单 -->
            <el-form ref="form" size="large" autocomplete="off" v-if="isRegister" :model="registeData">
                <el-form-item>
                    <h1>Sign Up</h1>
                </el-form-item>
                <el-form-item>
                    <el-input :prefix-icon="User" placeholder="Username" v-model="registeData.username"></el-input>
                </el-form-item>
                <el-form-item>
                    <el-input :prefix-icon="Lock" type="password" placeholder="Password" v-model="registeData.password"></el-input>
                </el-form-item>
                <el-form-item>
                    <el-input :prefix-icon="Lock" type="password" placeholder="Password Again" v-model="registeData.repassword"></el-input>
                </el-form-item>
                <!-- 注册按钮 -->
                <el-form-item>
                    <el-button class="button" type="primary" auto-insert-space>
                        Sign Up
                    </el-button>
                </el-form-item>
                <el-form-item class="flex">
                    <el-link type="info" :underline="false" @click="isRegister = false">
                        ← back
                    </el-link>
                </el-form-item>
            </el-form>
            <!-- 登录表单 -->
            <el-form ref="form" size="large" autocomplete="off" v-else>
                <el-form-item>
                    <h1>Sign In</h1>
                </el-form-item>
                <el-form-item>
                    <el-input :prefix-icon="User" placeholder="Username"></el-input>
                </el-form-item>
                <el-form-item>
                    <el-input name="password" :prefix-icon="Lock" type="password" placeholder="Password"></el-input>
                </el-form-item>
                <el-form-item class="flex">
                    <div class="flex">
                        <el-checkbox>Remember me</el-checkbox>
                        <el-link type="primary" :underline="false">Forget pass？</el-link>
                    </div>
                </el-form-item>
                <!-- 登录按钮 -->
                <el-form-item>
                    <el-button class="button" type="primary" auto-insert-space>Sign In</el-button>
                </el-form-item>
                <el-form-item class="flex">
                    <el-link type="info" :underline="false" @click="isRegister = true">
                        Sign Up →
                    </el-link>
                </el-form-item>
            </el-form>
        </el-col>
    </el-row>
</template>

<style lang="scss" scoped>
/* 样式 */
.login-page {
    height: 100vh;
    background-color: #fff;

    .bg {
        background: url('../assets/logo2.png') no-repeat 60% center / 440px auto,
            url('../assets/login_bg.jpeg') no-repeat center / cover;
        border-radius: 0 20px 20px 0;
    }

    .form {
        display: flex;
        flex-direction: column;
        justify-content: center;
        user-select: none;

        .title {
            margin: 0 auto;
        }

        .button {
            width: 100%;
        }

        .flex {
            width: 100%;
            display: flex;
            justify-content: space-between;
        }
    }
}
</style>