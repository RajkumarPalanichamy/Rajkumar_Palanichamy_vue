
<script setup>

 
const props = defineProps({
  showSidebar: Boolean, 
  toggleActive: Function,
})   

</script>


<template>
  <!--<<  sub side bar custom >>-->
  <div :class="`subside__barmenu sub__contact ${showSidebar ? 'active' : ''}`">
    <div class="remove__click d-flex justify-content-center align-items-center">
      <i @click="toggleActive" class="bi bi-x-lg"></i>
    </div>
    <div class="sub__contact__wrapper d-grid">
      <NuxtLink to="/" class="side-logo">
        <img src="~/assets/img/logo/logo.png" alt="img">
      </NuxtLink>
      <p>
        Neque porro quisquam est, qui dolorem ipsum quia dolor sit consectetur, aliquam quaerats voluptatem. Ut enim ad
        minima veniam, exercitationem laboriosam, nisi ut aliquid ex ea autem velit esse quam nihil
      </p>
      <div class="sub__contact-left d-grid">
        <div class="sub__contac-item">
          <div class="content">
            <span class="address d-block">
              address
            </span>
            <span class="textp">
              Victoria Street London,
            </span>
          </div>
        </div>
        <div class="sub__contac-item">
          <div class="content">
            <span class="address d-block">
              email
            </span>
            <a href="mailto:matias999@.com" class="textp">
              matias999@.com
            </a>
          </div>
        </div>
        <div class="sub__contac-item">
          <div class="content">
            <span class="address d-block">
              call now
            </span>
            <a href="tel:+98 4758 2154 021" class="textp">
              +98 4758 2154 021
            </a>
          </div>
        </div>
      </div>
      <div class="sub__contact-right mb-80 position-relative">
        <ul class="social d-flex gap-3">
          <li>
            <NuxtLink target="_blank" to="https://www.facebook.com">
              <i class="bi bi-facebook"></i>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink target="_blank" to="https://www.twitter.com">
              <i class="bi bi-twitter"></i>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink target="_blank" to="https://www.linkedin.com">
              <i class="bi bi-linkedin"></i>
            </NuxtLink>
          </li>
          <li>
            <NuxtLink target="_blank" to="https://www.youtube.com">
              <i class="bi bi-youtube"></i>
            </NuxtLink>
          </li>
        </ul>
      </div>
      <a href="#" class="d-flex justify-content-center fw-500 cmn--btn align-items-center gap-2">
        <span>
          <i class="bi bi-chevron-right"></i>
        </span>
        <span class="get__text">
          Let's Talk
        </span>
      </a>
    </div>
  </div>
  <!--<<  sub side bar custom >>-->
</template>

 