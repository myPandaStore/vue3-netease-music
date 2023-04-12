<script setup lang="ts">
import { ref } from "vue"

// 模拟<a href="/#"></a>
const simulateAtag = () => {
    window.scrollTo({
        top: 0,
        left: 0,
        behavior: 'smooth'
    });
}

const activeIndex = ref(0)
// header 激活态
const activateItem = (index: number) => {
    activeIndex.value = index
}

// 初始化 header input 框值
const input = ref("")

</script>
<template>
    <div class="header">
        <div class="container">
            <div class="header_left">
                <div class="header_left_item" @click="simulateAtag">
                </div>
                <div class="header_left_item" @click="activateItem(0)">
                    <a href="/#">发现音乐</a>
                    <sub v-show="activeIndex === 0"></sub>
                </div>
                <div class="header_left_item" @click="activateItem(1)">
                    <a href="/#">我的音乐</a>
                    <sub v-show="activeIndex === 1"></sub>
                </div>
                <div class="header_left_item" @click="activateItem(2)">
                    <a href="/#">关注</a>
                    <sub v-show="activeIndex === 2"></sub>
                </div>
                <div class="header_left_item">
                    <a href="/#">商城</a>

                </div>
                <div class="header_left_item">
                    <a href="/#">音乐人</a>

                </div>
                <div class="header_left_item" @click="activateItem(5)">
                    <a href="/#">下载客户端</a>
                    <sub v-show="activeIndex === 5"></sub>
                </div>
            </div>
            <div class="header_right">
                <el-input v-model="input" placeholder="音乐/视频/电台/用户" class="header_right_search" />
                <div class="header_right_creator">创作者中心</div>
                <div class="header_right_login">登陆</div>
            </div>
        </div>
    </div>
</template>
<style lang="less">
.header {
    background: #242424;


    .container {
        width: 1100px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin: 0 auto;
    }

    &_left {
        display: flex;
        justify-content: space-around;

        &_item {
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;

            &:hover {
                background: #000;
            }

            &>a {
                text-decoration: none;
                color: white;
                font-size: 14px;
                padding: 0 19px;
            }

            &>sub {
                display: block;
                position: absolute;
                left: 50%;
                top: 63px;
                width: 12px;
                height: 7px;
                margin-left: -6px;
                overflow: hidden;
                background: url(@/assets/Home/topbar.png) no-repeat -226px 0;
            }

            &:first-child {
                background: url(@/assets/Home/topbar.png) no-repeat 0 0;
                background-position: 0 0;
                width: 176px;
                height: 69px;

                &:hover {
                    cursor: pointer;
                }
            }

            &:last-child {
                position: relative;

                &::after {
                    content: "";
                    display: block;
                    position: absolute;
                    top: 15px;
                    right: -15px;
                    width: 28px;
                    height: 19px;
                    background: url(@/assets/Home/topbar.png) no-repeat -190px 0;
                }
            }
        }

    }

    &_right {
        display: flex;
        justify-content: center;
        align-items: center;

        &_search {
            width: 158px;
            height: 32px;
            font-size: 12px;
            --el-input-border-radius: 100px;
            background: white;
            border-radius: 100px;

            .el-input__wrapper {
                background: url(@/assets/Home/topbar.png) no-repeat 0 -99px;
            }

            .el-input__inner {
                margin-left: 20px;
            }
        }

        &_creator {
            width: 90px;
            height: 32px;
            margin: 0 20px;
            box-sizing: border-box;
            padding-left: 16px;
            border: 1px solid #4F4F4F;
            line-height: 33px;
            color: #ccc;
            border-radius: 20px;
        }

        &_login {
            width: 28px;
            color: #787878;
        }
    }
}
</style>