<script setup>
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import {ref} from "vue";

gsap.registerPlugin(ScrollTrigger);
const isPlaying = ref(false)
const audioRef = ref(null)

const toggleAudio = () => {
  if (!audioRef.value) return

  if (isPlaying.value) {
    audioRef.value.pause()
  } else {
    audioRef.value.play()
  }

  isPlaying.value = !isPlaying.value
}


setTimeout(() => {
  const tl1 = gsap.timeline({
    scrollTrigger: {
      trigger: '.main',
      scrub: true,
      pin: true
    },
  });

  const tl2 = gsap.timeline({
    scrollTrigger: {
      trigger: '.title',
      scrub: true,
      pin: true
    },
  });

  const tl3 = gsap.timeline({
    scrollTrigger: {
      trigger: '.about',
      scrub: true,
      pin: true
    },
  });

  const tl5 = gsap.timeline({
    scrollTrigger: {
      trigger: '.stack',
      scrub: true,
      start: '+=400px bottom',
      end: '+=400px',
    },
  });

  ScrollTrigger.matchMedia({
    // 💻 Десктоп
    "(min-width: 1024px)": function () {
      tl1
          .set('#title1', {
            autoAlpha: 0
          })
          .set('#title2', {
            autoAlpha: 0
          })
          .to('.main-man', {
            scale: 1.2,
            duration: 50
          })
          .to('#title1', {
            autoAlpha: 1,
            duration: 50
          })
          .to('#title2', {
            autoAlpha: 1,
            duration: 50
          })
      tl2
          .set('.title-name', {
            scale: 0.3,
            opacity: 0
          })
          .set('.title-bg', {
            scale: 0.3,
            opacity: 0
          })
          .to('.title-bg', {
            scale: 1,
            opacity: 0.4,
            duration: 50
          })
          .to('.title-name', {
            scale: 1,
            opacity: 1,
            duration: 50
          })
      tl3
          .set('.about-left', {
            xPercent: -100,
            opacity: 0
          })
          .set('.about-right', {
            xPercent: 100,
            opacity: 0
          })
          .to('.about-left', {
            xPercent: 0,
            opacity: 1
          })
          .to('.about-right', {
            xPercent: 0,
            opacity: 1
          })
      tl5
          .set('#stack1', {autoAlpha: 0})
          .set('#stack2', {autoAlpha: 0})
          .set('#stack3', {autoAlpha: 0})
          .set('#stack4', {autoAlpha: 0})
          .set('#stack5', {autoAlpha: 0})
          .set('#stack6', {autoAlpha: 0})
          .set('#stack7', {autoAlpha: 0})
          .set('#stack8', {autoAlpha: 0})
          .set('#stack9', {autoAlpha: 0})
          .set('#stack10', {autoAlpha: 0})
          .set('#stack11', {autoAlpha: 0})
          .set('#stack12', {autoAlpha: 0})
          .set('#stack13', {autoAlpha: 0})
          .set('#stack14', {autoAlpha: 0})
          .to('#stack1', {autoAlpha: 1})
          .to('#stack2', {autoAlpha: 1})
          .to('#stack3', {autoAlpha: 1})
          .to('#stack4', {autoAlpha: 1})
          .to('#stack5', {autoAlpha: 1})
          .to('#stack6', {autoAlpha: 1})
          .to('#stack7', {autoAlpha: 1})
          .to('#stack8', {autoAlpha: 1})
          .to('#stack9', {autoAlpha: 1})
          .to('#stack10', {autoAlpha:1})
          .to('#stack11', {autoAlpha:1})
          .to('#stack12', {autoAlpha:1})
          .to('#stack13', {autoAlpha:1})
          .to('#stack14', {autoAlpha:1})
    },
    // 📱 мобильные
    "(max-width: 1023px)": function () {
      tl1
          .set('#title1', {
            opacity: 0
          })
          .set('#title2', {
            opacity: 0
          })
          .to('.main-man', {
            scale: 1.2,
            duration: 50
          })
          .to('#title1', {
            opacity: 1,
            y: '-55vh',
            duration: 50
          })
          .to('#title2', {
            opacity: 1,
            y: '-53vh',
            duration: 50
          })
      tl2
          .set('.title-name', {
            scale: 0.3,
            opacity: 0
          })
          .set('.title-bg', {
            scale: 0.3,
            opacity: 0
          })
          .to('.title-bg', {
            scale: 1,
            opacity: 0.4,
            duration: 50
          })
          .to('.title-name', {
            scale: 1,
            opacity: 1,
            duration: 50
          })
    },
  });
}, 500)
</script>

<template>
  <main class="main">
    <div class="main-glow"/>
    <img src="@/assets/images/me.png" class="main-man"/>
    <svg class="main-svg-title" width="1920" height="356" viewBox="0 0 1920 356" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path opacity="0.05" fill-rule="evenodd" clip-rule="evenodd" d="M860.874 261.349C860.874 254.129 863.399 247.85 868.454 242.513C873.822 237.177 880.773 232.31 889.301 227.915C898.141 223.52 908.09 219.439 919.149 215.672C930.52 211.905 942.202 208.138 954.209 204.37C968.422 199.661 982.636 194.638 996.849 189.302C1011.37 184.278 1024.33 178 1035.7 170.466C1042.16 166.297 1047.9 161.696 1052.92 156.662V280.185H1052.76C1044.86 284.894 1036.96 288.976 1029.07 292.429C1021.49 295.882 1013.43 298.864 1004.9 301.376C996.375 303.887 987.056 305.771 976.95 307.026C966.839 308.282 955.468 308.91 942.838 308.91C927.989 308.91 915.359 307.654 904.936 305.143C894.513 302.945 885.984 299.806 879.351 295.725C873.03 291.644 868.293 286.621 865.138 280.656C862.295 274.691 860.874 268.256 860.874 261.349ZM1052.92 334.955C1045.33 337.527 1037.85 339.99 1030.49 342.344C1021.64 345.169 1012.48 347.524 1003.01 349.407C993.533 351.605 983.583 353.175 973.16 354.116C963.049 355.372 951.84 356 939.522 356C916.145 356 895.934 353.489 878.878 348.466C862.133 343.757 848.082 337.007 836.711 328.217C825.652 319.427 817.442 308.91 812.075 296.667C806.701 284.423 804.02 270.924 804.02 256.169C804.02 242.356 807.337 230.584 813.97 220.852C820.914 211.12 829.76 202.644 840.501 195.423C851.554 188.203 863.873 181.924 877.456 176.587C891.352 171.564 905.409 166.698 919.623 161.989C932.253 157.908 944.416 153.67 956.104 149.275C967.787 145.194 978.21 140.642 987.374 135.619C996.531 130.91 1003.79 125.416 1009.17 119.138C1014.85 112.859 1017.7 105.796 1017.7 97.9471C1017.7 90.0986 1016.11 83.0351 1012.96 76.7566C1009.8 70.4781 1004.59 65.1409 997.323 60.746C990.054 56.3512 980.579 52.8975 968.896 50.3862C957.208 48.1885 942.676 47.0899 925.308 47.0899C911.095 47.0899 898.777 47.875 888.353 49.4444C877.93 51.0139 868.293 53.2116 859.453 56.037C853.318 57.9975 847.332 60.2596 841.497 62.8246L710.44 348.937H670.78H658.324H357.781H356.19H304.718V211.905H74.4601V348.937H74.0553H21.3966H-196V6.59259H21.3966H74.0553H74.4601V168.582H304.718V6.59259H357.781V302.788H487.426V6.59259H501.502H540.49H564.515C569.882 17.8942 575.886 31.2361 582.519 46.619C589.151 62.3155 596.096 79.1111 603.365 97.0053H765.872C773.135 79.1111 779.923 62.3155 786.245 46.619C792.877 31.2361 798.875 17.8942 804.248 6.59259H861.822C871.297 4.70898 881.402 3.13953 892.144 1.88358C903.196 0.627655 915.671 0 929.572 0C955.468 0 977.58 2.66861 995.902 8.00528C1014.22 13.3419 1029.22 20.7196 1040.91 30.1376C1045.37 33.7355 1049.38 37.5855 1052.92 41.6871V6.59259H1105.99V168.582H1336.24V6.59259H1347.11H1389.31H1410.12C1415.49 17.8942 1421.5 31.2361 1428.13 46.619C1434.76 62.3155 1441.71 79.1111 1448.97 97.0053H1611.48C1618.74 79.1111 1625.53 62.3155 1631.85 46.619C1638.49 31.2361 1644.48 17.8942 1649.86 6.59259H1659.65H1712.71H1712.87L1712.74 6.87573L1731.67 226.032C1732.3 235.136 1732.77 243.612 1733.09 251.46C1733.41 259.622 1733.56 267.628 1733.56 275.476H1738.3L1851.53 72.0476H1887.07L1999.83 275.476H2004.56V251.931C2004.88 244.083 2005.51 235.45 2006.46 226.032L2024.94 6.59259H2078L2048.15 348.937H1985.61C1968.56 320.055 1952.45 292.429 1937.29 266.058C1930.97 254.757 1924.49 243.141 1917.86 231.212C1911.23 219.282 1904.91 207.667 1898.91 196.365C1892.91 185.378 1887.54 174.86 1882.8 164.815C1878.06 155.083 1874.27 146.45 1871.43 138.915H1866.69C1863.85 146.45 1860.06 155.083 1855.32 164.815C1850.59 174.86 1845.22 185.378 1839.21 196.365C1833.53 207.667 1827.37 219.282 1820.74 231.212C1814.1 243.141 1807.63 254.757 1801.31 266.058C1786.15 292.429 1770.2 320.055 1753.46 348.937H1689.5L1668.16 104.192L1556.05 348.937H1503.93L1389.31 98.7071V348.937H1336.24V211.905H1105.99V348.937H1052.92V334.955ZM637.183 302.788H540.49V91.7121L637.183 302.788ZM21.3966 302.788H-142.937V211.905H21.3966V302.788ZM21.3966 168.582H-142.937V52.7407H21.3966V168.582ZM715.651 221.794L749.763 139.857H619.474L652.638 221.794C664.009 249.42 673.796 274.849 682.013 298.079H686.75C694.961 274.849 704.592 249.42 715.651 221.794ZM1595.37 139.857L1561.26 221.794C1550.2 249.42 1540.57 274.849 1532.36 298.079H1527.62C1519.41 274.849 1509.62 249.42 1498.25 221.794L1465.08 139.857H1595.37Z" fill="white"/>
    </svg>
    <div class="main-titles">
      <h2 id="title1">
        Hello,
      </h2>
      <h2 id="title2">
        I'm Artem Ptashenko
      </h2>
    </div>
  </main>
  <section class="title">
    <h2 class="title-name">
      Front-end developer
    </h2>
    <img src="@/assets/images/coding-bg.jpg" class="title-bg" />
  </section>
  <section class="about">
    <div class="about-wrapper">
      <div class="about-left">
        <h2>
          About me
        </h2>
        <p>
          Hey there! I'm a front-end developer who loves building things that actually feel good to use.
          Over the last few years, I’ve been crafting websites and apps in areas like mental health, astrology, lead generation, and e-commerce.
          I mostly work with Vue.js, Nuxt, TypeScript, and Tailwind, and I care a lot about performance, accessibility, and clean code.
          I’m all about turning ideas into fast, responsive, and modern interfaces—with just the right amount of animation and a good dose of curiosity.
          When I’m not coding, I’m probably sketching out ideas, reading about UX, or just learning something random and new.
        </p>
        <button class="sound-button" :class="{animation: isPlaying}" @click="toggleAudio">
          <img v-if="!isPlaying" src="@/assets/images/sound-off.svg" />
          <img v-else src="@/assets/images/sound-on.svg" />
        </button>
        <audio ref="audioRef" class="audio-content">
          <source src="@/assets/voice_text.mp3" type="audio/mpeg">
          Your browser does not support the audio element.
        </audio>
      </div>
      <div class="about-right">
        <svg id="question" width="72" height="106" viewBox="0 0 72 106" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path opacity="0.5" fill-rule="evenodd" clip-rule="evenodd" d="M21.6914 4.43056C30.8043 3.17362 40.9532 2.41177 49.9721 3.5755C52.1586 3.85763 53.3078 4.65651 53.9328 5.56993C54.5896 6.52994 54.8497 7.88071 54.7143 9.58396C54.4411 13.0214 52.6206 17.1286 51.0203 20.0069C48.445 24.6386 45.0605 28.781 41.4452 32.8907C40.5561 33.9013 39.65 34.9131 38.7392 35.9301L38.7385 35.9309C35.9793 39.012 33.1771 42.141 30.675 45.4309C30.5653 45.5751 30.4541 45.7207 30.3418 45.8678C29.0093 47.6128 27.5185 49.5652 26.654 51.652C25.6709 54.0253 25.455 56.6587 26.9669 59.4936C29.4653 64.178 33.0764 67.9455 36.5097 71.5274L36.5098 71.5275C36.7922 71.8221 37.0734 72.1154 37.3526 72.4079C41.0824 76.3146 44.5037 80.0988 46.5114 84.9174C46.8301 85.6821 47.7083 86.0438 48.473 85.7251C49.2377 85.4065 49.5993 84.5283 49.2807 83.7636C47.0342 78.372 43.2389 74.2289 39.5225 70.3363C39.2568 70.058 38.9916 69.7811 38.7273 69.5051C35.2401 65.8634 31.9086 62.3843 29.614 58.0819C28.6018 56.1841 28.7174 54.5098 29.4256 52.8002C30.1331 51.0923 31.3896 49.4432 32.786 47.6105L32.786 47.6105L33.0628 47.247C35.4855 44.0616 38.1726 41.0608 40.9107 38.0031C41.8366 36.9691 42.7683 35.9286 43.6976 34.8722C47.3425 30.729 50.9041 26.3892 53.6422 21.4647C55.292 18.4977 57.3788 13.9248 57.7049 9.82164C57.8691 7.75456 57.6019 5.61984 56.4087 3.87593C55.1837 2.08545 53.1603 0.962009 50.356 0.600161C40.9441 -0.614274 30.4859 0.189131 21.2815 1.4587C20.9917 1.49867 20.6825 1.54015 20.3564 1.58389L20.3563 1.58391C17.4159 1.97833 13.1061 2.55645 9.28073 3.87512C5.11169 5.31226 0.859132 7.85941 0.145275 12.6524C-0.0205774 13.766 -0.0158764 14.9189 0.0210886 15.9856C0.0348317 16.3822 0.0523361 16.7576 0.0692237 17.1199C0.100098 17.7821 0.128911 18.4001 0.128911 19.0222C0.128911 19.8506 0.800483 20.5222 1.62891 20.5222C2.45734 20.5222 3.12891 19.8506 3.12891 19.0222C3.12891 18.3347 3.09452 17.5901 3.06178 16.881C3.04584 16.5359 3.03029 16.1992 3.01929 15.8817C2.98377 14.8568 2.98847 13.9274 3.11255 13.0944C3.55938 10.0942 6.2711 8.08583 10.2584 6.71134C13.7808 5.4971 17.7864 4.95755 20.7578 4.55729L20.7583 4.55722C21.0823 4.51357 21.394 4.47159 21.6914 4.43056ZM57.5214 95.5715C57.5947 95.3203 57.6621 95.2164 57.6899 95.1819C58.9762 94.6538 61.0708 94.55 63.175 94.9988C65.323 95.4569 67.0272 96.3912 67.7756 97.4851C68.5051 98.5513 68.741 99.2936 68.7711 99.7686C68.7971 100.178 68.6795 100.465 68.4205 100.737C68.1188 101.055 67.587 101.382 66.7613 101.666C65.9495 101.945 64.9524 102.148 63.8283 102.283C61.7476 102.533 59.3965 102.53 57.2958 102.429C57.4629 102.187 57.5608 101.894 57.5608 101.577C57.5608 101.18 57.5138 100.612 57.4667 100.044L57.4664 100.04C57.4564 99.9194 57.4464 99.7988 57.4369 99.6798C57.3782 98.9471 57.3243 98.1581 57.3271 97.4076C57.3299 96.64 57.3931 96.0116 57.5214 95.5715ZM51.7529 101.909C52.3323 101.998 53.3934 102.134 54.7206 102.252C54.6184 102.049 54.5608 101.82 54.5608 101.577C54.5608 101.316 54.528 100.916 54.482 100.356L54.482 100.355C54.4708 100.22 54.4589 100.075 54.4465 99.9195C54.3868 99.1752 54.3238 98.2805 54.3271 97.3964C54.3303 96.5294 54.3962 95.5723 54.6413 94.7317C54.8788 93.9176 55.3805 92.9003 56.4854 92.4338C58.5262 91.5722 61.3173 91.5351 63.8007 92.0647C66.2609 92.5894 68.8673 93.7679 70.2516 95.7911C71.1446 97.0963 71.6878 98.3603 71.7651 99.5786C71.8466 100.863 71.4002 101.956 70.5954 102.803C69.8334 103.606 68.8019 104.137 67.7366 104.503C66.6574 104.874 65.4358 105.112 64.1855 105.262C59.2318 105.856 53.0762 105.148 51.2967 104.874C50.4779 104.748 49.9163 103.982 50.0423 103.164C50.1682 102.345 50.9341 101.783 51.7529 101.909ZM57.6989 95.1716C57.7016 95.1687 57.7031 95.1675 57.7032 95.1676C57.7032 95.1678 57.7019 95.1692 57.6989 95.1716Z" fill="white"/>
        </svg>
        <img src="@/assets/images/artem1.jpg" />
        <svg id="lamp" width="207" height="230" viewBox="0 0 207 230" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M86.8652 69.3336C92.2435 67.1174 97.6524 65.6164 103.481 65.742C104.757 65.7695 105.634 65.6727 106.861 65.8908C107.443 65.9942 108.157 65.6485 108.763 65.6211C109.333 65.5952 109.659 66.081 110.232 66.1721C112.099 66.469 114.216 67.8272 115.579 69.0655C119.207 72.3617 124.545 73.7593 127.149 78.1746C127.544 78.8451 128.388 79.1508 128.86 79.782C129.359 80.4483 129.539 81.2919 130.041 81.9722C130.846 83.0624 131.521 84.1591 132.037 85.4115C133.18 88.1854 134.659 90.8391 135.821 93.6599C137.022 96.5755 139.045 99.8396 139.466 102.972C139.6 103.969 140.259 105.515 139.932 106.442C138.858 109.486 138.697 112.979 138.76 116.176C138.798 118.042 138.108 119.698 137.879 121.572C137.695 123.08 137.858 124.974 137.359 126.39C136.081 130.014 136.18 133.693 135.436 137.419C135.172 138.741 135.362 140.063 135.792 141.298C136.196 142.457 135.81 144.046 135.922 145.249C136.134 147.542 138.203 149.631 138.597 151.898C138.727 152.644 138.19 153.379 138.331 154.214C138.423 154.761 138.953 156.022 138.339 156.416C137.437 156.996 136.842 158.406 136.06 159.304C133.822 161.876 131.601 163.414 128.219 164.077" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M137.561 158.686C139.142 158.034 143.785 160.494 142.233 162.542C141.958 162.906 140.508 164.489 140.564 164.986C140.661 165.843 142.451 166.954 143.175 167.165C143.675 167.311 144.162 168.945 144.217 169.434C144.402 171.071 142.773 171.463 142.678 172.767C142.574 174.192 146.213 174.982 146.517 176.731C146.821 178.48 143.825 178.58 143.96 179.776C144.14 181.372 145.091 182.29 144.507 183.962C143.561 186.673 139.57 187.924 136.948 189.004" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M141.985 187.536C142.913 189.789 141.822 192.783 142.618 195.072C143.125 196.532 141.522 200.706 139.16 201.679" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M99.3647 55.7027C97.7144 50.5099 97.5457 44.3135 97.3379 38.9351C97.0384 31.1874 97.3265 23.3578 97.4933 15.6149" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M125.206 58.5456C127.504 54.9453 129.144 51.134 130.514 47.107" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M142.851 75.1734C144.751 73.4874 147.746 72.7816 150.037 71.8265C154.385 70.0142 158.43 68.0443 162.408 65.5727" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M151.754 97.7158C154.219 96.8936 156.827 97.9403 159.291 98.3363C161.427 98.6798 163.366 98.6458 165.46 98.2357" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M150.172 123.808C154.929 124.327 158.447 128.62 163.2 129.233" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M131.498 162.246C130.302 159.342 129.105 156.438 127.908 153.534C127.399 152.297 126.737 151.125 126.223 149.878C125.749 148.726 125.366 147.427 124.747 146.344C124.392 145.723 123.855 145.266 123.518 144.616C123.113 143.834 122.701 143.046 122.212 142.313C121.707 141.557 121.388 140.748 121.044 139.914C120.484 138.553 120.039 137.495 119.943 136.037C119.694 132.221 119.331 128.46 118.796 124.67C118.204 120.485 118.76 116.395 118.842 112.225C118.87 110.845 119.002 109.472 119.016 108.091C119.032 106.512 118.751 105.059 118.568 103.508C118.383 101.939 118.185 100.162 118.276 98.5819C118.325 97.7411 118.064 96.6191 118.267 95.8346C118.45 95.1239 118.62 94.4376 118.731 93.7065C118.938 92.331 117.826 93.2361 117.233 93.6879C115.772 94.8006 114.108 95.498 112.695 96.6802C111.539 97.6478 110.235 98.4887 108.944 99.2687C108.495 99.5402 107.94 99.6316 107.501 99.913C107.189 100.114 106.826 100.635 106.603 100.095C106.392 99.5836 106.107 99.0599 105.993 98.5182C105.925 98.1931 105.325 94.9988 104.693 95.5574C104.169 96.0213 103.884 96.86 103.55 97.4588C103.226 98.0396 103.487 98.8804 103.169 99.3541C102.83 99.8583 102.963 100.812 102.858 101.419C102.758 101.995 102.807 102.609 102.786 103.197C102.771 103.599 102.606 104.129 102.683 104.491C102.852 105.28 101.881 103.804 101.785 103.589C101.291 102.48 100.061 101.947 99.1852 101.184" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M125.717 164.27C124.603 163.585 124.372 160.921 124.01 159.789C123.371 157.793 122.432 155.863 121.633 153.925C121.165 152.789 120.851 151.593 120.379 150.448C119.703 148.806 119.434 147.22 118.93 145.533C118.353 143.601 117.874 141.764 117.101 139.89C116.59 138.65 116.08 137.41 115.569 136.171C114.408 133.354 112.93 130.518 112.118 127.58C111.325 124.707 110.409 121.913 109.273 119.158C109.041 118.594 108.867 117.723 108.42 117.304C107.812 116.734 107.721 116.539 108.207 115.703C108.625 114.985 109.002 114.327 109.294 113.567C109.626 112.701 109.4 112.887 108.594 113.219C107.692 113.591 106.69 114.177 105.727 114.361C104.967 114.507 104.172 114.505 103.447 114.804C102.21 115.314 101.058 115.94 99.8416 116.469C98.0816 117.234 102.842 119.587 103.477 119.867C103.849 120.032 104.833 120.319 105.061 120.675C105.403 121.207 105.602 121.936 105.832 122.522C106.37 123.891 106.466 125.361 107.032 126.736C107.688 128.328 108.037 129.995 108.672 131.583C110.028 134.973 111.227 138.403 112.539 141.81C113.928 145.418 115.161 149.066 116.633 152.638C118.543 157.274 120.454 161.91 122.364 166.546" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M86.0856 69.6548C80.7071 71.8711 75.8109 74.6165 71.763 78.8117C70.8762 79.7308 70.1859 80.2796 69.4686 81.299C69.1283 81.7825 68.3782 82.0401 67.9288 82.4474C67.5063 82.8304 67.6167 83.4054 67.2744 83.8735C66.1582 85.3998 65.613 87.8548 65.5182 89.6938C65.2658 94.5889 62.4614 99.342 63.7244 104.31C63.9162 105.064 63.5326 105.875 63.642 106.656C63.7575 107.481 64.224 108.206 64.347 109.043C64.5439 110.383 64.8378 111.637 65.3538 112.889C66.4968 115.663 67.3168 118.589 68.4792 121.409C69.6806 124.325 70.5449 128.066 72.4533 130.586C73.0606 131.388 73.682 132.949 74.5671 133.377C77.4732 134.781 80.0493 137.146 82.256 139.46C83.5445 140.81 85.2009 141.499 86.6832 142.668C87.8764 143.608 89.0947 145.068 90.4469 145.721C93.9074 147.393 96.4283 150.073 99.5813 152.193C100.7 152.946 101.497 154.017 102.061 155.197C102.591 156.304 103.985 157.16 104.753 158.092C106.218 159.869 106.222 162.81 107.539 164.697C107.972 165.317 108.871 165.46 109.359 166.152C109.679 166.605 110.192 167.874 110.905 167.721C111.954 167.496 113.369 168.078 114.557 168.165C117.958 168.412 120.618 167.94 123.485 166.028" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M112.212 169.521C110.297 170.31 108.039 175.484 110.998 175.632C111.524 175.658 114.036 175.58 114.368 175.948C114.94 176.583 114.193 178.684 113.708 179.378C113.373 179.858 114.194 181.3 114.52 181.663C115.612 182.875 117.368 181.88 118.455 182.659C119.643 183.512 116.998 186.824 118.069 188.201C119.141 189.579 121.896 187.342 122.693 188.228C123.758 189.411 123.614 190.741 125.42 191.386C128.348 192.432 132.875 190.184 136.048 188.877" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M127.735 192.327C128.741 194.767 131.45 196.407 132.559 198.785C133.267 200.301 137.094 202.531 139.16 201.679" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M65.8098 69.5296C63.3227 64.6816 59.0768 60.1653 55.4352 56.2019C50.1892 50.4924 44.4687 45.1388 38.8952 39.7613" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M49.4727 89.7527C45.3056 88.8164 41.456 87.2675 37.6464 85.3749" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M48.6645 113.984C46.1277 114.127 43.5048 115.736 41.206 116.672C36.8439 118.449 32.5848 119.901 28.0206 120.949" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M58.2271 136.255C55.8987 137.408 54.7846 139.989 53.3153 142.005C52.0413 143.754 50.6411 145.096 48.8663 146.28" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path opacity="0.4" d="M77.7332 153.658C74.7215 157.378 75.2499 162.902 72.3084 166.686" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M118.066 167.781C116.87 164.877 115.673 161.973 114.476 159.069C113.966 157.832 113.611 156.534 113.097 155.287C112.622 154.135 111.978 152.944 111.655 151.739C111.469 151.048 111.528 150.346 111.309 149.647C111.045 148.807 110.783 147.957 110.614 147.092C110.439 146.2 110.096 145.401 109.752 144.567C109.192 143.207 108.762 142.142 107.802 141.04C105.29 138.156 102.899 135.232 100.609 132.164C98.0802 128.778 94.8042 126.266 91.8075 123.365C90.8161 122.405 89.7548 121.524 88.7716 120.553C87.6476 119.445 86.8245 118.215 85.8609 116.985C84.887 115.742 83.7758 114.341 82.5975 113.284C81.9705 112.722 81.3652 111.742 80.6688 111.327C80.0379 110.952 79.4335 110.585 78.8402 110.144C77.7241 109.314 79.1506 109.173 79.89 109.076C81.711 108.836 83.3831 108.159 85.2187 108.002C86.7211 107.874 88.2386 107.553 89.7044 107.197C90.2146 107.073 90.6731 106.747 91.1824 106.638C91.5457 106.56 92.1709 106.674 91.948 106.133C91.7375 105.622 91.5712 105.049 91.2703 104.585C91.0897 104.306 89.2649 101.617 90.1066 101.568C90.8058 101.528 91.5987 101.922 92.2577 102.112C92.8968 102.296 93.3037 103.077 93.8635 103.189C94.4593 103.308 95.037 104.078 95.5393 104.435C96.0158 104.774 96.4136 105.243 96.8429 105.646C97.136 105.921 97.6272 106.18 97.8272 106.492C98.2632 107.171 97.9127 105.44 97.8294 105.22C97.3988 104.084 97.8959 102.839 97.9803 101.681" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <path d="M123.595 165.145C123.903 163.874 122.19 161.82 121.65 160.761C120.697 158.895 120.004 156.864 119.205 154.925C118.737 153.789 118.117 152.719 117.646 151.575C116.969 149.933 116.042 148.617 115.211 147.065C114.26 145.288 113.306 143.647 112.533 141.772C112.023 140.532 111.512 139.293 111.001 138.053C109.84 135.237 108.891 132.182 107.398 129.525C105.937 126.928 104.618 124.299 103.483 121.544C103.251 120.98 102.761 120.239 102.782 119.627C102.812 118.794 102.74 118.592 101.806 118.341C101.003 118.126 100.272 117.925 99.5295 117.59C98.6836 117.21 98.975 117.183 99.781 116.851C100.684 116.479 101.807 116.189 102.62 115.641C103.263 115.209 103.826 114.648 104.551 114.349C105.788 113.839 107.047 113.472 108.282 112.99C110.07 112.294 108.349 117.317 108.097 117.964C107.948 118.343 107.453 119.24 107.541 119.653C107.673 120.271 108.046 120.929 108.295 121.507C108.878 122.858 109.846 123.968 110.412 125.343C111.068 126.935 111.995 128.364 112.663 129.938C114.09 133.299 115.655 136.578 117.124 139.92C118.68 143.46 120.375 146.917 121.847 150.489C123.757 155.125 125.668 159.761 127.578 164.397" stroke="white" stroke-width="2" stroke-linecap="round"/>
          <g filter="url(#filter0_f_1_71)">
            <path d="M139.426 89.8933C144.722 102.746 143.006 116.741 136.047 127.628C131.671 134.474 144.937 155.762 125.52 163.762C102.868 173.097 99.6553 147.359 91.3919 145.246C79.2839 142.151 68.7378 133.578 63.6102 121.135C54.9832 100.199 64.9615 76.2332 85.8974 67.6062C106.833 58.9792 130.799 68.9575 139.426 89.8933Z" fill="#FFB800"/>
          </g>
          <defs>
            <filter id="filter0_f_1_71" x="0.507202" y="4.50317" width="202.021" height="221.291" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
              <feFlood flood-opacity="0" result="BackgroundImageFix"/>
              <feBlend mode="normal" in="SourceGraphic" in2="BackgroundImageFix" result="shape"/>
              <feGaussianBlur stdDeviation="30" result="effect1_foregroundBlur_1_71"/>
            </filter>
          </defs>
        </svg>
      </div>
    </div>
  </section>
  <section class="experience">
    <div class="experience-wrapper">
      <h2 class="experience-title">
        Recent projects
      </h2>
      <div class="experience-list">
        <div id="exp-1" class="experience-item">
          <div class="experience-item-left">
            <h2>Astroway</h2>
            <a href="https://astroway.life" target="_blank" class="">
              https://astroway.life
            </a>
            <div class="experience-item-stack">
              <img src="@/assets/images/logos/vue.svg"/>
              <img src="@/assets/images/logos/vite.svg"/>
              <img src="@/assets/images/logos/js.svg"/>
              <img src="@/assets/images/logos/sass.svg"/>
              <img src="@/assets/images/logos/html.svg"/>
              <img src="@/assets/images/logos/npm.svg"/>
              <img src="@/assets/images/logos/pwa.svg"/>
            </div>
          </div>
          <div class="experience-item-right">
            <p>
              An interactive web platform offering personalized horoscopes, Tarot card readings, and natal chart generation based on birth data. The service combines traditional astrological methods with modern UX to deliver deep, personalized insights in an intuitive format.
            </p>
          </div>
        </div>
        <div id="exp-2" class="experience-item">
          <div class="experience-item-left">
            <h2>MindHealthy</h2>
            <a href="https://mindhealthy.pro" target="_blank">
              https://mindhealthy.pro
            </a>
            <div class="experience-item-stack">
              <img src="@/assets/images/logos/vue.svg"/>
              <img src="@/assets/images/logos/vite.svg"/>
              <img src="@/assets/images/logos/js.svg"/>
              <img src="@/assets/images/logos/sass.svg"/>
              <img src="@/assets/images/logos/html.svg"/>
              <img src="@/assets/images/logos/npm.svg"/>
            </div>
          </div>
          <div class="experience-item-right">
            <p>
              A digital tool for tracking emotional well-being. Users can log their feelings, take depression and anxiety tests, and access helpful psychology and mental health articles. The goal is to support self-awareness and emotional clarity.
            </p>
          </div>
        </div>
        <div id="exp-3" class="experience-item">
          <div class="experience-item-left">
            <h2>Generect</h2>
            <a href="https://generect.com" target="_blank">
              https://generect.com
            </a>
            <div class="experience-item-stack">
              <img src="@/assets/images/logos/nuxtjs.svg"/>
              <img src="@/assets/images/logos/vite.svg"/>
              <img src="@/assets/images/logos/js.svg"/>
              <img src="@/assets/images/logos/sass.svg"/>
              <img src="@/assets/images/logos/html.svg"/>
              <img src="@/assets/images/logos/npm.svg"/>
            </div>
          </div>
          <div class="experience-item-right">
            <p>
              A B2B platform that helps users discover decision-makers’ contact information — including emails, phone numbers, and social media profiles. The tool automates lead search and streamlines targeted outreach for sales and marketing teams.
            </p>
          </div>
        </div>
        <div id="exp-4" class="experience-item">
          <div class="experience-item-left">
            <h2>HubForce</h2>
            <a href="https://hubforce.com" target="_blank">
              https://hubforce.com
            </a>
            <div class="experience-item-stack">
              <img src="@/assets/images/logos/vue.svg"/>
              <img src="@/assets/images/logos/vite.svg"/>
              <img src="@/assets/images/logos/ts.svg"/>
              <img src="@/assets/images/logos/sass.svg"/>
              <img src="@/assets/images/logos/html.svg"/>
              <img src="@/assets/images/logos/npm.svg"/>
              <img src="@/assets/images/logos/docker.svg"/>
            </div>
          </div>
          <div class="experience-item-right">
            <p>
              An online builder for crafting personalized digital sales proposals. Users can generate dynamic web pages featuring product descriptions, pricing, presentations, and contact forms. The service enhances the sales process by making proposals more engaging and interactive.
            </p>
          </div>
        </div>
        <div id="exp-5" class="experience-item">
          <div class="experience-item-left">
            <h2>NovaTag S.r.l.</h2>
            <a href="https://www.novatag.it" target="_blank">
              https://www.novatag.it
            </a>
            <div class="experience-item-stack">
              <img src="@/assets/images/logos/nuxtjs.svg"/>
              <img src="@/assets/images/logos/vite.svg"/>
              <img src="@/assets/images/logos/ts.svg"/>
              <img src="@/assets/images/logos/sass.svg"/>
              <img src="@/assets/images/logos/html.svg"/>
              <img src="@/assets/images/logos/npm.svg"/>
            </div>
          </div>
          <div class="experience-item-right">
            <p>
              Worked at an Italian marketing agency specializing in digital campaigns for the HoReCa and FMCG (Fast-Moving Consumer Goods) sectors. Designed and developed promotional landing pages, interactive product pages, and digital assets for leading Italian and international brands. Developed digital materials for a variety of well-known brands, including: Coca-Cola, Ichnusa, Coop Italia, Babybel, Segafredo, Caffè Vergnano.
            </p>
          </div>
        </div>
        <div id="exp-6" class="experience-item">
          <div class="experience-item-left">
            <h2>Quiz Dr. Kegel</h2>
            <a href="https://quiz.kegel-plan.com" target="_blank">
              https://quiz.kegel-plan.com
            </a>
            <div class="experience-item-stack">
              <img src="@/assets/images/logos/vue.svg"/>
              <img src="@/assets/images/logos/webpack.svg"/>
              <img src="@/assets/images/logos/nuxtjs.svg"/>
              <img src="@/assets/images/logos/vite.svg"/>
              <img src="@/assets/images/logos/ts.svg"/>
              <img src="@/assets/images/logos/sass.svg"/>
              <img src="@/assets/images/logos/html.svg"/>
              <img src="@/assets/images/logos/npm.svg"/>
              <img src="@/assets/images/logos/pwa.svg"/>
              <img src="@/assets/images/logos/nodejs.svg"/>
            </div>
          </div>
          <div class="experience-item-right">
            <p>
              A marketing quiz funnel designed to promote Kegel training courses. Users answer a series of questions and receive a personalized recommendation with a course offer. The funnel is optimized to increase engagement and conversion rates.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
  <section class="stack">
    <div class="stack-wrapper">
      <h2 class="stack-title">
        My stack
      </h2>
      <div class="stack-content">
        <div class="stack-list">
          <div id="stack1" class="stack-item">
            <img src="@/assets/images/logos/css.svg"/>
            <p>CSS</p>
          </div>
          <div id="stack2" class="stack-item">
            <img src="@/assets/images/logos/docker.svg"/>
            <p>Docker</p>
          </div>
          <div id="stack3" class="stack-item">
            <img src="@/assets/images/logos/figma.svg"/>
            <p>Figma</p>
          </div>
          <div id="stack4" class="stack-item">
            <img src="@/assets/images/logos/html.svg"/>
            <p>HTML</p>
          </div>
          <div id="stack5" class="stack-item">
            <img src="@/assets/images/logos/js.svg"/>
            <p>JavaScript</p>
          </div>
          <div id="stack6" class="stack-item">
            <img src="@/assets/images/logos/nodejs.svg"/>
            <p>NodeJS</p>
          </div>
          <div id="stack7" class="stack-item">
            <img src="@/assets/images/logos/vue.svg"/>
            <p>VueJS</p>
          </div>

        </div>
        <div class="stack-list">
          <div id="stack8" class="stack-item">
            <img src="@/assets/images/logos/npm.svg"/>
            <p>NPM</p>
          </div>
          <div id="stack9" class="stack-item">
            <img src="@/assets/images/logos/nuxtjs.svg"/>
            <p>NuxtJS</p>
          </div>
          <div id="stack10" class="stack-item">
            <img src="@/assets/images/logos/pwa.svg"/>
            <p>PWA</p>
          </div>
          <div id="stack11" class="stack-item">
            <img src="@/assets/images/logos/sass.svg"/>
            <p>Sass</p>
          </div>
          <div id="stack12" class="stack-item">
            <img src="@/assets/images/logos/ts.svg"/>
            <p>TypeScript</p>
          </div>
          <div id="stack13" class="stack-item">
            <img src="@/assets/images/logos/vite.svg"/>
            <p>Vite</p>
          </div>
          <div id="stack14" class="stack-item">
            <img src="@/assets/images/logos/webpack.svg"/>
            <p>Webpack</p>
          </div>
        </div>
      </div>
    </div>
  </section>
  <footer class="footer">
    <div class="footer-wrapper">
      <h2 class="footer-title">Wana book a project?</h2>
      <a href="mailto:aptashenko2019@gmail.com" class="footer-email">aptashenko2019@gmail.com</a>
      <div class="footer-links">
        <a href="https://wa.me/380505742362" target="_blank">Whatsapp</a>
        <a href="https://t.me/aptashenko" target="_blank">Telegram</a>
        <a href="https://www.instagram.com/vuejs.aptashenko" target="_blank">Instagram</a>
        <a href="https://github.com/aptashenko" target="_blank">GitHub</a>
        <a href="https://www.linkedin.com/in/aptashenko/" target="_blank">LinkedIn</a>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.main {
  position: relative;
  min-height: 100vh;
  overflow-x: hidden;
  overflow-y: hidden;
}

.main::after {
  content: '';
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 50vh;
  pointer-events: none;
  background: linear-gradient(to bottom, transparent, #030303);
  z-index: 5;
}

.main-glow {
  position: absolute;
  width: 100%;
  height: 100%;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: radial-gradient(circle,rgba(255, 255, 255, 1) 40%, transparent 100%);
  filter: blur(100px);
  opacity: 0.05;
}

.main-man {
  position: absolute;
  bottom: 0;
  left: 50%;
  transform: translateX(-50%);
  width: 30vw;
  z-index: 1;

  @media (max-width: 480px) {
    width: 40vh;
  }
}
.main-svg-title {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.main-titles {
  position: absolute;
  bottom: 15vh;
  left: 50%;
  transform: translateX(-50%);
  z-index: 10;

  width: 80%;

  font-style: normal;
  font-weight: 600;
  font-size: 120px;
  line-height: 1;
  text-align: center;

  color: #FFFFFF;

  text-shadow: 9px 6px 6px rgba(0, 0, 0, 0.25);

  @media (max-width: 480px) {
    font-size: 40px;
  }
}

#title2 {
  @media (max-width: 480px) {
    font-size: 30px;
  }
}

.title {
  position: relative;
  min-height: 100vh;
}

.title::before {
  content: '';
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 50vh;
  pointer-events: none;
  background: linear-gradient(to bottom, transparent, #030303);
  z-index: 10;
}

.title::after {
  content: '';
  position: absolute;
  top: 0;
  width: 100%;
  height: 50vh;
  pointer-events: none;
  background: linear-gradient(to top, transparent, #030303);
  z-index: 10;
}

.title-bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  opacity: 0.4;
}

.title-name {
  font-style: normal;
  font-weight: 400;
  font-size: 140px;
  line-height: 165px;
  text-align: center;

  color: transparent;
  -webkit-text-stroke: 1px white;
  letter-spacing: 2px;

  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 90%;
  z-index: 2;

  @media (max-width: 480px) {
    font-size: 24px;
  }
}

.about {
  position: relative;
  min-height: 100vh;
}


.about-wrapper {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 90%;

  display: flex;
  align-items: center;
  justify-content: center;
  gap: 5vw;

  @media (max-width: 480px) {
    flex-direction: column;
  }
}

.about-left {
  flex-basis: 60%;
}

.about-left h2 {
  font-style: normal;
  font-weight: 400;
  font-size: 98px;
  line-height: 116px;

  color: #FFFFFF;

  margin-bottom: 40px;


  @media (max-width: 480px) {
    font-size: 40px;
    line-height: 1.2;
    margin-bottom: 20px;
  }
}

.about-left p {
  font-style: normal;
  font-weight: 400;
  font-size: 24px;
  line-height: 36px;

  color: #FFFFFF;

  opacity: 0.6;

  @media (max-width: 480px) {
    font-size: 15px;
    line-height: 1.3;
  }
}

.about-right {
  position: relative;
  width: 100%;
  flex-basis: 40%;

  @media (max-width: 480px) {
    width: 80%;
    flex-basis: 30%;
  }
}

.about-right #question {
  position: absolute;
  left: 85%;
  bottom: 90%;

  @media (max-width: 480px) {
    width: 50px;
    left: 90%;
    bottom:75%;
  }
}

.about-right #lamp {
  position: absolute;
  right: 70%;
  top: 60%;

  @media (max-width: 480px) {
    width: 100px;
    right: 80%;
    top: 40%;
  }
}

.about-right img {
  display: block;
  width: 90%;
  margin: 0 auto;
}

.experience {
  position: relative;
  min-height: 100vh;
  background: #E6E6E6;
  padding: 60px 0;
}

.experience-wrapper {
  width: 90%;
  margin: 0 auto;
}

.experience-title {
  font-style: normal;
  font-weight: 400;
  font-size: 98px;
  line-height: 116px;
  color: #030303;
  margin-bottom: 80px;

  @media (max-width: 480px) {
    font-size: 40px;
    margin-bottom: 0;
    line-height: 1.3;
  }
}

.experience-list {
  display: flex;
  flex-direction: column;
}

.experience-item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 40px 0;

  border-bottom: 1px solid rgba(3, 3, 3, 0.5);

  @media (max-width: 480px) {
    flex-direction: column;
  }
}

.experience-item-left {
  @media (max-width: 480px) {
    width: 100%;
  }
}

.experience-item-left h2 {
  font-style: normal;
  font-weight: 600;
  font-size: 54px;
  line-height: 66px;

  color: #030303;

  @media (max-width: 480px) {
    font-size: 32px;
  }
}

.experience-item-left a {
  position: relative;
  display: block;
  font-style: normal;
  font-weight: 300;
  font-size: 18px;
  line-height: 36px;
  width: fit-content;

  color: #030303;

  opacity: 0.84;

}

.experience-item-left a::before {
  position: absolute;
  top: 90%;
  content: '';
  display: block;
  background: #030303;
  width: 0;
  height: 1px;
  transition: width 0.3s ease; /* добавляем анимацию */
}

.experience-item-left a:hover {
  opacity: 0.7;
}

.experience-item-left a:hover::before {
  width: 100%;
}

.experience-item-right p {
  font-style: normal;
  font-weight: 300;
  font-size: 24px;
  line-height: 36px;

  color: #030303;

  opacity: 0.84;

  @media (max-width: 480px) {
    font-size: 18px;
    line-height: 1.4;
  }
}

.experience-item > div {
  flex: 1;
}

.stack {
  height: 100vh;
  padding: 60px 0;

  @media (max-width: 480px) {
    height: auto;
  }
}

.stack-wrapper {
  width: 90%;
  margin: 0 auto;
  height: 100%;

  display: flex;
  flex-direction: column;
}

.stack-title {
  font-style: normal;
  font-weight: 400;
  font-size: 98px;
  line-height: 116px;
  color: #fff;

  @media (max-width: 480px) {
    font-size: 40px;
  }
}

.stack-content {
  flex: 1;

  display: flex;
  flex-direction: column;
  justify-content: center;
}

.stack-list {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  width: fit-content;
  margin: 0 auto;
}

.stack-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  font-size: 14px;
  line-height: 1;
  color: #fff;
  text-align: center;

  transition: all .5s ease;
}

.stack-item > p {
  opacity: 0.6;
}

.stack-item img {
  display: block;
  width: 150px;

  @media (max-width: 480px) {
    width: 80px;
  }
}

.footer {
  min-height: 50vh;
  padding: 60px 0;
}

.footer-wrapper {
  width: 90%;
  margin: 0 auto;
}

.footer-title {
  font-style: normal;
  font-weight: 400;
  font-size: 98px;
  line-height: 116px;
  color: #fff;

  @media (max-width: 480px) {
    font-size: 34px;
    line-height: 1;
    text-align: center;
  }
}

.footer-email {
  position: relative;
  font-style: normal;
  font-weight: 400;
  font-size: 40px;
  line-height: 116px;
  color: #fff;
  transition: all .25s ease;

  @media (max-width: 480px) {
    font-size: 22px;
    margin: 24px auto;
    width: fit-content;

    display: block;
    line-height: 1.2;

    text-align: center;
  }
}

.footer-email::before {
  position: absolute;
  top: 100%;
  content: '';
  display: block;
  background: #fff;
  width: 0;
  height: 1px;
  transition: width 0.3s ease; /* добавляем анимацию */
}

.footer-email:hover {
  color: #fff;
  opacity: 0.7;
}

.footer-email:hover::before {
  width: 100%;
}

.footer-links {
  display: flex;
  align-items: center;
  justify-content: flex-end;
  gap: 24px;


  @media (max-width: 480px) {
    flex-direction: column;
  }
}

.footer-links a {
  position: relative;
  color: #fff;
  transition: all .25s ease;
}

.footer-links a::before {
  position: absolute;
  top: 100%;
  content: '';
  display: block;
  background: #fff;
  width: 0;
  height: 1px;
  transition: width 0.3s ease; /* добавляем анимацию */
}

.footer-links a:hover {
  color: #fff;
  opacity: 0.7;
}

.footer-links a:hover::before {
  width: 100%;
}

.experience-item-stack {
  display: flex;
  align-items: center;
  width: fit-content;
  @media (max-width: 480px) {
    flex-wrap: wrap;
  }
}

.experience-item-stack img {
  display: block;
  width: 40px;
}

.sound-button {
  position: absolute;
  right: 0;
  top: 0;
  width: 60px;
  background: transparent;
  border: none;
  cursor: pointer;
  border-radius: 50%;
  padding: 5px;
  transition: all .25s ease;
}

.sound-button:hover {
  background: rgba(255, 255, 255, 0.1);
}

.sound-button img {
  display: block;
  width: 100%;
}

.sound-button.animation {
  -webkit-animation: pulsate-fwd 0.5s ease-in-out infinite both;
  animation: pulsate-fwd 0.5s ease-in-out infinite both;
}

.audio-content {
  visibility: hidden;
}

@-webkit-keyframes pulsate-fwd {
  0% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
  50% {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}
@keyframes pulsate-fwd {
  0% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
  50% {
    -webkit-transform: scale(1.1);
    transform: scale(1.1);
  }
  100% {
    -webkit-transform: scale(1);
    transform: scale(1);
  }
}

</style>
