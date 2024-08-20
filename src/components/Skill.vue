<template>
    <section id="skill">
        <div class="skill__inner">
            <h2 class="skill__title">
                Skills <em>스택기술</em>
            </h2>
            <div class="skill__desc">
                <div v-for="(skill, key) in skills" :key="key">
                    <span>{{ key + 1 }}</span>
                    <h3>{{ skill.title }}</h3>
                    <p>{{ skill.desc }}</p>
                    <div class="progress-bar" @mouseover="increaseProgress(key)" @mouseout="resetProgress(key)">
                        <div class="progress" :style="{ width: skill.progressWidth }"></div>
                        <p>{{ skill.progressWidth }}</p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<script setup>
import { skillText } from '@/constants';
import { ref } from 'vue';

const skills = ref(skillText.map(skill => ({
    ...skill,
    progressWidth: "0%" // 모든 스킬의 초기 progressWidth를 0%로 설정
})));


function increaseProgress(key) {
  skills.value[key].progressWidth = skills.value[key].targetWidth; // 마우스 오버 시 개별 목표 너비로 변경
}

</script>

<style lang="scss">
.skill__inner {
    padding: 16px;
    display: flex;
    justify-content: space-between;

    @media (max-width: 800px) {
        flex-direction: column;
    }

    .skill__title {
        position: sticky;
        top: 70px;
        left: 0;
        width: 48%;
        height: 5vw;
        font-size: 3vw;
        font-weight: 900;
        line-height: 1.6;
        font-family: var(--mainKor-font);
        text-transform: uppercase;
        color: var(--black100);
        border-bottom: 0.4vw solid var(--black100);

        @media (max-width: 800px) {
            width: 100%;
            margin-bottom: 10vw;
            font-size: 30px;
            height: auto;
            top: 68px;
            background-color: var(--mainBg-color);
        }

        em {
            font-size: 1.25rem;
            font-weight: 400;
            line-height: 2;
        }
    }

    .skill__desc {
        width: 50%;

        @media (max-width: 800px) {
            width: 100%;
        }

        span {
            font-size: 5vw;
            line-height: 1;
            font-weight: 900;
            line-height: 1.3;
            font-family: var(--mainNum-font);

            @media (max-width: 800px) {
                font-size: 20vw;
            }
        }

        h3 {
            font-size: 1.5rem;
            text-decoration: underline;
            text-underline-position: under;
            margin-bottom: 1vw;
        }

        p {
            margin-bottom: 30px;
            font-size: 1.1rem;
        }

        .progress-bar {
            width: 100%;
            height: 30px;
            background-color: #dedede;
            font-weight: 600;
            font-size: 1rem;
            margin-bottom: 30vh;
            position: relative;
            overflow: hidden;

            .progress {
                height: 30px;
                padding: 0;
                text-align: center;
                background-color: #4F98FF;
                color: #111;
                transition: width 0.5s ease;
                position: relative;
                display: flex;
                align-items: center;
                justify-content: center;

            }

            p {
                margin-bottom: 0;
                position: absolute;
                transform: translate(-50%, -50%);
                top: 50%;
                left: 50%;
            }
        }
    }
}
</style>
