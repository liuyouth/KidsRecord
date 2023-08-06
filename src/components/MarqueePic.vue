<script setup lang="ts">
// @ts-ignore
import anime from 'animejs';
import { onMounted } from 'vue';
import TheWelcome from '../components/TheWelcome.vue'
onMounted(() => {
    var xTrans = [];
    anime.set('.m-top', {
        translateX: function (el, i, l) {
            xTrans[i] = { x: i * 600 };
            return i * 600;
        },
    });
    anime({
        targets: xTrans,
        duration: 28000, //走一周持续时间
        easing: 'linear',
        x: "+=2400",
        loop: true,
        update: function (anim) {
            anime.set('.m-top', {
                translateX: function (el, i, l) {
                    return xTrans[i].x % 4200
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
                <TheWelcome images="/src/assets/1.jfif" name="DING · YI MING" title="旋转风车" minTitle="SPIKE PRIME 进阶" />
            </div>
            <div class="m-top">


                <TheWelcome images="/src/assets/2.jfif" name="WANG · ZI HAO" title="旋转风车" minTitle="SPIKE PRIME 进阶" />
            </div>
            <div class="m-top">
                <TheWelcome images="/src/assets/3.jfif" name="LI · NUO HAN" title="陀螺发射器" minTitle="SPIKE PRIME 高级" />
            </div>
            <div class="m-top">
                <TheWelcome images="/src/assets/4.jfif" name="LI · NUO HAN" title="陀螺发射器" minTitle="SPIKE PRIME 高级" />
            </div>
            <div class="m-top">
                <TheWelcome images="/src/assets/3.jfif" name="DING · YI MING" title="旋转风车" minTitle="SPIKE PRIME 进阶" />
            </div>
            <div class="m-top">
                <TheWelcome images="/src/assets/2.jfif" name="WANG · ZI HAO" title="旋转风车" minTitle="SPIKE PRIME 进阶" />
            </div>
            <div class="m-top">
                <TheWelcome images="/src/assets/1.jfif" name="LI · NUO HAN" title="陀螺发射器" minTitle="SPIKE PRIME 高级" />
            </div>

        </div>
    </div>
</template>
<style scoped>
.marqueeBox {
    position: relative;
    width: 4800px;
    overflow: hidden;
    background: black;
    color: rgb(255, 255, 255);
    font-weight: 800;
    font-size: large;
    height: 400px;
    left: -1200px;
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
