<script setup lang="ts">
// @ts-ignore
// 使用animejs 制作的动画
import anime from 'animejs';
import { onMounted } from 'vue';
onMounted(() => {
    var xTrans = [];
    anime.set('.m-top', {
        translateX: function (el, i, l) {
            xTrans[i] = { x: i * 600 };
            return i * 600;
             // 每个轮播div的宽度
        },
    });
    anime({
        targets: xTrans,
        duration: 7000, //走一周持续时间   需要和 div的个数和宽度以及速度相匹配才可以做到无跳动
        easing: 'linear',
        x: "-=600",
        loop: true,
        update: function (anim) {
            anime.set('.m-top', {
                translateX: function (el, i, l) {
                    return xTrans[i].x % 3000
                }
            });
        }
    })
})

</script>
<template>
    <div style="overflow: hidden;">
        <div class="marqueeBox">
            <div class="m-top">
                <svg class="marquee-top__separator" height="19" width="19" viewBox="0 0 20 20">
                    <polygon points="17.25,7 11.54,7 16.05,0.05 11.08,0.05 8.12,0.05 2.75,10.17 7.33,10.17 4.32,19.95 ">
                    </polygon>
                </svg>
                <b> MAGO KIDS CENTER 2023 精彩集锦</b>
            </div>
            <div class="m-top">
                <svg class="marquee-top__separator" height="19" width="19" viewBox="0 0 20 20">
                    <polygon points="17.25,7 11.54,7 16.05,0.05 11.08,0.05 8.12,0.05 2.75,10.17 7.33,10.17 4.32,19.95 ">
                    </polygon>
                </svg>
                <b> MAGO KIDS CENTER 2023 精彩集锦</b>
            </div>
            <div class="m-top">
                <svg class="marquee-top__separator" height="19" width="19" viewBox="0 0 20 20">
                    <polygon points="17.25,7 11.54,7 16.05,0.05 11.08,0.05 8.12,0.05 2.75,10.17 7.33,10.17 4.32,19.95 ">
                    </polygon>
                </svg>
                <b> MAGO KIDS CENTER 2023 精彩集锦</b>
            </div>
            <div class="m-top">
                <svg class="marquee-top__separator" height="19" width="19" viewBox="0 0 20 20">
                    <polygon points="17.25,7 11.54,7 16.05,0.05 11.08,0.05 8.12,0.05 2.75,10.17 7.33,10.17 4.32,19.95 ">
                    </polygon>
                </svg>
                <b> MAGO KIDS CENTER 2023 精彩集锦</b>
            </div>
            <div class="m-top">
                <svg class="marquee-top__separator" height="19" width="19" viewBox="0 0 20 20">
                    <polygon points="17.25,7 11.54,7 16.05,0.05 11.08,0.05 8.12,0.05 2.75,10.17 7.33,10.17 4.32,19.95 ">
                    </polygon>
                </svg>
                <b> MAGO KIDS CENTER 2023 精彩集锦</b>
            </div>
        </div>
    </div>
</template>
<style scoped>
.marqueeBox {
    position: relative;
    width:3000px;
    overflow: hidden;
    background: black;
    color: rgb(255, 255, 255);
    font-weight: 800;
    font-size: large;
    height: 60px;
    left: -600px;
}

.m-top {

    white-space: nowrap;
    text-align: start;
    width: 600px;
    position: absolute;
    background: rgb(0, 0, 0);
    font-size: 25px;
    line-height: 60px;
    text-align: center;
}

.marquee-top__separator {
    position: relative;
    top: -1px;
    margin: 0 10px;
    font-size: 1.3em;
    vertical-align: middle;
    fill: currentColor;
}
</style>
