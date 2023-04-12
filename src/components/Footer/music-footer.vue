<template>
    <div class="footer">
        <div class="footer_enter">
            <div class="footer_enter_item">
                <a href="https://developer.music.163.com/st/developer" target="_blank"></a>
                <span>音乐开放平台</span>
            </div>
            <div class="footer_enter_item">
                <a href="//music.163.com/st/web-sublicense/home://developer.music.163.com/st/developer" target="_blank"></a>
                <span>云村交易所</span>
            </div>
            <div class="footer_enter_item">
                <a href="https://web-amped.music.163.com/" target="_blank"></a>
                <span>Amped Studio</span>
            </div>
            <div class="footer_enter_item">
                <a href="//music.163.com/st/userbasic#/auth" target="_blank"></a>
                <span>用户认证</span>
            </div>
            <div class="footer_enter_item">
                <a href="//music.163.com/st/ad-cms-bills/mlogin?from=mainStation" target="_blank"></a>
                <span>音乐交易平台</span>
            </div>
            <div class="footer_enter_item">
                <a href="//music.163.com/web/reward" target="_blank"></a>
                <span>赞赏</span>
            </div>
            <div class="footer_enter_item">
                <a href="//music.163.com/st/ncreator/revenue-plan" target="_blank"></a>
                <span>视频激励</span>
            </div>
        </div>
        <div class="copyright">
            <div class="copyright_item">
                <a href="//st.music.163.com/official-terms/service" target="_blank">服务条款</a>
                <a href="//st.music.163.com/official-terms/privacy" target="_blank">隐私政策</a>
                <a href="//st.music.163.com/official-terms/children" target="_blank">儿童隐私政策</a>
                <a href="//music.163.com/st/staticdeal/complaints.html" target="_blank">版权投诉</a>
                <a href="http://ir.music.163.com" target="_blank">投资者关系</a>
                <a href="https://music.163.com/ui/resource" target="_blank">广告合作</a>
                <a href="//mp.music.163.com/600948c936c13f4d09752e73/contact-us-web/index.html?source=Music-Main-Station"
                    target="_blank">联系我们</a>
            </div>
            <div class="copyright_item"></div>
            <div class="copyright_item"></div>
            <div class="copyright_item"></div>
        </div>
    </div>
</template>

<style lang="less">
.footer {
    width: 980px;
    margin: 0 auto;

    &_enter {
        margin-top: 40px;
        display: flex;
        justify-content: space-between;
        align-items: center;

        &_item {

            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;

            &>a {
                display: block;
                background: url(@/assets/Home/foot_enter_new2.png) no-repeat;
                background-size: 220px 220px;
                width: 50px;
                height: 50px;
            }


            &>span {
                margin-top: 20px;
            }

            &:first-child {
                a {
                    background-position: -170px -5px;
                }
            }

            &:nth-child(2) {
                a {
                    background-position: -5px -170px;
                }
            }

            &:nth-child(3) {
                a {
                    background-position: -5px -60px;
                }
            }

            &:nth-child(4) {
                a {
                    background-position: -60px -60px;
                }
            }

            &:nth-child(5) {
                a {
                    background-position: -115px -115px;
                }
            }

            &:nth-child(6) {
                a {
                    background-position: -170px -115px;
                }
            }

            &:nth-child(7) {
                a {
                    background-position: -170px -60px;
                }
            }
        }
    }
    .copyright {
        &_item {
            display: flex;
            justify-content: space-between;

            &:first-child {
                
            }
        }
    }
}
</style>