
<script setup>
 
 const showSidebar = ref(false)
const toggleActive = () => {
  showSidebar.value = !showSidebar.value 
}

const showMenu = ref(false)
const toggleMenu = () => {
  showMenu.value = !showMenu.value
}

// active menu
const isSticky = ref(false);
const handleSticky = () => {
  if (window.scrollY > 80) {
    isSticky.value = true;
  } else {
    isSticky.value = false;
  }
};

onMounted(() => {
  window.addEventListener('scroll', handleSticky);
});
onUnmounted(() => {
  window.removeEventListener('scroll', handleSticky);
});






// video popup
import {useVideoModal} from "~/components/composables/useVideoModal";
const { playVideo } = useVideoModal();
const videoUrl = 'https://www.youtube.com/embed/cuA_ZDb-QDk?si=MlPxBV05EDKHnvIk';



</script>


<template>

  <CommonSidebar :showSidebar="showSidebar" :toggleActive="toggleActive" />

  <!-- banner  -->
  <section class="banner__section">
    <!-- Header v-1  -->
    <header :class="`header-section ${isSticky ? 'menu-fixed' : ''}`">
      <div class="container">
        <div class="header-wrapper">
          <div class="main__logo">
            <NuxtLink to="/" class="logo">
              <img src="~/assets/img/logo/logo.png" alt="logo">
            </NuxtLink>
          </div>
          <ul :class="`main-menu ${showMenu ? 'active' : ''}`">
            <li>
              <NuxtLink to="/"> 
                Home
              </NuxtLink>
            </li>
            <li>
              <a href="#about">
                About
              </a>
            </li>
            <li>
              <a href="#prot">
                Work
              </a>
            </li>
            <li>
              <a href="#services">
                Services
              </a>
              <ul class="sub-menu">
                <li>
                  <NuxtLink to="/service">
                    Service
                  </NuxtLink>
                </li>
                <li>
                  <NuxtLink to="/service-details">
                    Service Details
                  </NuxtLink>
                </li>
              </ul>
            </li>
            <li>
              <a href="#testi">
                Testimonial
              </a>
            </li>
            <li>
              <a href="#">
                Blog
              </a>
              <ul class="sub-menu">
                <li class="subtwohober">
                  <NuxtLink to="/blog">Blog</NuxtLink>
                </li>
                <li><NuxtLink to="/blog-details">Blog Details</NuxtLink></li>
              </ul>
            </li>
            <li>
              <NuxtLink to="/contact">
                Contact
              </NuxtLink>
            </li>
          </ul>
          <div class="menu__components d-flex align-items-center">
            <NuxtLink to="/contact" class="d-flex fw-500 cmn--btn align-items-center gap-2">
              <span class="get__text">
                Let's Talk
              </span>
              <span>
                <i class="bi bi-arrow-right fz-20"></i>
              </span>
            </NuxtLink>
            <div @click="toggleMenu" :class="`header-bar d-lg-none ${showMenu ? 'active' : ''}`">
              <span></span>
              <span></span>
              <span></span>
            </div>
            <div @click="toggleActive" class="remove__click">
              <i class="bi bi-list"></i>
            </div>
          </div>
        </div>
      </div>
    </header>
    <!-- Header v-1  -->
    <div class="container">
      <div class="row g-4">
        <div class="col-lg-8">
          <div class="banner__content">
            <a href="#" class="bn__currently">
              <span class="d-block">
                Currently available for freelance
              </span>
              <span class="d-flex gap-4 align-items-center">
                worldwide
                <i class="bi bi-arrow-up-right"></i>
              </span>
            </a>
            <h1>
              <span class="hone"> Creative Visual</span>
              <span class="d-block designers" data-text="Designer">Designer</span>
            </h1>
            <div class="video__area">
              <img src="~/assets/img/banner/bn-arrow.png" class="vid__arrow" alt="img">
              <a 
              @click="playVideo(videoUrl)" :style="{ cursor: 'pointer' }" 
                class="video__80 video-btn">
                <i class="bi bi-play-fill"></i>
              </a>
              <span class="proces">
                Work
                Process
              </span>
            </div>
          </div>
        </div>
        <div class="col-lg-4">
          <div class="banner__thumb" data-aos="fade-up-right" data-aos-duration="300">
            <img src="~/assets/img/banner/banner-man.png" alt="man-img">
          </div>
        </div>
      </div>
    </div>
    <div class="banner__leftinfo">
      <div class="left__infomobile">
        <a href="#">
          <img src="~/assets/img/banner/dial.png" alt="img">
        </a>
        <a href="#">
          (+02)-574-328-301
        </a>
      </div>
      <div class="right__infoscroll">
        <a href="#prot" class="scroll">
          scroll down
        </a>
        <a href="#prot" class="scroll__bar">
          <img src="~/assets/img/banner/scroll-down.png" alt="img">
        </a>
      </div>
    </div>
    <div class="banner__rightinfo">
      <div class="right__infoscroll">
        <a href="#" class="scroll">
          Follow Me
        </a>
        <a href="#" class="scroll__bar">
          <img src="~/assets/img/banner/scroll-down.png" alt="img">
        </a>
      </div>
      <div class="banner__xlsocial">
        <ul class="banner__soci d-grid justify-content-center">
          <li>
            <NuxtLink to="https://www.facebook.com" target="_blank">
              <i class="bi bi-facebook"></i>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink to="https://www.twitter.com" target="_blank">
              <i class="bi bi-twitter"></i>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink to="https://www.instagram.com" target="_blank">
              <i class="bi bi-instagram"></i>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink to="https://www.globe.com" target="_blank">
              <i class="bi bi-globe"></i>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink to="https://www.linkedin.com" target="_blank">
              <i class="bi bi-linkedin"></i>
            </NuxtLink>
          </li>
        </ul>
      </div>
    </div>
  </section>
  <!-- banner  -->

  <CommonVideoModal ref="video_modal" video-url="https://www.youtube.com/embed/7e90gBu4pas" />

</template>
 