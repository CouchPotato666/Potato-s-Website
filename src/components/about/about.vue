<script setup>
import { gsap } from 'gsap';
import {
    SplitText,
    ScrollToPlugin,
    ScrollSmoother,
    ScrollTrigger
} from 'gsap/all';
import { onMounted } from 'vue';

const emits = defineEmits(["getJumpId"]);

onMounted(() => {
    gsap.registerPlugin(SplitText, ScrollSmoother, ScrollTrigger, ScrollToPlugin);
})

function handleJump(id) {
    emits("getJumpId", id)
}
</script>

<template>
    <div class="about-container">
        <div class="container-inner">
            <div style="margin-bottom: 48px">
                <div class="subtitle">My Info</div>
                <div class="title">About me</div>
            </div>
            <n-grid :x-gap="48" style="align-items: center">
                <n-gi :span="12">
                    <div class="photo-container">
                        <img src="/Potato-s-Website/portrait2.png" alt="">
                    </div>
                </n-gi>
                <n-gi :span="12">
                    <n-flex :size="32" vertical>
                        <div id="hello" style="font-size: 1.5rem; font-weight: 600;">
                            Hi, I am Michael Xia, based in Beijing, China. I am currently study in Harrow International
                            School Beijing.
                        </div>
                        <div id="description" style="font-size: 1.1rem">
                            Although I was born in Hangzhou, I grew up in Beijing and consider it my home. At home, I
                            take care of five Maine Coon cats, who always keep me busy and entertained. In my free time,
                            I enjoy exploring space in No Man’s Sky on Steam, which inspires my curiosity and sense of
                            adventure. My strongest subject is Economics, which I hope to study further in the future.
                            Outside the classroom, one of my favorite things is enjoying authentic Chinese
                            food—especially Mao Xue Wang.
                        </div>
                        <n-grid :x-gap="12">
                            <n-gi id="skill" :span="8" class="skill-block">
                                <n-flex vertical>
                                    <div class="icon">
                                        <n-icon :size="32" color="#26FF00">
                                            <svg xmlns="http://www.w3.org/2000/svg"
                                                xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 512 512">
                                                <path
                                                    d="M496.2 296.5C527.7 218.7 512 126.2 449 63.1C365.1-21 229-21 145.1 63.1l-56 56.1l211.5 211.5c46.1-62.1 131.5-77.4 195.6-34.2zm-217.9 79.7L57.9 155.9c-27.3 45.3-21.7 105 17.3 144.1l34.5 34.6L6.7 424c-8.6 7.5-9.1 20.7-1 28.8l53.4 53.5c8 8.1 21.2 7.6 28.7-1L177.1 402l35.7 35.7c19.7 19.7 44.6 30.5 70.3 33.3c-7.1-17-11-35.6-11-55.1c-.1-13.8 2.5-27 6.2-39.7zM416 320c-53 0-96 43-96 96s43 96 96 96s96-43 96-96s-43-96-96-96z"
                                                    fill="currentColor"></path>
                                            </svg>
                                        </n-icon>
                                    </div>
                                    <div class="label">Table Tennis</div>
                                    <div class="time">2012 - 2020</div>
                                </n-flex>
                            </n-gi>
                            <n-gi id="skill2" :span="8" class="skill-block">
                                <n-flex vertical>
                                    <div class="icon">
                                        <n-icon :size="32" color="#26FF00">
                                            <svg xmlns="http://www.w3.org/2000/svg"
                                                xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 32 32">
                                                <rect x="20" y="2" width="4" height="4" rx="2" fill="currentColor">
                                                </rect>
                                                <path
                                                    d="M11 16a1 1 0 0 1-.707-1.707l7-7a1 1 0 1 1 1.414 1.414l-7 7A.996.996 0 0 1 11 16z"
                                                    fill="currentColor"></path>
                                                <path
                                                    d="M23.707 24.293a8.395 8.395 0 0 0-4.72-2.209c.2-.164.393-.336.578-.521a9.245 9.245 0 0 0 1.733-9.914l-1.877.697c1.11 2.98.635 5.898-1.272 7.802a6.696 6.696 0 0 1-5.56 1.805a9.775 9.775 0 0 1-5.772-2.786c-2.973-2.97-4.076-8.227-.98-11.32c1.906-1.905 4.826-2.38 7.809-1.27l.699-1.875c-3.683-1.369-7.486-.706-9.924 1.731c-3.943 3.939-2.676 10.496.98 14.149a11.814 11.814 0 0 0 6.976 3.36c.21.022.416.023.623.033V24h4.996a6.846 6.846 0 0 1 4.297 1.707L26.586 30L28 28.586z"
                                                    fill="currentColor"></path>
                                            </svg>
                                        </n-icon>
                                    </div>
                                    <div class="label">Badminton</div>
                                    <div class="time">Since 2024</div>
                                </n-flex>
                            </n-gi>
                            <n-gi id="skill3" :span="8" class="skill-block">
                                <n-flex vertical>
                                    <div class="icon">
                                        <n-icon :size="32" color="#26FF00">
                                            <svg xmlns="http://www.w3.org/2000/svg"
                                                xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 512 512">
                                                <path
                                                    d="M429.46 32.07c-23.6 6.53-205.55 58.81-250.54 71.43a4 4 0 0 0-2.92 3.83v247a2 2 0 0 1-1.33 1.89l-27.85 9.55c-19 7.44-66.82 16.68-66.82 59.19c0 35.54 24.63 51.54 45.86 54.28a52.06 52.06 0 0 0 7.81.8c7.37 0 36.38-7.08 53.3-18.08C208 448.25 208 448 208 412V202c0-.9.62-.84 1.48-1.07l188-51.92a2 2 0 0 1 2.53 2v155.54a2 2 0 0 1-1.36 1.89c-8.9 3-19.23 6.5-26.48 9.12C341.39 328.68 304 335.65 304 376c0 38.51 28.26 54.58 46.3 55.83a87.37 87.37 0 0 0 21.33-1c9-1.38 24.09-5.9 38.14-14.86C432 401.79 432 401.51 432 360V34a2 2 0 0 0-2.54-1.93z"
                                                    fill="currentColor"></path>
                                            </svg>
                                        </n-icon>
                                    </div>
                                    <div class="label">Bass Clarinet</div>
                                    <div class="time">2020 - 2021</div>
                                </n-flex>
                            </n-gi>
                        </n-grid>
                    </n-flex>
                </n-gi>
            </n-grid>
        </div>
    </div>
</template>

<style lang="less" scoped>
.about-container {
    height: 100vh;
    font-family: "Poppins", sans-serif;
    background-color: hsl(242, 19%, 5%);
    display: flex;
    align-items: center;
    justify-content: center;

    .container-inner {
        width: 85vw;
        margin: 0 auto;
        position: relative;
    }

    .subtitle {
        color: var(--primary-color);
        font-weight: 600;
        text-align: center;
        font-size: 1.5rem;
    }

    .title {
        text-align: center;
        font-weight: 700;
        font-size: 3rem;
    }

    .photo-container {
        img {
            width: 100%;
            border-radius: 8px;
        }
    }

    .skill-block {
        background: rgb(19, 19, 22);
        border-radius: 8px;
        padding: 1rem;

        .icon {
            text-align: center;
        }

        .label {
            text-align: center;
            font-size: 1.4rem;
            font-weight: 700;
        }

        .time {
            text-align: center;
            font-size: 1.1rem;
        }
    }
}
</style>