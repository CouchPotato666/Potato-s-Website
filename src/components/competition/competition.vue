<script lang='ts' setup>
import { ref } from 'vue'

</script>

<template>
    <div class="competition-container">
        <div class="container-inner">
            <div class="subtitle">Competition</div>
            <div class="title">National Economics Challenge</div>
            <div class="tabContent">
                <div class="tabCard">
                    <n-grid :x-gap="48" style="align-items: center;">
                        <n-gi :span="12">
                            <n-carousel autoplay draggable>
                                <img style="border-radius: 8px; width: 100%" :src="'/Potato-s-Website/nec_1.webp'"
                                    alt="">
                                <img style="border-radius: 8px; width: 100%" :src="'/Potato-s-Website/nec_2.webp'"
                                    alt="">
                            </n-carousel>
                        </n-gi>
                        <n-gi :span="12">
                            <p>
                                SKT-CNEC (China National Economics Challenge), formerly known as SKT-NEC, is China's
                                exclusive pathway to the prestigious NEC global rounds, organized by the Council for
                                Economic Education (CEE)
                            </p>
                            <p>
                                In November 2024, I registered for the <b>SKT-CNEC 2025</b> and took the online
                                preliminary
                                exam in December. The test lasted about an hour and a half and was quite
                                challenging, covering microeconomics, macroeconomics, and factual knowledge. Despite
                                the difficulty, I managed to qualify for the offline stage.
                            </p>
                            <p>
                                In March 2025, I traveled to the
                                <n-popover trigger="hover" placement="left">
                                    <template #trigger>
                                        <n-button text>
                                            <u><b>Changsha International Conference Center</b></u>
                                        </n-button>
                                    </template>
                                    <img style="width: 360px" src="/Potato-s-Website/nec_3.webp" alt="">
                                </n-popover>
                                to participate in the first offline round. Together with four classmates from my
                                school, I formed a team. We began with a written test that determined whether we
                                could advance to the global round. The questions were difficult, but I gave my best
                                effort.
                            </p>
                            <p>
                                The next morning, around thirty teams competed in a quiz session. The format
                                involved multiple-choice questions, with points awarded for correct answers that
                                were added to each team’s total. There were fifteen questions in total, and we had
                                to discuss within our team before writing down our final answers and showing them to
                                the judges. At the end, the advancing teams were announced. Unfortunately, despite
                                our hard work, we did not make it through to the next round.
                            </p>
                            <p>
                                Although it was not a “successful” experience in terms of results, it was still
                                immensely rewarding. Both the online preliminary and the offline rounds exposed me
                                to concepts and theories in economics that are usually taught at higher levels.
                                Through this process, I gained early insight into advanced economic knowledge and
                                sharpened my problem-solving and teamwork skills.
                            </p>
                        </n-gi>
                    </n-grid>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang='less' scoped>
.competition-container {
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

    .tabContent {
        margin-top: 3rem
    }
}
</style>