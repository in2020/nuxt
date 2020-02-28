<template>
  <section class="hf_main_banner">
    <div class="hf_banner_wrap">
      <div class="hf_intro_movie">
        <video poster="//cdn.homefit.co.kr/movie/main/movie009.jpg" id="movie002" playsinline="" muted="" loop="" preload="true" controlslist="nodownload">
          <source src="//cdn.homefit.co.kr/movie/main/movie009.mp4" type="video/mp4">
        </video>
      </div>
      <div class="hf_banner_content_box">
        <h1>헬스장보다 집이 더 편하니까</h1>
        <h2>원하는 시간에, 원하는 장소로<br>검증된 코치가 찾아갑니다</h2>
        <nuxt-link to="/bbb" class="hf_banner_search_button trial hf_function_popup_search">무료체험 심청하기</nuxt-link>
      </div>
    </div>
    <div class="hf_banner_movie_popup_button_wrap">
    </div>
    <div id="modal-media-video" class="uk-flex-top uk-modal" uk-modal="">
      <div class="uk-modal-dialog uk-width-auto uk-margin-auto-vertical">
        <button class="uk-modal-close-outside uk-close uk-icon" type="button" uk-close=""><svg width="14" height="14" viewBox="0 0 14 14" xmlns="http://www.w3.org/2000/svg"><line fill="none" stroke="#000" stroke-width="1.1" x1="1" y1="1" x2="13" y2="13"></line><line fill="none" stroke="#000" stroke-width="1.1" x1="13" y1="1" x2="1" y2="13"></line></svg></button>
      </div>
    </div>
  </section>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'
import homefit from "../layouts/homefit";

export default {
  layout: 'homefit'
}
</script>
