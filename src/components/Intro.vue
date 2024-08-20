<template>
    <section id="intro">
        <div class="intro__inner">
            <h2 class="intro__title">
                {{introText.title }}
            </h2>
            <div class="intro__lines">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
            <div class="intro__text">
                <div class="text">
                    <div>{{ introText.desc[0] }}</div>
                    <div>{{ introText.desc[1] }}</div>
                    <div>{{ introText.desc[2] }}</div>
                </div>
                <div class="img">
                    <img src="@/assets/img/portmain.jpeg" alt="로고" />
                </div>
            </div>
            <div class="intro__lines bottom">
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
                <span class="line"></span>
            </div>
        </div>
    </section>
</template>
<script setup>
import { introText } from '@/constants';
</script>
<style lang="scss" scoped>
@import "@/assets/scss/mixin";

    #intro {
        height: 100vh;
    }
    .intro__inner {
        width: 100%;
        height: 100%;
        display: flex;
        align-items: flex-start;
        justify-content: flex-end;
        flex-direction: column;
        padding: 16px;
    
        @media (max-width: 800px){
            justify-content: center;
        }
    
        .intro__title {
            font-size: 8vw;
            text-transform: uppercase;
            line-height: 1;
            font-weight: 800;
            white-space: nowrap;
            text-indent: -0.5vw;
            letter-spacing: -0.3vw;
            color: var(--black);
            @media (max-width: 320px){ 
                display: none;
            }
        }
        .intro__text {
            width: 100%;
            height: 50vh;
            background: var(--white);
            color: var(--gray);
            display: flex;
            align-items: center;
            justify-content: center;
            flex-direction: column;
            position: relative;
            overflow: hidden;
            &::before {
                content: "";
                position: absolute;
                width: 200%;
                height: 100%;
                background-color: #1b1b1e;
                top: 56%;
                left: 50%;
                transform: translate(-50%, -50%);
                clip-path: ellipse(50% 20% at 50% 80%);
                animation: wave 5s infinite ease-in-out;
            }
            .text {
                font-size: 3vw;
                line-height: 1;
                font-weight: 900;
                text-transform: uppercase;
                text-decoration: underline;
                text-align: center;
                position: relative;
                z-index: 100;
                opacity: 0;
                transition: all 0.1s;
                cursor: all-scroll;
                @media (max-width: 800px){ 
                    font-size: 24px;
                }
            }
            .img {
                position: absolute;
                left: 50%;
                top: 50%;
                transform: translate(-50%, -50%);
                width: 40vh;
                height: 40vh;
                border-radius: 50%;
                overflow: hidden;
                filter: grayscale(0%);
                transition: all 0.3s;
    
                @media (max-width: 320px){ 
                    width: 20vh;
                    height: 20vh;
                }
            }
    
            &:hover .text {
                opacity: 1;
            }
            &:hover .img {
                filter: grayscale(100%);
            }
        }
        .intro__lines {
            width: 100%;
    
            .line {
                display: block;
                width: 100%;
                height: 1px;
                background-color: var(--white);
                margin-bottom: 0.5vw;
    
                &:nth-child(1){
                    height: 1px;
                }
                &:nth-child(2){
                    height: 2px;
                }
                &:nth-child(3){
                    height: 5px;
                }
                &:nth-child(4){
                    height: 9px;
                }
                &:nth-child(5){
                    height: 13px;
                }
                &:nth-child(6){
                    height: 17px;
                }
                &:nth-child(7){
                    height: 25px;
                }
            }
    
            &.bottom {
                .line {
                    margin-top: 0.5vw;
                    margin-bottom: 0;
                    display: none;
    
                    @media (max-width: 800px){ 
                        display: block;
                    }
    
                    &:nth-child(1){
                        height: 25px;
                    }
                    &:nth-child(2){
                        height: 17px;
                    }
                    &:nth-child(3){
                        height: 13px;
                    }
                    &:nth-child(4){
                        height: 9px;
                    }
                    &:nth-child(5){
                        height: 5px;
                    }
                    &:nth-child(6){
                        height: 2px;
                    }
                    &:nth-child(7){
                        height: 1px;
                    }
                }
            }
        }
    }
    @keyframes wave {
    0% {
        transform: translate(-50%, -50%) translateX(0%);
        clip-path: ellipse(50% 20% at 50% 80%);
    }
    50% {
        transform: translate(-50%, -50%) translateX(-10%);
        clip-path: ellipse(55% 25% at 50% 75%);
    }
    100% {
        transform: translate(-50%, -50%) translateX(0%);
        clip-path: ellipse(50% 20% at 50% 80%);
    }
}
</style>