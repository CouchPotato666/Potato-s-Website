<script setup>
import { ref, onMounted } from 'vue'
import { gsap } from 'gsap';
import {
    ScrollSmoother,
    ScrollTrigger,
    SplitText
} from 'gsap/all';

const emits = defineEmits(["getJumpId"]);

onMounted(() => {
    document.fonts.ready.then(() => {
        gsap.registerPlugin(SplitText);
        const split = SplitText.create(".hello", { type: "chars" });
        gsap.from(split.chars, {
            y: 20,
            autoAlpha: 0,
            stagger: 0.05
        });

        gsap.set("#intro", { opacity: 1 })

        let mySplitText = SplitText.create("#intro", { type: "chars, words" });

        gsap.from(mySplitText.chars, {
            duration: 2,
            opacity: 0,
            stagger: { from: "random", each: 0.01 }
        });

        gsap.set(".SocialMedia", { opacity: 0, y: -100 })

        gsap.to(".SocialMedia", {
            duration: 1,
            opacity: 1,
            stagger: { y: 0 },
            delay: 1
        });

        gsap.set(".email", { opacity: 0, y: 100 })

        gsap.to(".email", {
            duration: 1,
            opacity: 1,
            stagger: { y: 0 },
            delay: 1
        });

        gsap.set("#aboutButton", { opacity: 0 })

        gsap.to("#aboutButton", {
            duration: 1,
            opacity: 1,
            delay: 2
        });
    })
})

function handleJump(id) {
    emits("getJumpId", id)
}
</script>

<template>
    <div class="landing-container">
        <div class="container-inner">
            <n-flex class="SocialMedia" :align="'center'">
                <div>Follow me</div>
                <div>-</div>
                <n-flex>
                    <n-icon :size="24">
                        <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                            viewBox="0 0 1024 1024">
                            <path
                                d="M847.7 112H176.3c-35.5 0-64.3 28.8-64.3 64.3v671.4c0 35.5 28.8 64.3 64.3 64.3h671.4c35.5 0 64.3-28.8 64.3-64.3V176.3c0-35.5-28.8-64.3-64.3-64.3zm0 736c-447.8-.1-671.7-.2-671.7-.3c.1-447.8.2-671.7.3-671.7c447.8.1 671.7.2 671.7.3c-.1 447.8-.2 671.7-.3 671.7zM230.6 411.9h118.7v381.8H230.6zm59.4-52.2c37.9 0 68.8-30.8 68.8-68.8a68.8 68.8 0 1 0-137.6 0c-.1 38 30.7 68.8 68.8 68.8zm252.3 245.1c0-49.8 9.5-98 71.2-98c60.8 0 61.7 56.9 61.7 101.2v185.7h118.6V584.3c0-102.8-22.2-181.9-142.3-181.9c-57.7 0-96.4 31.7-112.3 61.7h-1.6v-52.2H423.7v381.8h118.6V604.8z"
                                fill="currentColor"></path>
                        </svg>
                    </n-icon>
                    <n-icon :size="24">
                        <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                            viewBox="0 0 512 512">
                            <path
                                d="M349.33 69.33a93.62 93.62 0 0 1 93.34 93.34v186.66a93.62 93.62 0 0 1-93.34 93.34H162.67a93.62 93.62 0 0 1-93.34-93.34V162.67a93.62 93.62 0 0 1 93.34-93.34h186.66m0-37.33H162.67C90.8 32 32 90.8 32 162.67v186.66C32 421.2 90.8 480 162.67 480h186.66C421.2 480 480 421.2 480 349.33V162.67C480 90.8 421.2 32 349.33 32z"
                                fill="currentColor"></path>
                            <path d="M377.33 162.67a28 28 0 1 1 28-28a27.94 27.94 0 0 1-28 28z" fill="currentColor">
                            </path>
                            <path
                                d="M256 181.33A74.67 74.67 0 1 1 181.33 256A74.75 74.75 0 0 1 256 181.33m0-37.33a112 112 0 1 0 112 112a112 112 0 0 0-112-112z"
                                fill="currentColor"></path>
                        </svg>
                    </n-icon>
                </n-flex>
            </n-flex>
            <n-grid :x-gap="24">
                <n-gi class="left" :span="10">
                    <n-flex vertical>
                        <div class="hello">
                            <b>Hello, I'm Michael</b>
                        </div>
                        <p id="intro" style="font-size: 1.1rem">
                            I am currently working on application for business, economics, and good future.
                        </p>
                        <div id="aboutButton" style="margin-top: 12px">
                            <n-button type="primary" style="color: #fff; padding: 1.5rem" @click="handleJump('#about')">
                                <template #icon>
                                    <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                                        viewBox="0 0 512 512">
                                        <path
                                            d="M344 144c-3.92 52.87-44 96-88 96s-84.15-43.12-88-96c-4-55 35-96 88-96s92 42 88 96z"
                                            fill="none" stroke="currentColor" stroke-linecap="round"
                                            stroke-linejoin="round" stroke-width="32"></path>
                                        <path
                                            d="M256 304c-87 0-175.3 48-191.64 138.6C62.39 453.52 68.57 464 80 464h352c11.44 0 17.62-10.48 15.65-21.4C431.3 352 343 304 256 304z"
                                            fill="none" stroke="currentColor" stroke-miterlimit="10" stroke-width="32">
                                        </path>
                                    </svg>
                                </template>
                                <b>More about me!</b>
                            </n-button>
                        </div>
                    </n-flex>
                </n-gi>
                <n-gi class="right" :span="14">
                    <img src="/Potato-s-Website/portrait.png" alt="">
                </n-gi>
            </n-grid>
            <div class="email">
                <n-flex :align="'center'" :size="16">
                    <n-icon :size="36" color="#26FF00">
                        <svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                            viewBox="0 0 24 24">
                            <g fill="none">
                                <path
                                    d="M18.75 3H5.25l-.184.005A3.25 3.25 0 0 0 2 6.25v9.5l.005.184A3.25 3.25 0 0 0 5.25 19h6.467c.184-.422.445-.807.773-1.135l.365-.365H5.25l-.144-.006A1.75 1.75 0 0 1 3.5 15.75V8.374l8.15 4.29l.097.042a.75.75 0 0 0 .602-.042L20.5 8.373v2.634a3.294 3.294 0 0 1 1.5.253V6.25l-.005-.184A3.25 3.25 0 0 0 18.75 3zM5.25 4.5h13.5l.143.006A1.75 1.75 0 0 1 20.5 6.25v.428L12 11.152L3.5 6.68V6.25l.006-.144A1.75 1.75 0 0 1 5.25 4.5zm13.85 8.17l-5.903 5.902a2.686 2.686 0 0 0-.706 1.247l-.458 1.831a1.087 1.087 0 0 0 1.319 1.318l1.83-.457a2.685 2.685 0 0 0 1.248-.707l5.902-5.902A2.286 2.286 0 0 0 19.1 12.67z"
                                    fill="currentColor"></path>
                            </g>
                        </svg>
                    </n-icon>
                    <n-flex vertical :size="0">
                        <div class="label">Email</div>
                        <div class="value">mixia@harrowbeijing.cn</div>
                    </n-flex>
                </n-flex>
            </div>
        </div>
    </div>
</template>

<style scoped>
.landing-container {
    height: 100vh;
    font-family: "Poppins", sans-serif;
    background: rgb(19, 19, 20);

    .container-inner {
        width: 85vw;
        margin: 0 auto;
        position: relative;

        .SocialMedia {
            position: absolute;
            font-size: 1.2rem;
            font-weight: 600;
            top: 2rem;
            left: 2rem;
        }

        .email {
            position: absolute;
            bottom: 2rem;
            left: 2rem;

            .label {
                font-size: 1.1rem;
                font-weight: 600;
            }

            .value {
                font-size: 1rem;
            }
        }

        .left {
            height: 100vh;
            display: flex;
            align-items: center;

            .n-flex {
                padding: 2rem;
            }

            .hello {
                font-size: 3rem;
            }
        }

        .right {
            position: relative;
            height: 100vh;
            display: flex;
            align-items: center;

            img {
                position: absolute;
                width: 85%;
                bottom: 0;
                right: 0
            }
        }
    }
}
</style>