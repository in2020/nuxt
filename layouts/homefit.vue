<template>
  <div>
    <header class="hf_layout_header uk-navbar" uk-navbar="">
      <div class="hf_layout_core_wrap hf_layout_header_wrap">
        <a href="/aaa"><img src="https://www.homefit.co.kr/static/img/common/header/homefit.black.png?rev=0.012c" class="hf_header_homefit" alt="HOMEFIT"></a>
        <nav class="hf_layout_header_nav">
          <ul>
            <!-- <li>
              <a href="/group/">기업/단체레슨</a>
            </li> -->
            <li>
              <a href="/user/login/">로그인</a>
            </li>
            <li>
              <a href="/user/register/">회원가입</a>
            </li>
            <li>
              <a href="/coach/">코치지원</a>
            </li>
          </ul>
          <span class="hf_search_button hf_function_popup_search">체험하기</span>

          <!--//<span class="hf_search_button" onclick="location.href='/suggest'">체험하기</span>-->
          <!-- a href="/user/register/" class="hf_register_button">회원가입</a -->
          <!-- button class="hf_profile_button" type="button">
            <span class="hf_main_menu_icon" uk-icon="icon: menu; ratio: 1"></span>
          </button>
            <div class="hf_guest_wrap" uk-drop="mode: click; pos: bottom-right">
              <div class="uk-card uk-card-small uk-card-body uk-card-default">
                  <ul class="hf_guest_menu">
                    <a href="/user/login/"><li>로그인</li></a>
                    <li class="hr"></li>
                    <a href="/user/register/"><li>회원가입</li></a>
                  </ul>
              </div>
            </div -->
        </nav>
        <div class="hf_layout_header_mobile">
          <div class="hf_menu_button_mobile">
            <span class="hf_menu_button uk-icon" uk-icon="icon: menu; ratio: 1.2"><svg width="24" height="24" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"> <rect x="2" y="4" width="16" height="1"></rect> <rect x="2" y="9" width="16" height="1"></rect> <rect x="2" y="14" width="16" height="1"></rect></svg></span>
          </div>
          <div class="hf_search_button_mobile">
            <span class="hf_search_button hf_function_popup_search">체험하기</span>
            <!--//<span class="hf_search_button" onclick="location.href='/suggest'">체험하기</span>-->
          </div>
        </div>
      </div>
    </header>
    <nuxt />
    <footer class="hf_layout_footer">
      <div class="hf_layout_core_wrap">
        <h1><img src="/static/img/common/footer/logo.png?rev=" class="hf_footer_logo" alt=""></h1>
        <ul class="hf_channel">
          <li>
            <a href="https://blog.naver.com/homefit_coach" target="new">
              <i class="fas fa-rss-square"></i>
              블로그
            </a>
          </li>
          <li>
            <a href="https://www.instagram.com/homefit_coach/" target="new">
              <i class="fab fa-instagram"></i>
              인스타그램
            </a>
          </li>
          <li>
            <a href="https://www.facebook.com/homefit89/" target="new">
              <i class="fab fa-facebook-square"></i>
              페이스북
            </a>
          </li>
        </ul>
        <ul class="hf_submenu">
          <li><a href="/docs/usage/">이용약관</a></li> |
          <li><a href="/docs/privacy/">개인정보취급방침</a></li> |
          <li><a href="/guide/">이용방법</a></li> |
          <li><a href="/listings/">프로그램 검색</a></li>
        </ul>
        <p>
          상호명 (주)홈핏 ㅣ 대표 엄선진<br>
          사업자등록번호 617-86-27572 (홈핏 스튜디오:158-60-00244) | <a href="http://www.ftc.go.kr/www/bizCommView.do?key=232&amp;apv_perm_no=2017310018430200112&amp;pageUnit=10&amp;searchCnd=wrkr_no&amp;searchKrwd=6178627572&amp;pageIndex=1" target="new">사업자정보확인</a><br>
          통신판매신고번호 제2017-서울노원-0112호<br>
          서울시 강남구 테헤란로410 금강타워 1502호 (주)홈핏<br>
          전화문의 02-6958-8253 | 카카오톡 플친 ID. 홈핏<br>
          이메일 | help@homefit.co.kr<br>
          © 2017 HOMEFIT Inc. All rights reserved.<br>
        </p>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data () {
    return {
    }
  }
}
</script>
