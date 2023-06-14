<script>
import NavBtn from './components/NavBtn.vue'
import Features from './components/Features.vue'
import NetworkIcon from './components/NetworkIcon.vue'
import FooterText from './components/FooterText.vue'

import Logo from '@/assets/images/logo.svg?component'
import IconOpen from '@/assets/images/icon-hamburger.svg?component'
import IconClose from '@/assets/images/icon-close.svg?component'
import BgPatternNav from '@/assets/images/bg-pattern-mobile-nav.svg?component'
import BgPatternIntroLeftMobile from '@/assets/images/bg-pattern-intro-left-mobile.svg?component'
import BgPatternIntroLeftDesktop from '@/assets/images/bg-pattern-intro-left-desktop.svg?component'
import BgPatternIntroRightMobile from '@/assets/images/bg-pattern-intro-right-mobile.svg?component'
import BgPatternIntroRightDesktop from '@/assets/images/bg-pattern-intro-right-desktop.svg?component'
import BgPatternHowWeWorkMobile from '@/assets/images/bg-pattern-how-we-work-mobile.svg?component'
import BgPatternHowWeWorkDesktop from '@/assets/images/bg-pattern-how-we-work-desktop.svg?component'
import BgPatternFooterMobile from '@/assets/images/bg-pattern-footer-mobile.svg?component'
import BgPatternFooterDesktop from '@/assets/images/bg-pattern-footer-desktop.svg?component'

import imgMobile from '@/assets/images/image-intro-mobile.jpg';
export default {
  data() {
    return {
      imgMobile,
      barClosed: false,
    }
  },
  components: {
    NavBtn,
    Features,
    NetworkIcon,
    FooterText,

    Logo,
    IconOpen,
    IconClose,
    BgPatternNav,
    BgPatternIntroLeftMobile,
    BgPatternIntroLeftDesktop,
    BgPatternIntroRightMobile,
    BgPatternIntroRightDesktop,
    BgPatternHowWeWorkMobile,
    BgPatternHowWeWorkDesktop,
    BgPatternFooterMobile,
    BgPatternFooterDesktop,
  }
}
</script>
<template>
  <body class="flex flex-col items-center text-neo-violet font-karla">
    <nav class=" flex justify-between items-center w-full h-20 px-6">
      <Logo />
      <button @click="barClosed = !barClosed" class=" cursor-pointer">
        <IconOpen v-show="!barClosed" />
        <IconClose v-show="barClosed" />
      </button>
      <div v-show="barClosed"
        class=" absolute right-0 top-20 flex flex-col items-center gap-6 w-full h-[587px] px-6 pt-10 bg-neo-dark-violet text-center z-50">
        <NavBtn txt="How we work" />
        <NavBtn txt="Blog" />
        <NavBtn txt="Account" />
        <NavBtn txt="View plans" hSize="h-[56px]" borderColor="border-neo-light-gray" />
        <BgPatternNav class=" absolute right-0 bottom-0" />
      </div>
    </nav>
    <main class=" flex flex-col gap-[140px]  w-[375px] mb-[140px]">
      <div>
        <img class=" " :src="imgMobile" alt="imgMobile" draggable="false">
        <div
          class=" relative flex flex-col justify-center gap-4 items-center h-[500px] px-[24px] bg-neo-violet text-neo-light-gray text-center">
          <div class=" absolute left-0 top-0">
            <BgPatternIntroLeftMobile />
            <BgPatternIntroLeftDesktop class=" hidden" />
          </div>
          <div class=" absolute right-0 -bottom-[176px]">
            <BgPatternIntroRightMobile />
            <BgPatternIntroRightDesktop class=" hidden" />
          </div>
          <h1 class=" text-[48px] leading-[48px] tracking-[-.67px] font-serif-display z-30">Humanizing your insurance.
          </h1>
          <p class=" mb-4 px-[2px] text-[16px] leading-[26px]">
            Get your life insurance coverage easier and faster. We blend our expertise
            and technology to help you find the plan that’s right for you. Ensure you
            and your loved ones are protected.
          </p>
          <button
            class=" w-[146px] h-[40px] hover:bg-neo-light-gray hover:text-neo-dark-violet text-[13px] leading-[15px] tracking-[1.5px] font-bold uppercase border-[1.5px] border-neo-light-gray select-none ">View
            plans</button>
        </div>
      </div>
      <div class=" flex flex-col gap-20 text-center">
        <div class=" flex flex-col items-center gap-10">
          <div class=" w-[150px] h-[1px] bg-extra1"></div>
          <h1 class=" text-[48px] leading-[48px] tracking-[-.67px] font-serif-display">We’re different</h1>
        </div>
        <div class=" flex flex-col gap-14">
          <Features :index="0" icon="One" />
          <Features :index="1" icon="Two" />
          <Features :index="2" icon="Three" />
        </div>
      </div>
      <div
        class=" relative flex flex-col justify-center items-center gap-10 h-[344px] bg-neo-violet mx-6 text-neo-light-gray text-center">
        <div class=" absolute right-0 top-0 pointer-events-none">
          <BgPatternHowWeWorkMobile />
          <BgPatternHowWeWorkDesktop class=" hidden" />
        </div>
        <h1 class=" text-[40px] leading-[40px] tracking-[-.56px] font-serif-display z-30">
          Find out more about how we work</h1>
        <button
          class=" w-[160px] h-[40px] hover:bg-neo-light-gray hover:text-neo-dark-violet text-[13px] leading-[15px] tracking-[1.5px] font-bold uppercase border-[1.5px] border-neo-light-gray select-none">How
          we work</button>
      </div>
    </main>
    <footer class=" relative flex flex-col gap-10 w-full px-6 py-[88px] bg-neo-light-gray">
      <div class=" absolute top-0 left-0">
        <BgPatternFooterMobile />
        <BgPatternFooterDesktop class=" hidden" />
      </div>
      <div class=" flex flex-col items-center gap-8 z-30">
        <Logo />
        <div class=" flex items-center gap-4">
          <NetworkIcon iconName="facebook" />
          <NetworkIcon iconName="twitter" />
          <NetworkIcon iconName="pinterest" />
          <NetworkIcon iconName="instagram" />
        </div>
      </div>
      <div class=" w-full h-[1px] bg-neo-grayish-violet"></div>
      <div class=" flex flex-col gap-10 text-center text-[13px] leading-[15px] tracking-[1.5px] font-bold">
        <FooterText :index="0" />
        <FooterText :index="1" />
        <FooterText :index="2" />
        <FooterText :index="3" />
      </div>
    </footer>
  </body>
</template>