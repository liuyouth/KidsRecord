<script setup lang="ts">
// @ts-ignore
// 使用animejs 制作的动画
import anime from 'animejs';
import { onMounted } from 'vue';
import TheWelcome from '../components/TheWelcome.vue'
onMounted(() => {
    var xTrans = [];
    anime.set('.m-topic', {
        translateX: function (el, i, l) {
            xTrans[i] = { x: i * 600 };
            return i * 600;
            // 每个轮播div的宽度
        },
    });
    anime({
        targets: xTrans,
        duration: 24000, //走一周持续时间   需要和 div的个数和宽度以及速度相匹配才可以做到无跳动
        easing: 'linear',
        x: "+=4800",
        loop: true,
        update: function (anim) {
            anime.set('.m-topic', {
                translateX: function (el, i, l) {
                    return xTrans[i].x % 4800
                }
            });
        }
    })
})

</script>
<template>
    <div style="overflow: hidden;">
        <div class="marqueeBox">
            <div class="m-topic">
                <TheWelcome images="/src/assets/1.jfif" name="DING · YI MING" title="1旋转风车" minTitle="SPIKE PRIME 进阶" />
            </div>
            <div class="m-topic">
                <TheWelcome images="/src/assets/2.jfif" name="WANG · ZI HAO" title="2旋转风车" minTitle="SPIKE PRIME 进阶" />
            </div>
            <div class="m-topic">
                <TheWelcome images="/src/assets/3.jfif" name="LI · NUO HAN" title="3陀螺发射器" minTitle="SPIKE PRIME 高级" />
            </div>
            <div class="m-topic">
                <TheWelcome images="/src/assets/4.jfif" name="LI · NUO HAN" title="4陀螺发射器" minTitle="SPIKE PRIME 高级" />
            </div>
            <div class="m-topic">
                <TheWelcome images="/src/assets/1.jfif" name="DING · YI MING" title="5旋转风车" minTitle="SPIKE PRIME 进阶" />
            </div>
            <div class="m-topic">
                <TheWelcome images="/src/assets/2.jfif" name="WANG · ZI HAO" title="6旋转风车" minTitle="SPIKE PRIME 进阶" />
            </div>
            <div class="m-topic">
                <TheWelcome images="/src/assets/3.jfif" name="LI · NUO HAN" title="7陀螺发射器" minTitle="SPIKE PRIME 高级" />
            </div>
            <div class="m-topic">
                <TheWelcome images="/src/assets/4.jfif" name="LI · NUO HAN" title="8陀螺发射器" minTitle="SPIKE PRIME 高级" />
            </div>
        </div>
    </div>
</template>
<style scoped>
.marqueeBox {
    position: relative;
    width: 7200px;
    overflow: hidden;
    background: black;
    color: rgb(255, 255, 255);
    font-weight: 800;
    font-size: large;
    height: 400px;
    left: -600px;
}

.m-topic {
    overflow: hidden;
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
