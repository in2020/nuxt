<template>
  <div class="hf_layout_main_wrapper suggest">

    <input type="checkbox" name="is_recommend" id="is_recommend" style="display: none;">
    <input type="text" name="sort" style="display: none;" value="1">

    <div class="top_banner" style="background-image:url('/static/img/form/search_request/main_banner.jpg?rev=0.012c');">
      <h1><span>&nbsp;</span><strong>나에게 맞는</strong> 프로그램은?<br>
        <span id="top_banner_sub">아래 항목을 입력해주시면 딱 맞는 프로그램 추천해드립니다.</span></h1>
    </div>
    <style>
      #top_banner_sub{display:none;}
      .hf_form_wrap div.form{margin-bottom:10px;}
      .hf_form_wrap{background-color:#fff;}
      .search_request{position:relative;}
      .pii_back{background:#f0f0f0;width:100%;height:100%;position:absolute;top:0px;left:0px;text-align:center;overflow:hidden;}
      .pii_layer_tt{padding-top:100px;font-size:30px;line-height:37px;color:#000;letter-spacing:-1.5px;}
      .pii_layer_tt span{font-weight:bold;}
      .pii_layer_sub{color:#aeaeae;padding-top:30px;padding-bottom:70px;}
      .pii_layer_sub span{font-weight:bold;text-decoration:underline;cursor:pointer;}
      .pii_layer_start{width:220px;height:60px;line-height:60px;font-size:18px;color:#c49a70;border:solid #c49a70 1px;border-radius:50px;margin:0 auto;font-weight:bold;cursor:pointer;}
      .pii_layer_bar{width:1px;height:150px;background:#c49a70;margin:0 auto;}

      .pii_sub_box{max-width:1024px;width:auto;margin:0 auto;padding-bottom:70px}
      .pii_sub_text{color:#000;font-size:14px;padding-bottom:50px;}
      .pii_sub_text a{font-weight:bold;text-decoration:underline;}
      .pii_sub_img{width:100%;padding-bottom:30px;display:block;}
      .pii_sub_img img{width:100%;}

      .pii_sub_img_mobile{display:none;}
      @media screen and (max-width: 1440px){
        .pii_sub_box {max-width:928px;}
      }
      @media screen and (max-width: 1024px){
        .pii_sub_box {
          max-width: 92%;
        }
      }
      @media screen and (max-width: 768px){
        .pii_sub_box {
          margin: 0;
          max-width: 100%;
          padding: 5px 15px;
        }
        .pii_layer_tt{padding-top:100px;font-size:22px;line-height:29px;color:#000;}
        .pii_layer_sub{padding-left:45px;padding-right:45px}

        .pii_sub_img{display:none;}
        .pii_sub_img_mobile{max-width: 100%;padding: 5px 15px;padding-bottom:50px;display:block;}
        .pii_sub_img_mobile img{width:100%;}
      }
    </style>

    <script>
      $(document).ready(function(){
        $('.pii_layer_start').click(function(){
          $('.pii_back').hide();
          $('.pii_sub_box').hide();
          $('#top_banner_sub').show();
          $('.hf_form_wrap').css('background-color','#f3f3f3');
          $('.hf_form_wrap div.form').css('margin-bottom','40px');
        });

        $('.show_sch_box').click(function(){
          if($('.mobile-indicator-max-1024').css("display") == "block") {
            $('.hf_global_popup_search_elements.hf_global_popup_search_box').css({"top" : $(window).scrollTop() + 40 + "px"});
          } else {
            $('.hf_global_popup_search_elements.hf_global_popup_search_box').css({"top" : $(window).scrollTop() + 160 + "px"});
          }
          $('.hf_global_popup_search_elements').show();
          $('.hf_search_step_1').css("height", "auto");
          $('.hf_search_step_1').show();
          $('.hf_global_popup_search_elements .hf_search_popup_close').removeClass('for_step_0');
          $('.hf_global_popup_search_elements .hf_search_step_back_btn').css('display','none');
          $('.hf_global_popup_search_elements .hf_search_step_0').css("height", "0px");
          $('.hf_global_popup_search_elements .hf_search_step_1').css("height", "auto");
          $('.hf_global_popup_search_elements .hf_search_step_2').css("height", "0px");
          $('.hf_global_popup_search_elements.hf_global_popup_search_box').css("background-color", "#ffffff");
        });
      });
    </script>
    <div class="hf_form_wrap">
      <div class="hf_layout_core_wrap">

        <div class="form search_request">
          <div class="pii_back">
            <div class="pii_layer_tt">아래 신청서를 작성해주시면<br><span>만족도가 높았던 우수 코치님을</span><br>우선적으로 배정해드리겠습니다.</div>
            <div class="pii_layer_sub">코치님을 직접 검색하고 싶으신 경우 <span class="show_sch_box">여기</span>를 눌러주세요.</div>
            <div class="pii_layer_start"> 지금 시작하기</div>
            <div class="pii_layer_bar"></div>
          </div>

          <div class="progress-bar">
            <div class="progress" style="width: 10%;"></div>
          </div>




          <!-- h1 class="title">코치 배정 요청서</h1 -->
          <form id="form_suggest" action="/form/search_request/ajax_submit.php" method="POST" target="_blank" class="container">
            <input name="ref_url" type="hidden" value="https://homefit.co.kr/">
            <input type="hidden" class="hf_form_hidden_completed" name="completed" value="">

            <div class="wrap flow_1" style="">
              <p class="title">운동 목적이 어떻게 되세요? (복수 선택 가능)</p>
              <div class="border checkbox">
                <span><input class="input flow_1" name="data_1" type="checkbox" value="1,2"> 몸매관리 (다이어트, 근력향상)</span>
                <span><input class="input flow_1" name="data_1" type="checkbox" value="4"> 바른체형/신체 정렬</span>
                <span><input class="input flow_1" name="data_1" type="checkbox" value="3"> 스트레스 해소</span>
                <span><input class="input flow_1" name="data_1" type="checkbox" value="5"> 산전 전문 관리</span>
                <span><input class="input flow_1" name="data_1" type="checkbox" value="6"> 산후 전문 관리</span>
                <span><input class="input flow_1" name="data_1" type="checkbox" value="7"> 중증의 통증케어/기능회복</span>
              </div>
              <div class="message"></div>
            </div>
            <div class="wrap flow_2" style="display: none;">
              <p class="title">임신하신지 얼마나 되셨어요? (주 단위로 입력)
                <small class="sub-title">안정기 (임신 16주) 이전에는 전문의의 소견을 받은 후
                  운동을 권장하고 있습니다.
                </small>
              </p>

              <div class="text">
                <input type="text" name="data_2" class="input flow_2" id="" placeholder="ex) 20주">
              </div>
              <div class="message"></div>
            </div>
            <div class="wrap flow_3" style="display: none;">
              <p class="title">출산하신지 얼마나 되셨어요?
                <small class="sub-title">홈핏 산후 전문 프로그램은 산후 6주~5개월까지 권장하고
                  있습니다.
                </small>
              </p>
              <div class="border checkbox">
                <span class=""><input class="input flow_3" name="data_3" type="radio" value="1"> 출산한지 5개월 이전 입니다.</span>
                <span><input class="input flow_3" name="data_3" type="radio" value="2"> 출산한지 5개월 이후 입니다.</span>
              </div>
              <div class="empty"></div>
              <p class="title">구체적으로 출산하신지 얼마나 되셨어요? (주 단위로 입력)</p>
              <div class="text">
                <input type="text" name="data_4" class="input flow_3" id="" placeholder="ex) 8주">
              </div>
              <div class="message"></div>
            </div>
            <div class="wrap flow_4" style="display: none;">
              <p class="title">선호하는 운동 종목이 있으신가요? (복수 선택 가능)</p>
              <div class="border checkbox">
                <span><input class="input flow_4" name="data_5" type="checkbox" value="1"> 요가</span>
                <span><input class="input flow_4" name="data_5" type="checkbox" value="2"> 필라테스</span>
                <span><input class="input flow_4" name="data_5" type="checkbox" value="3"> 웨이트</span>
                <span><input class="input flow_4" name="data_5" type="checkbox" value="0"> 무관</span>
              </div>
              <div class="message"></div>
            </div>
            <div class="wrap flow_5" style="display: none;">
              <p class="title">원하는 수업 형태
                <small class="sub-title">4인 이상 단체레슨은 <a href="/group" style="text-decoration: underline;">기업/단체
                  페이지</a>에서 신청해주세요.
                </small>
              </p>
              <div class="border checkbox">
                <span class=""><input class="input flow_5" name="data_6" type="radio" value="1"> 개인 레슨</span>
                <span><input class="input flow_5" name="data_6" type="radio" value="2"> 2인 그룹 레슨</span>
                <span><input class="input flow_5" name="data_6" type="radio" value="3"> 3인 그룹 레슨</span>
              </div>
              <div class="flow_5 more" style="display: none;">
                <div class="empty"></div>
                <p class="title">함께 수업 받으시는 분의 연령대와 성별, 관계를 기재해주세요.</p>
                <div class="text">
                  <input type="text" name="data_7" class="input flow_5" id="" placeholder="ex) 30대 여성 (자매)">
                </div>
              </div>
              <div class="message"></div>
            </div>
            <div class="wrap flow_6" style="display: none;">
              <div class="empty"></div>
              <p class="title">수업 가능 요일 및 시간
                <small class="sub-title">가능한 요일 및 시간을 모두 입력해주세요. 구체적일수록
                  좋습니다.
                </small>
              </p>

              <div class="schedule">
                <p class="title">요일</p>
                <div id="button">
                  <div style="margin-bottom: 20px">
                    <button type="button" data-toggle="add-timetable" data-value="mon">월</button>
                    <button type="button" data-toggle="add-timetable" data-value="tue">화</button>
                    <button type="button" data-toggle="add-timetable" data-value="wed">수</button>
                    <button type="button" data-toggle="add-timetable" data-value="thu">목</button>
                    <button type="button" data-toggle="add-timetable" data-value="fri">금</button>
                    <button type="button" data-toggle="add-timetable" data-value="sat">토</button>
                    <button type="button" data-toggle="add-timetable" data-value="sun">일</button>
                  </div>
                  <div style="margin-bottom: 20px">
                    <button type="button" data-toggle="add-timetable" data-value="wek">주중</button>
                    <button type="button" data-toggle="add-timetable" data-value="end">주말</button>
                  </div>
                  <div>
                    <button type="button" data-toggle="add-timetable" data-value="all">모든 요일
                    </button>
                  </div>
                </div>

                <p class="title">시간</p>

                <div style="display: inline-block; width: 100%;" id="timetable">
                  <div class="timetable-wrap" data-value="mon" style="display: none;">
                    <div class="timetable">
                      <p class="title">
                        월
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="mon" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="mon" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="mon" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="mon" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="mon" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="mon" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>
                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="tue" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        화
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="tue" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="tue" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="tue" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="tue" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="tue" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="tue" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="wed" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        수
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wed" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wed" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wed" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wed" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wed" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wed" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="thu" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        목
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="thu" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="thu" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="thu" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="thu" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="thu" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="thu" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="fri" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        금
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="fri" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="fri" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="fri" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="fri" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="fri" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="fri" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="sat" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        토
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sat" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sat" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sat" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sat" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sat" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sat" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="sun" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        일
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sun" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sun" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sun" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sun" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sun" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="sun" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="wek" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        주중
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wek" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wek" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wek" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wek" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wek" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="wek" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="end" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        주말
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="end" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="end" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="end" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="end" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="end" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="end" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                  <div class="timetable-wrap" data-value="all" style="display: none;">
                    <div class="timetable">

                      <p class="title">
                        모든 요일
                        <i class="xi-close" style="float: right;"></i>
                      </p>
                      <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택 가능)</p>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="all" value="1">
                        <span class="text">이른 오전 (9시 이전)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="all" value="2">
                        <span class="text">늦은 오전 (9시~12시)</span>
                      </div>

                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="all" value="3">
                        <span class="text">이른 오후 (12시~15시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="all" value="4">
                        <span class="text">늦은 오후 (15시~18시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="all" value="5">
                        <span class="text">이른 저녁 (18시~21시)</span>
                      </div>
                      <div class="yp-checkbox">
                        <input type="checkbox" name="data_8" class="uk-checkbox" data-value="all" value="6">
                        <span class="text">늦은 저녁 (21시 이후)</span>
                      </div>

                    </div>
                  </div>
                </div>
              </div>
              <div class="message"></div>
            </div>
            <div class="wrap flow_7" style="display: none;">
              <p class="title">
                지역
                <span style="float: right; font-size: 70%; text-decoration:underline; cursor: pointer;" id="flow_7_region" onclick="$('#id01').fadeIn(300);">가능 지역 확인하기</span>
              </p>
              <div class="select">
                <select name="data_9" style="width: 100px;">
                  <option value="0">시/도</option>
                  <option value="서울">서울</option>              <option value="경기">경기</option>              <option value="인천">인천</option>              <option value="부산">부산</option>              <option value="대구">대구</option>              <option value="대전">대전</option>              <option value="광주">광주</option>              <option value="울산">울산</option>              <option value="세종">세종</option>              <option value="경남">경남</option>              <option value="경북">경북</option>              <option value="충남">충남</option>              <option value="충북">충북</option>              <option value="전남">전남</option>              <option value="전북">전북</option>              <option value="강원">강원</option>              <option value="제주">제주</option>                            </select>
                <select name="data_10" style="width: 160px;">
                  <option value="0">상세지역</option>
                  <span><option value="서울 강남구" class="depth_1_id_서울" style="display: none;">강남구</option></span>              <span><option value="서울 강동구" class="depth_1_id_서울" style="display: none;">강동구</option></span>              <span><option value="서울 강북구" class="depth_1_id_서울" style="display: none;">강북구</option></span>              <span><option value="서울 강서구" class="depth_1_id_서울" style="display: none;">강서구</option></span>              <span><option value="서울 관악구" class="depth_1_id_서울" style="display: none;">관악구</option></span>              <span><option value="서울 광진구" class="depth_1_id_서울" style="display: none;">광진구</option></span>              <span><option value="서울 구로구" class="depth_1_id_서울" style="display: none;">구로구</option></span>              <span><option value="서울 금천구" class="depth_1_id_서울" style="display: none;">금천구</option></span>              <span><option value="서울 노원구" class="depth_1_id_서울" style="display: none;">노원구</option></span>              <span><option value="서울 도봉구" class="depth_1_id_서울" style="display: none;">도봉구</option></span>              <span><option value="서울 동대문구" class="depth_1_id_서울" style="display: none;">동대문구</option></span>              <span><option value="서울 동작구" class="depth_1_id_서울" style="display: none;">동작구</option></span>              <span><option value="서울 마포구" class="depth_1_id_서울" style="display: none;">마포구</option></span>              <span><option value="서울 서대문구" class="depth_1_id_서울" style="display: none;">서대문구</option></span>              <span><option value="서울 서초구" class="depth_1_id_서울" style="display: none;">서초구</option></span>              <span><option value="서울 성동구" class="depth_1_id_서울" style="display: none;">성동구</option></span>              <span><option value="서울 성북구" class="depth_1_id_서울" style="display: none;">성북구</option></span>              <span><option value="서울 송파구" class="depth_1_id_서울" style="display: none;">송파구</option></span>              <span><option value="서울 양천구" class="depth_1_id_서울" style="display: none;">양천구</option></span>              <span><option value="서울 영등포구" class="depth_1_id_서울" style="display: none;">영등포구</option></span>              <span><option value="서울 용산구" class="depth_1_id_서울" style="display: none;">용산구</option></span>              <span><option value="서울 은평구" class="depth_1_id_서울" style="display: none;">은평구</option></span>              <span><option value="서울 종로구" class="depth_1_id_서울" style="display: none;">종로구</option></span>              <span><option value="서울 중구" class="depth_1_id_서울" style="display: none;">중구</option></span>              <span><option value="서울 중랑구" class="depth_1_id_서울" style="display: none;">중랑구</option></span>              <span><option value="경기 가평군" class="depth_1_id_경기" style="display: none;">가평군</option></span>              <span><option value="경기 고양시" class="depth_1_id_경기" style="display: none;">고양시</option></span>              <span><option value="경기 과천시" class="depth_1_id_경기" style="display: none;">과천시</option></span>              <span><option value="경기 광명시" class="depth_1_id_경기" style="display: none;">광명시</option></span>              <span><option value="경기 광주시" class="depth_1_id_경기" style="display: none;">광주시</option></span>              <span><option value="경기 구리시" class="depth_1_id_경기" style="display: none;">구리시</option></span>              <span><option value="경기 군포시" class="depth_1_id_경기" style="display: none;">군포시</option></span>              <span><option value="경기 김포시" class="depth_1_id_경기" style="display: none;">김포시</option></span>              <span><option value="경기 남양주시" class="depth_1_id_경기" style="display: none;">남양주시</option></span>              <span><option value="경기 동두천시" class="depth_1_id_경기" style="display: none;">동두천시</option></span>              <span><option value="경기 부천시" class="depth_1_id_경기" style="display: none;">부천시</option></span>              <span><option value="경기 성남시" class="depth_1_id_경기" style="display: none;">성남시</option></span>              <span><option value="경기 수원시" class="depth_1_id_경기" style="display: none;">수원시</option></span>              <span><option value="경기 시흥시" class="depth_1_id_경기" style="display: none;">시흥시</option></span>              <span><option value="경기 안산시" class="depth_1_id_경기" style="display: none;">안산시</option></span>              <span><option value="경기 안성시" class="depth_1_id_경기" style="display: none;">안성시</option></span>              <span><option value="경기 안양시" class="depth_1_id_경기" style="display: none;">안양시</option></span>              <span><option value="경기 양주시" class="depth_1_id_경기" style="display: none;">양주시</option></span>              <span><option value="경기 양평군" class="depth_1_id_경기" style="display: none;">양평군</option></span>              <span><option value="경기 여주시" class="depth_1_id_경기" style="display: none;">여주시</option></span>              <span><option value="경기 연천군" class="depth_1_id_경기" style="display: none;">연천군</option></span>              <span><option value="경기 오산시" class="depth_1_id_경기" style="display: none;">오산시</option></span>              <span><option value="경기 용인시" class="depth_1_id_경기" style="display: none;">용인시</option></span>              <span><option value="경기 의왕시" class="depth_1_id_경기" style="display: none;">의왕시</option></span>              <span><option value="경기 의정부시" class="depth_1_id_경기" style="display: none;">의정부시</option></span>              <span><option value="경기 이천시" class="depth_1_id_경기" style="display: none;">이천시</option></span>              <span><option value="경기 파주시" class="depth_1_id_경기" style="display: none;">파주시</option></span>              <span><option value="경기 평택시" class="depth_1_id_경기" style="display: none;">평택시</option></span>              <span><option value="경기 포천시" class="depth_1_id_경기" style="display: none;">포천시</option></span>              <span><option value="경기 하남시" class="depth_1_id_경기" style="display: none;">하남시</option></span>              <span><option value="경기 화성시" class="depth_1_id_경기" style="display: none;">화성시</option></span>              <span><option value="인천 강화군" class="depth_1_id_인천" style="display: none;">강화군</option></span>              <span><option value="인천 계양구" class="depth_1_id_인천" style="display: none;">계양구</option></span>              <span><option value="인천 미추홀구(남구)" class="depth_1_id_인천" style="display: none;">미추홀구(남구)</option></span>              <span><option value="인천 남동구" class="depth_1_id_인천" style="display: none;">남동구</option></span>              <span><option value="인천 동구" class="depth_1_id_인천" style="display: none;">동구</option></span>              <span><option value="인천 부평구" class="depth_1_id_인천" style="display: none;">부평구</option></span>              <span><option value="인천 서구" class="depth_1_id_인천" style="display: none;">서구</option></span>              <span><option value="인천 연수구" class="depth_1_id_인천" style="display: none;">연수구</option></span>              <span><option value="인천 옹진군" class="depth_1_id_인천" style="display: none;">옹진군</option></span>              <span><option value="인천 중구" class="depth_1_id_인천" style="display: none;">중구</option></span>              <span><option value="부산 강서구" class="depth_1_id_부산" style="display: none;">강서구</option></span>              <span><option value="부산 금정구" class="depth_1_id_부산" style="display: none;">금정구</option></span>              <span><option value="부산 기장군" class="depth_1_id_부산" style="display: none;">기장군</option></span>              <span><option value="부산 남구" class="depth_1_id_부산" style="display: none;">남구</option></span>              <span><option value="부산 동구" class="depth_1_id_부산" style="display: none;">동구</option></span>              <span><option value="부산 동래구" class="depth_1_id_부산" style="display: none;">동래구</option></span>              <span><option value="부산 부산진구" class="depth_1_id_부산" style="display: none;">부산진구</option></span>              <span><option value="부산 북구" class="depth_1_id_부산" style="display: none;">북구</option></span>              <span><option value="부산 사상구" class="depth_1_id_부산" style="display: none;">사상구</option></span>              <span><option value="부산 사하구" class="depth_1_id_부산" style="display: none;">사하구</option></span>              <span><option value="부산 서구" class="depth_1_id_부산" style="display: none;">서구</option></span>              <span><option value="부산 수영구" class="depth_1_id_부산" style="display: none;">수영구</option></span>              <span><option value="부산 연제구" class="depth_1_id_부산" style="display: none;">연제구</option></span>              <span><option value="부산 영도구" class="depth_1_id_부산" style="display: none;">영도구</option></span>              <span><option value="부산 중구" class="depth_1_id_부산" style="display: none;">중구</option></span>              <span><option value="부산 해운대구" class="depth_1_id_부산" style="display: none;">해운대구</option></span>              <span><option value="대구 중구" class="depth_1_id_대구" style="display: none;">중구</option></span>              <span><option value="대구 동구" class="depth_1_id_대구" style="display: none;">동구</option></span>              <span><option value="대구 서구" class="depth_1_id_대구" style="display: none;">서구</option></span>              <span><option value="대구 남구" class="depth_1_id_대구" style="display: none;">남구</option></span>              <span><option value="대구 북구" class="depth_1_id_대구" style="display: none;">북구</option></span>              <span><option value="대구 수성구" class="depth_1_id_대구" style="display: none;">수성구</option></span>              <span><option value="대구 달서구" class="depth_1_id_대구" style="display: none;">달서구</option></span>              <span><option value="대구 달성군" class="depth_1_id_대구" style="display: none;">달성군</option></span>              <span><option value="대전 대덕구" class="depth_1_id_대전" style="display: none;">대덕구</option></span>              <span><option value="대전 동구" class="depth_1_id_대전" style="display: none;">동구</option></span>              <span><option value="대전 서구" class="depth_1_id_대전" style="display: none;">서구</option></span>              <span><option value="대전 유성구" class="depth_1_id_대전" style="display: none;">유성구</option></span>              <span><option value="대전 중구" class="depth_1_id_대전" style="display: none;">중구</option></span>              <span><option value="울산 남구" class="depth_1_id_울산" style="display: none;">남구</option></span>              <span><option value="울산 동구" class="depth_1_id_울산" style="display: none;">동구</option></span>              <span><option value="울산 북구" class="depth_1_id_울산" style="display: none;">북구</option></span>              <span><option value="울산 울주군" class="depth_1_id_울산" style="display: none;">울주군</option></span>              <span><option value="울산 중구" class="depth_1_id_울산" style="display: none;">중구</option></span>              <span><option value="세종 세종시" class="depth_1_id_세종" style="display: none;">세종시</option></span>              <span><option value="충남 계룡시" class="depth_1_id_충남" style="display: none;">계룡시</option></span>              <span><option value="충남 공주시" class="depth_1_id_충남" style="display: none;">공주시</option></span>              <span><option value="충남 금산군" class="depth_1_id_충남" style="display: none;">금산군</option></span>              <span><option value="충남 논산시" class="depth_1_id_충남" style="display: none;">논산시</option></span>              <span><option value="충남 당진시" class="depth_1_id_충남" style="display: none;">당진시</option></span>              <span><option value="충남 보령시" class="depth_1_id_충남" style="display: none;">보령시</option></span>              <span><option value="충남 부여군" class="depth_1_id_충남" style="display: none;">부여군</option></span>              <span><option value="충남 서산시" class="depth_1_id_충남" style="display: none;">서산시</option></span>              <span><option value="충남 서천군" class="depth_1_id_충남" style="display: none;">서천군</option></span>              <span><option value="충남 아산시" class="depth_1_id_충남" style="display: none;">아산시</option></span>              <span><option value="충남 예산군" class="depth_1_id_충남" style="display: none;">예산군</option></span>              <span><option value="충남 천안시" class="depth_1_id_충남" style="display: none;">천안시</option></span>              <span><option value="충남 청양군" class="depth_1_id_충남" style="display: none;">청양군</option></span>              <span><option value="충남 태안군" class="depth_1_id_충남" style="display: none;">태안군</option></span>              <span><option value="충남 홍성군" class="depth_1_id_충남" style="display: none;">홍성군</option></span>              <span><option value="충북 괴산군" class="depth_1_id_충북" style="display: none;">괴산군</option></span>              <span><option value="충북 단양군" class="depth_1_id_충북" style="display: none;">단양군</option></span>              <span><option value="충북 보은군" class="depth_1_id_충북" style="display: none;">보은군</option></span>              <span><option value="충북 영동군" class="depth_1_id_충북" style="display: none;">영동군</option></span>              <span><option value="충북 옥천군" class="depth_1_id_충북" style="display: none;">옥천군</option></span>              <span><option value="충북 음성군" class="depth_1_id_충북" style="display: none;">음성군</option></span>              <span><option value="충북 제천시" class="depth_1_id_충북" style="display: none;">제천시</option></span>              <span><option value="충북 증평군" class="depth_1_id_충북" style="display: none;">증평군</option></span>              <span><option value="충북 진천군" class="depth_1_id_충북" style="display: none;">진천군</option></span>              <span><option value="충북 청주시" class="depth_1_id_충북" style="display: none;">청주시</option></span>              <span><option value="충북 충주시" class="depth_1_id_충북" style="display: none;">충주시</option></span>              <span><option value="경북 경산시" class="depth_1_id_경북" style="display: none;">경산시</option></span>              <span><option value="경북 경주시" class="depth_1_id_경북" style="display: none;">경주시</option></span>              <span><option value="경북 고령군" class="depth_1_id_경북" style="display: none;">고령군</option></span>              <span><option value="경북 구미시" class="depth_1_id_경북" style="display: none;">구미시</option></span>              <span><option value="경북 군위군" class="depth_1_id_경북" style="display: none;">군위군</option></span>              <span><option value="경북 김천시" class="depth_1_id_경북" style="display: none;">김천시</option></span>              <span><option value="경북 문경시" class="depth_1_id_경북" style="display: none;">문경시</option></span>              <span><option value="경북 봉화군" class="depth_1_id_경북" style="display: none;">봉화군</option></span>              <span><option value="경북 상주시" class="depth_1_id_경북" style="display: none;">상주시</option></span>              <span><option value="경북 성주군" class="depth_1_id_경북" style="display: none;">성주군</option></span>              <span><option value="경북 안동시" class="depth_1_id_경북" style="display: none;">안동시</option></span>              <span><option value="경북 영덕군" class="depth_1_id_경북" style="display: none;">영덕군</option></span>              <span><option value="경북 영양군" class="depth_1_id_경북" style="display: none;">영양군</option></span>              <span><option value="경북 영주시" class="depth_1_id_경북" style="display: none;">영주시</option></span>              <span><option value="경북 영천시" class="depth_1_id_경북" style="display: none;">영천시</option></span>              <span><option value="경북 예천군" class="depth_1_id_경북" style="display: none;">예천군</option></span>              <span><option value="경북 울릉군" class="depth_1_id_경북" style="display: none;">울릉군</option></span>              <span><option value="경북 울진군" class="depth_1_id_경북" style="display: none;">울진군</option></span>              <span><option value="경북 의성군" class="depth_1_id_경북" style="display: none;">의성군</option></span>              <span><option value="경북 청도군" class="depth_1_id_경북" style="display: none;">청도군</option></span>              <span><option value="경북 청송군" class="depth_1_id_경북" style="display: none;">청송군</option></span>              <span><option value="경북 칠곡군" class="depth_1_id_경북" style="display: none;">칠곡군</option></span>              <span><option value="경북 포항시" class="depth_1_id_경북" style="display: none;">포항시</option></span>              <span><option value="광주 광산구" class="depth_1_id_광주" style="display: none;">광산구</option></span>              <span><option value="광주 남구" class="depth_1_id_광주" style="display: none;">남구</option></span>              <span><option value="광주 동구" class="depth_1_id_광주" style="display: none;">동구</option></span>              <span><option value="광주 북구" class="depth_1_id_광주" style="display: none;">북구</option></span>              <span><option value="광주 서구" class="depth_1_id_광주" style="display: none;">서구</option></span>              <span><option value="강원 강릉시" class="depth_1_id_강원" style="display: none;">강릉시</option></span>              <span><option value="강원 고성군" class="depth_1_id_강원" style="display: none;">고성군</option></span>              <span><option value="강원 동해시" class="depth_1_id_강원" style="display: none;">동해시</option></span>              <span><option value="강원 삼척시" class="depth_1_id_강원" style="display: none;">삼척시</option></span>              <span><option value="강원 속초시" class="depth_1_id_강원" style="display: none;">속초시</option></span>              <span><option value="강원 양구군" class="depth_1_id_강원" style="display: none;">양구군</option></span>              <span><option value="강원 양양군" class="depth_1_id_강원" style="display: none;">양양군</option></span>              <span><option value="강원 영월군" class="depth_1_id_강원" style="display: none;">영월군</option></span>              <span><option value="강원 원주시" class="depth_1_id_강원" style="display: none;">원주시</option></span>              <span><option value="강원 인제군" class="depth_1_id_강원" style="display: none;">인제군</option></span>              <span><option value="강원 정선군" class="depth_1_id_강원" style="display: none;">정선군</option></span>              <span><option value="강원 철원군" class="depth_1_id_강원" style="display: none;">철원군</option></span>              <span><option value="강원 춘천시" class="depth_1_id_강원" style="display: none;">춘천시</option></span>              <span><option value="강원 태백시" class="depth_1_id_강원" style="display: none;">태백시</option></span>              <span><option value="강원 평창군" class="depth_1_id_강원" style="display: none;">평창군</option></span>              <span><option value="강원 홍천군" class="depth_1_id_강원" style="display: none;">홍천군</option></span>              <span><option value="강원 화천군" class="depth_1_id_강원" style="display: none;">화천군</option></span>              <span><option value="강원 횡성군" class="depth_1_id_강원" style="display: none;">횡성군</option></span>              <span><option value="경남 거제시" class="depth_1_id_경남" style="display: none;">거제시</option></span>              <span><option value="경남 거창군" class="depth_1_id_경남" style="display: none;">거창군</option></span>              <span><option value="경남 고성군" class="depth_1_id_경남" style="display: none;">고성군</option></span>              <span><option value="경남 김해시" class="depth_1_id_경남" style="display: none;">김해시</option></span>              <span><option value="경남 남해군" class="depth_1_id_경남" style="display: none;">남해군</option></span>              <span><option value="경남 밀양시" class="depth_1_id_경남" style="display: none;">밀양시</option></span>              <span><option value="경남 사천시" class="depth_1_id_경남" style="display: none;">사천시</option></span>              <span><option value="경남 산청군" class="depth_1_id_경남" style="display: none;">산청군</option></span>              <span><option value="경남 양산시" class="depth_1_id_경남" style="display: none;">양산시</option></span>              <span><option value="경남 의령군" class="depth_1_id_경남" style="display: none;">의령군</option></span>              <span><option value="경남 진주시" class="depth_1_id_경남" style="display: none;">진주시</option></span>              <span><option value="경남 창녕군" class="depth_1_id_경남" style="display: none;">창녕군</option></span>              <span><option value="경남 창원시" class="depth_1_id_경남" style="display: none;">창원시</option></span>              <span><option value="경남 통영시" class="depth_1_id_경남" style="display: none;">통영시</option></span>              <span><option value="경남 하동군" class="depth_1_id_경남" style="display: none;">하동군</option></span>              <span><option value="경남 함안군" class="depth_1_id_경남" style="display: none;">함안군</option></span>              <span><option value="경남 함양군" class="depth_1_id_경남" style="display: none;">함양군</option></span>              <span><option value="경남 합천군" class="depth_1_id_경남" style="display: none;">합천군</option></span>              <span><option value="전남 강진군" class="depth_1_id_전남" style="display: none;">강진군</option></span>              <span><option value="전남 고흥군" class="depth_1_id_전남" style="display: none;">고흥군</option></span>              <span><option value="전남 곡성군" class="depth_1_id_전남" style="display: none;">곡성군</option></span>              <span><option value="전남 광양시" class="depth_1_id_전남" style="display: none;">광양시</option></span>              <span><option value="전남 구례군" class="depth_1_id_전남" style="display: none;">구례군</option></span>              <span><option value="전남 나주시" class="depth_1_id_전남" style="display: none;">나주시</option></span>              <span><option value="전남 담양군" class="depth_1_id_전남" style="display: none;">담양군</option></span>              <span><option value="전남 목포시" class="depth_1_id_전남" style="display: none;">목포시</option></span>              <span><option value="전남 무안군" class="depth_1_id_전남" style="display: none;">무안군</option></span>              <span><option value="전남 보성군" class="depth_1_id_전남" style="display: none;">보성군</option></span>              <span><option value="전남 순천시" class="depth_1_id_전남" style="display: none;">순천시</option></span>              <span><option value="전남 신안군" class="depth_1_id_전남" style="display: none;">신안군</option></span>              <span><option value="전남 여수시" class="depth_1_id_전남" style="display: none;">여수시</option></span>              <span><option value="전남 영광군" class="depth_1_id_전남" style="display: none;">영광군</option></span>              <span><option value="전남 영암군" class="depth_1_id_전남" style="display: none;">영암군</option></span>              <span><option value="전남 완도군" class="depth_1_id_전남" style="display: none;">완도군</option></span>              <span><option value="전남 장성군" class="depth_1_id_전남" style="display: none;">장성군</option></span>              <span><option value="전남 장흥군" class="depth_1_id_전남" style="display: none;">장흥군</option></span>              <span><option value="전남 진도군" class="depth_1_id_전남" style="display: none;">진도군</option></span>              <span><option value="전남 함평군" class="depth_1_id_전남" style="display: none;">함평군</option></span>              <span><option value="전남 해남군" class="depth_1_id_전남" style="display: none;">해남군</option></span>              <span><option value="전남 화순군" class="depth_1_id_전남" style="display: none;">화순군</option></span>              <span><option value="전북 고창군" class="depth_1_id_전북" style="display: none;">고창군</option></span>              <span><option value="전북 군산시" class="depth_1_id_전북" style="display: none;">군산시</option></span>              <span><option value="전북 김제시" class="depth_1_id_전북" style="display: none;">김제시</option></span>              <span><option value="전북 남원시" class="depth_1_id_전북" style="display: none;">남원시</option></span>              <span><option value="전북 무주군" class="depth_1_id_전북" style="display: none;">무주군</option></span>              <span><option value="전북 부안군" class="depth_1_id_전북" style="display: none;">부안군</option></span>              <span><option value="전북 순창군" class="depth_1_id_전북" style="display: none;">순창군</option></span>              <span><option value="전북 완주군" class="depth_1_id_전북" style="display: none;">완주군</option></span>              <span><option value="전북 익산시" class="depth_1_id_전북" style="display: none;">익산시</option></span>              <span><option value="전북 임실군" class="depth_1_id_전북" style="display: none;">임실군</option></span>              <span><option value="전북 장수군" class="depth_1_id_전북" style="display: none;">장수군</option></span>              <span><option value="전북 전주시" class="depth_1_id_전북" style="display: none;">전주시</option></span>              <span><option value="전북 정읍시" class="depth_1_id_전북" style="display: none;">정읍시</option></span>              <span><option value="전북 진안군" class="depth_1_id_전북" style="display: none;">진안군</option></span>              <span><option value="제주 서귀포시" class="depth_1_id_제주" style="display: none;">서귀포시</option></span>              <span><option value="제주 제주시" class="depth_1_id_제주" style="display: none;">제주시</option></span>                            </select>
              </div>


              <div class="empty"></div>
              <p class="title">나머지 주소를 입력해주세요.</p>
              <div class="text">
                <input type="text" name="data_11" class="input flow_7" id="" placeholder="ex) 대치동 889-13 금강타워">
              </div>
              <!--                            </div>-->
              <div class="message"></div>
            </div>
            <div class="wrap flow_8" style="display: none;">
              <p class="title">성별
                <small class="sub-title">회원님과 동일한 성별의 코치님만 배정이 가능합니다. (단 부부나 커플 등의 그룹 레슨은 예외)</small>
              </p>
              <div class="border checkbox">
                                <span class="">
                                    <input class="input flow_8" name="data_12" type="radio" value="F">여성
                                </span>
                <span>
                                    <input class="input flow_8" name="data_12" type="radio" value="M"> 남성
                                </span>
              </div>

              <div class="empty"></div>
              <p class="title">연령대</p>
              <div class="border checkbox">
                                <span class="">
                                    <input class="input flow_8" name="data_13" type="radio" value="1">10대
                                </span>
                <span>
                                    <input class="input flow_8" name="data_13" type="radio" value="2"> 20대
                                </span>
                <span>
                                    <input class="input flow_8" name="data_13" type="radio" value="3"> 30대
                                </span>
                <span>
                                    <input class="input flow_8" name="data_13" type="radio" value="4"> 40대
                                </span>
                <span>
                                    <input class="input flow_8" name="data_13" type="radio" value="5"> 50대
                                </span>
                <span>
                                    <input class="input flow_8" name="data_13" type="radio" value="6"> 60대 이상
                                </span>
              </div>
              <div class="message"></div>
            </div>
            <div class="wrap flow_9" style="display: none;">
              <p class="title">과거에 수술 하셨던 이력이나 특별히 불편을 느끼는 곳이 있으신가요?</p>
              <div class="border checkbox">
                                <span class="">
                                    <input class="input flow_9" name="data_14" type="radio" value="1">네, 있습니다.
                                </span>
                <span>
                                    <input class="input flow_9" name="data_14" type="radio" value="2"> 아니요, 없습니다.
                                </span>
              </div>
              <div class="flow_9 more" style="display: none;">
                <div class="empty"></div>
                <p class="title">구체적으로 어떤 곳이 불편하세요?</p>
                <div class="text">
                  <input type="text" name="data_15" class="input flow_9" id="" placeholder="ex) 허리 디스크 치료 이력이 있습니다.">
                </div>
                <div class="empty"></div>
                <p class="title">위와 같은 불편함이 어느 정도나 지속되고 있나요?</p>
                <div class="text">
                  <input type="text" name="data_16" class="input flow_9" id="" placeholder="ex) 6개월">
                </div>
                <div class="empty"></div>
                <p class="title">관련해서 진단서 혹은 의사 소견서 내용이 있으시다면 구체적으로 말씀해주세요.</p>
                <div class="text">
                  <input type="text" name="data_17" class="input flow_9" id="">
                </div>
              </div>

              <div class="message"></div>
            </div>
            <div class="wrap flow_10" style="display: none;">
              <p class="title">홈핏은 어떻게 알게 되셨어요?
                <small class="sub-title">답변해주시면 추첨을 통해 커피교환권을 보내드립니다.</small>
              </p>
              <div class="border checkbox">
                                <span class="">
                                    <input class="input flow_10" name="data_18" type="radio" value="직접검색">직접검색
                                </span>
                <span class="">
                                    <input class="input flow_10" name="data_18" type="radio" value="인스타그램">인스타그램
                                </span>
                <span class="">
                                    <input class="input flow_10" name="data_18" type="radio" value="페이스북">페이스북
                                </span>
                <span class="">
                                    <input class="input flow_10" name="data_18" type="radio" value="블로그">블로그
                                </span>
                <span class="">
                                    <input class="input flow_10" name="data_18" type="radio" value="카카오톡">카카오톡
                                </span>
                <span class="">
                                    <input class="input flow_10" name="data_18" type="radio" value="지인 추천">지인 추천
                                </span>
                <span class="">
                                    <input class="input flow_10" name="data_18" type="radio" value="기타">기타
                                </span>
              </div>
              <div class="flow_10 more first" style="display: none;">
                <div class="empty"></div>
                <p class="title">검색어를 입력해주세요.</p>
                <div class="text">
                  <input type="text" name="data_19" class="input flow_9" id="" placeholder="ex) 방문 PT">
                </div>
              </div>
              <div class="flow_10 more second" style="display: none;">
                <div class="empty"></div>
                <p class="title">어떻게 알게 되셨는지 직접 기재해주세요.</p>
                <div class="text">
                  <input type="text" name="data_20" class="input flow_9" id="" placeholder="">
                </div>


              </div>
              <div class="message"></div>
            </div>
            <div class="wrap flow_105" style="display: none;">
              <!-- <p class="title">기본 정보
                  <small class="sub-title">아래 항목을 입력해주시면 만족도가 높았던 우수 코치님을 우선적으로 배정해드리겠습니다.</small>
              </p> -->

              <p class="title">성함</p>
              <div class="text">
                <input type="text" name="data_21" class="input flow_105" id="" placeholder="">
              </div>
              <p class="title">연락처</p>
              <div class="text">
                <input type="text" name="data_22" class="input flow_105" id="" placeholder="">
              </div>
              <p class="title">요청사항이 있다면 기재해주세요.</p>
              <div class="text">
                <input type="text" name="data_23" class="input flow_105" id="" placeholder="">
              </div>

              <small class="sub-title" style="margin-top: 8px;">
                ※ 작성을 완료해주시면 우수 코치님을 우선적으로 배정해드리겠습니다.<br>
                ※ 지역 및 스케줄에 따라 코치매칭이 어려울 수 있습니다.<br>
                ※ 완료 버튼 클릭 시 이용약관 및 개인정보취급방침에 동의한 것으로 간주합니다.
              </small>
              <div class="message"></div>
            </div>


            <div class="wrap flow_11" style="display: none;">
              <div class="text-center">
                <p style="font-size: 20px; font-weight: bold;">직접 프로그램을 선택하시면<br>상담이 더 빨라집니다!</p>
                <p class="pc-big" style="font-weight: bold; margin: 0; color: #c69c6d; font-size: 13px;">회원님과 가장 적합하다고 생각되는
                  프로그램입니다.</p>
                <p class="pc-big" style="margin: 0; font-size: 13px;">프로그램을 선택하신 후 상담 신청 해주시면<br>코치님이 연락을 드립니다.</p>
                <hr style="margin: 30px 0;">
              </div>
              <p style="margin: 0; font-size: 12px; color: #999; margin-bottom: 3px;">
                <i class="xi-info"></i> 코치의 보유 자격증과 지도 경험을 토대로 철저한 검증 후 프로그램을 개설하고 있습니다.
                <span onclick="$('#id02').fadeIn(300);" style="color: #000; font-weight: bold; text-decoration: underline; cursor: pointer;">코치 검증 절차 확인하기</span>
              </p>
              <p style="margin: 0; font-size: 12px; color: #999; margin-bottom: 32px;">
                <i class="xi-info"></i> 회원님과 동일한 성별의 코치님만 매칭이 가능합니다. (단, 부부나 커플 등의 그룹 레슨은 예외)</p>

              <div class="search-recommend">
                <div class="programs recommend">


                </div>
              </div>


              <div class="search-filters" style="display: none;">
                <ul>
                  <li>
                    <div class="label">
                      <h3>지역</h3>
                    </div>
                    <div class="filter-box select">
                      <select name="search_data_9" style="width: 100px;">
                        <option value="0">시/도</option>
                        <option value="서울">서울</option>              <option value="경기">경기</option>              <option value="인천">인천</option>              <option value="부산">부산</option>              <option value="대구">대구</option>              <option value="대전">대전</option>              <option value="광주">광주</option>              <option value="울산">울산</option>              <option value="세종">세종</option>              <option value="경남">경남</option>              <option value="경북">경북</option>              <option value="충남">충남</option>              <option value="충북">충북</option>              <option value="전남">전남</option>              <option value="전북">전북</option>              <option value="강원">강원</option>              <option value="제주">제주</option>                                        </select>
                      <select name="search_data_10" style="width: 160px;">
                        <option value="0">상세지역</option>
                        <span><option value="서울 강남구" class="depth_1_id_서울" style="display: none;">강남구</option></span>              <span><option value="서울 강동구" class="depth_1_id_서울" style="display: none;">강동구</option></span>              <span><option value="서울 강북구" class="depth_1_id_서울" style="display: none;">강북구</option></span>              <span><option value="서울 강서구" class="depth_1_id_서울" style="display: none;">강서구</option></span>              <span><option value="서울 관악구" class="depth_1_id_서울" style="display: none;">관악구</option></span>              <span><option value="서울 광진구" class="depth_1_id_서울" style="display: none;">광진구</option></span>              <span><option value="서울 구로구" class="depth_1_id_서울" style="display: none;">구로구</option></span>              <span><option value="서울 금천구" class="depth_1_id_서울" style="display: none;">금천구</option></span>              <span><option value="서울 노원구" class="depth_1_id_서울" style="display: none;">노원구</option></span>              <span><option value="서울 도봉구" class="depth_1_id_서울" style="display: none;">도봉구</option></span>              <span><option value="서울 동대문구" class="depth_1_id_서울" style="display: none;">동대문구</option></span>              <span><option value="서울 동작구" class="depth_1_id_서울" style="display: none;">동작구</option></span>              <span><option value="서울 마포구" class="depth_1_id_서울" style="display: none;">마포구</option></span>              <span><option value="서울 서대문구" class="depth_1_id_서울" style="display: none;">서대문구</option></span>              <span><option value="서울 서초구" class="depth_1_id_서울" style="display: none;">서초구</option></span>              <span><option value="서울 성동구" class="depth_1_id_서울" style="display: none;">성동구</option></span>              <span><option value="서울 성북구" class="depth_1_id_서울" style="display: none;">성북구</option></span>              <span><option value="서울 송파구" class="depth_1_id_서울" style="display: none;">송파구</option></span>              <span><option value="서울 양천구" class="depth_1_id_서울" style="display: none;">양천구</option></span>              <span><option value="서울 영등포구" class="depth_1_id_서울" style="display: none;">영등포구</option></span>              <span><option value="서울 용산구" class="depth_1_id_서울" style="display: none;">용산구</option></span>              <span><option value="서울 은평구" class="depth_1_id_서울" style="display: none;">은평구</option></span>              <span><option value="서울 종로구" class="depth_1_id_서울" style="display: none;">종로구</option></span>              <span><option value="서울 중구" class="depth_1_id_서울" style="display: none;">중구</option></span>              <span><option value="서울 중랑구" class="depth_1_id_서울" style="display: none;">중랑구</option></span>              <span><option value="경기 가평군" class="depth_1_id_경기" style="display: none;">가평군</option></span>              <span><option value="경기 고양시" class="depth_1_id_경기" style="display: none;">고양시</option></span>              <span><option value="경기 과천시" class="depth_1_id_경기" style="display: none;">과천시</option></span>              <span><option value="경기 광명시" class="depth_1_id_경기" style="display: none;">광명시</option></span>              <span><option value="경기 광주시" class="depth_1_id_경기" style="display: none;">광주시</option></span>              <span><option value="경기 구리시" class="depth_1_id_경기" style="display: none;">구리시</option></span>              <span><option value="경기 군포시" class="depth_1_id_경기" style="display: none;">군포시</option></span>              <span><option value="경기 김포시" class="depth_1_id_경기" style="display: none;">김포시</option></span>              <span><option value="경기 남양주시" class="depth_1_id_경기" style="display: none;">남양주시</option></span>              <span><option value="경기 동두천시" class="depth_1_id_경기" style="display: none;">동두천시</option></span>              <span><option value="경기 부천시" class="depth_1_id_경기" style="display: none;">부천시</option></span>              <span><option value="경기 성남시" class="depth_1_id_경기" style="display: none;">성남시</option></span>              <span><option value="경기 수원시" class="depth_1_id_경기" style="display: none;">수원시</option></span>              <span><option value="경기 시흥시" class="depth_1_id_경기" style="display: none;">시흥시</option></span>              <span><option value="경기 안산시" class="depth_1_id_경기" style="display: none;">안산시</option></span>              <span><option value="경기 안성시" class="depth_1_id_경기" style="display: none;">안성시</option></span>              <span><option value="경기 안양시" class="depth_1_id_경기" style="display: none;">안양시</option></span>              <span><option value="경기 양주시" class="depth_1_id_경기" style="display: none;">양주시</option></span>              <span><option value="경기 양평군" class="depth_1_id_경기" style="display: none;">양평군</option></span>              <span><option value="경기 여주시" class="depth_1_id_경기" style="display: none;">여주시</option></span>              <span><option value="경기 연천군" class="depth_1_id_경기" style="display: none;">연천군</option></span>              <span><option value="경기 오산시" class="depth_1_id_경기" style="display: none;">오산시</option></span>              <span><option value="경기 용인시" class="depth_1_id_경기" style="display: none;">용인시</option></span>              <span><option value="경기 의왕시" class="depth_1_id_경기" style="display: none;">의왕시</option></span>              <span><option value="경기 의정부시" class="depth_1_id_경기" style="display: none;">의정부시</option></span>              <span><option value="경기 이천시" class="depth_1_id_경기" style="display: none;">이천시</option></span>              <span><option value="경기 파주시" class="depth_1_id_경기" style="display: none;">파주시</option></span>              <span><option value="경기 평택시" class="depth_1_id_경기" style="display: none;">평택시</option></span>              <span><option value="경기 포천시" class="depth_1_id_경기" style="display: none;">포천시</option></span>              <span><option value="경기 하남시" class="depth_1_id_경기" style="display: none;">하남시</option></span>              <span><option value="경기 화성시" class="depth_1_id_경기" style="display: none;">화성시</option></span>              <span><option value="인천 강화군" class="depth_1_id_인천" style="display: none;">강화군</option></span>              <span><option value="인천 계양구" class="depth_1_id_인천" style="display: none;">계양구</option></span>              <span><option value="인천 미추홀구(남구)" class="depth_1_id_인천" style="display: none;">미추홀구(남구)</option></span>              <span><option value="인천 남동구" class="depth_1_id_인천" style="display: none;">남동구</option></span>              <span><option value="인천 동구" class="depth_1_id_인천" style="display: none;">동구</option></span>              <span><option value="인천 부평구" class="depth_1_id_인천" style="display: none;">부평구</option></span>              <span><option value="인천 서구" class="depth_1_id_인천" style="display: none;">서구</option></span>              <span><option value="인천 연수구" class="depth_1_id_인천" style="display: none;">연수구</option></span>              <span><option value="인천 옹진군" class="depth_1_id_인천" style="display: none;">옹진군</option></span>              <span><option value="인천 중구" class="depth_1_id_인천" style="display: none;">중구</option></span>              <span><option value="부산 강서구" class="depth_1_id_부산" style="display: none;">강서구</option></span>              <span><option value="부산 금정구" class="depth_1_id_부산" style="display: none;">금정구</option></span>              <span><option value="부산 기장군" class="depth_1_id_부산" style="display: none;">기장군</option></span>              <span><option value="부산 남구" class="depth_1_id_부산" style="display: none;">남구</option></span>              <span><option value="부산 동구" class="depth_1_id_부산" style="display: none;">동구</option></span>              <span><option value="부산 동래구" class="depth_1_id_부산" style="display: none;">동래구</option></span>              <span><option value="부산 부산진구" class="depth_1_id_부산" style="display: none;">부산진구</option></span>              <span><option value="부산 북구" class="depth_1_id_부산" style="display: none;">북구</option></span>              <span><option value="부산 사상구" class="depth_1_id_부산" style="display: none;">사상구</option></span>              <span><option value="부산 사하구" class="depth_1_id_부산" style="display: none;">사하구</option></span>              <span><option value="부산 서구" class="depth_1_id_부산" style="display: none;">서구</option></span>              <span><option value="부산 수영구" class="depth_1_id_부산" style="display: none;">수영구</option></span>              <span><option value="부산 연제구" class="depth_1_id_부산" style="display: none;">연제구</option></span>              <span><option value="부산 영도구" class="depth_1_id_부산" style="display: none;">영도구</option></span>              <span><option value="부산 중구" class="depth_1_id_부산" style="display: none;">중구</option></span>              <span><option value="부산 해운대구" class="depth_1_id_부산" style="display: none;">해운대구</option></span>              <span><option value="대구 중구" class="depth_1_id_대구" style="display: none;">중구</option></span>              <span><option value="대구 동구" class="depth_1_id_대구" style="display: none;">동구</option></span>              <span><option value="대구 서구" class="depth_1_id_대구" style="display: none;">서구</option></span>              <span><option value="대구 남구" class="depth_1_id_대구" style="display: none;">남구</option></span>              <span><option value="대구 북구" class="depth_1_id_대구" style="display: none;">북구</option></span>              <span><option value="대구 수성구" class="depth_1_id_대구" style="display: none;">수성구</option></span>              <span><option value="대구 달서구" class="depth_1_id_대구" style="display: none;">달서구</option></span>              <span><option value="대구 달성군" class="depth_1_id_대구" style="display: none;">달성군</option></span>              <span><option value="대전 대덕구" class="depth_1_id_대전" style="display: none;">대덕구</option></span>              <span><option value="대전 동구" class="depth_1_id_대전" style="display: none;">동구</option></span>              <span><option value="대전 서구" class="depth_1_id_대전" style="display: none;">서구</option></span>              <span><option value="대전 유성구" class="depth_1_id_대전" style="display: none;">유성구</option></span>              <span><option value="대전 중구" class="depth_1_id_대전" style="display: none;">중구</option></span>              <span><option value="울산 남구" class="depth_1_id_울산" style="display: none;">남구</option></span>              <span><option value="울산 동구" class="depth_1_id_울산" style="display: none;">동구</option></span>              <span><option value="울산 북구" class="depth_1_id_울산" style="display: none;">북구</option></span>              <span><option value="울산 울주군" class="depth_1_id_울산" style="display: none;">울주군</option></span>              <span><option value="울산 중구" class="depth_1_id_울산" style="display: none;">중구</option></span>              <span><option value="세종 세종시" class="depth_1_id_세종" style="display: none;">세종시</option></span>              <span><option value="충남 계룡시" class="depth_1_id_충남" style="display: none;">계룡시</option></span>              <span><option value="충남 공주시" class="depth_1_id_충남" style="display: none;">공주시</option></span>              <span><option value="충남 금산군" class="depth_1_id_충남" style="display: none;">금산군</option></span>              <span><option value="충남 논산시" class="depth_1_id_충남" style="display: none;">논산시</option></span>              <span><option value="충남 당진시" class="depth_1_id_충남" style="display: none;">당진시</option></span>              <span><option value="충남 보령시" class="depth_1_id_충남" style="display: none;">보령시</option></span>              <span><option value="충남 부여군" class="depth_1_id_충남" style="display: none;">부여군</option></span>              <span><option value="충남 서산시" class="depth_1_id_충남" style="display: none;">서산시</option></span>              <span><option value="충남 서천군" class="depth_1_id_충남" style="display: none;">서천군</option></span>              <span><option value="충남 아산시" class="depth_1_id_충남" style="display: none;">아산시</option></span>              <span><option value="충남 예산군" class="depth_1_id_충남" style="display: none;">예산군</option></span>              <span><option value="충남 천안시" class="depth_1_id_충남" style="display: none;">천안시</option></span>              <span><option value="충남 청양군" class="depth_1_id_충남" style="display: none;">청양군</option></span>              <span><option value="충남 태안군" class="depth_1_id_충남" style="display: none;">태안군</option></span>              <span><option value="충남 홍성군" class="depth_1_id_충남" style="display: none;">홍성군</option></span>              <span><option value="충북 괴산군" class="depth_1_id_충북" style="display: none;">괴산군</option></span>              <span><option value="충북 단양군" class="depth_1_id_충북" style="display: none;">단양군</option></span>              <span><option value="충북 보은군" class="depth_1_id_충북" style="display: none;">보은군</option></span>              <span><option value="충북 영동군" class="depth_1_id_충북" style="display: none;">영동군</option></span>              <span><option value="충북 옥천군" class="depth_1_id_충북" style="display: none;">옥천군</option></span>              <span><option value="충북 음성군" class="depth_1_id_충북" style="display: none;">음성군</option></span>              <span><option value="충북 제천시" class="depth_1_id_충북" style="display: none;">제천시</option></span>              <span><option value="충북 증평군" class="depth_1_id_충북" style="display: none;">증평군</option></span>              <span><option value="충북 진천군" class="depth_1_id_충북" style="display: none;">진천군</option></span>              <span><option value="충북 청주시" class="depth_1_id_충북" style="display: none;">청주시</option></span>              <span><option value="충북 충주시" class="depth_1_id_충북" style="display: none;">충주시</option></span>              <span><option value="경북 경산시" class="depth_1_id_경북" style="display: none;">경산시</option></span>              <span><option value="경북 경주시" class="depth_1_id_경북" style="display: none;">경주시</option></span>              <span><option value="경북 고령군" class="depth_1_id_경북" style="display: none;">고령군</option></span>              <span><option value="경북 구미시" class="depth_1_id_경북" style="display: none;">구미시</option></span>              <span><option value="경북 군위군" class="depth_1_id_경북" style="display: none;">군위군</option></span>              <span><option value="경북 김천시" class="depth_1_id_경북" style="display: none;">김천시</option></span>              <span><option value="경북 문경시" class="depth_1_id_경북" style="display: none;">문경시</option></span>              <span><option value="경북 봉화군" class="depth_1_id_경북" style="display: none;">봉화군</option></span>              <span><option value="경북 상주시" class="depth_1_id_경북" style="display: none;">상주시</option></span>              <span><option value="경북 성주군" class="depth_1_id_경북" style="display: none;">성주군</option></span>              <span><option value="경북 안동시" class="depth_1_id_경북" style="display: none;">안동시</option></span>              <span><option value="경북 영덕군" class="depth_1_id_경북" style="display: none;">영덕군</option></span>              <span><option value="경북 영양군" class="depth_1_id_경북" style="display: none;">영양군</option></span>              <span><option value="경북 영주시" class="depth_1_id_경북" style="display: none;">영주시</option></span>              <span><option value="경북 영천시" class="depth_1_id_경북" style="display: none;">영천시</option></span>              <span><option value="경북 예천군" class="depth_1_id_경북" style="display: none;">예천군</option></span>              <span><option value="경북 울릉군" class="depth_1_id_경북" style="display: none;">울릉군</option></span>              <span><option value="경북 울진군" class="depth_1_id_경북" style="display: none;">울진군</option></span>              <span><option value="경북 의성군" class="depth_1_id_경북" style="display: none;">의성군</option></span>              <span><option value="경북 청도군" class="depth_1_id_경북" style="display: none;">청도군</option></span>              <span><option value="경북 청송군" class="depth_1_id_경북" style="display: none;">청송군</option></span>              <span><option value="경북 칠곡군" class="depth_1_id_경북" style="display: none;">칠곡군</option></span>              <span><option value="경북 포항시" class="depth_1_id_경북" style="display: none;">포항시</option></span>              <span><option value="광주 광산구" class="depth_1_id_광주" style="display: none;">광산구</option></span>              <span><option value="광주 남구" class="depth_1_id_광주" style="display: none;">남구</option></span>              <span><option value="광주 동구" class="depth_1_id_광주" style="display: none;">동구</option></span>              <span><option value="광주 북구" class="depth_1_id_광주" style="display: none;">북구</option></span>              <span><option value="광주 서구" class="depth_1_id_광주" style="display: none;">서구</option></span>              <span><option value="강원 강릉시" class="depth_1_id_강원" style="display: none;">강릉시</option></span>              <span><option value="강원 고성군" class="depth_1_id_강원" style="display: none;">고성군</option></span>              <span><option value="강원 동해시" class="depth_1_id_강원" style="display: none;">동해시</option></span>              <span><option value="강원 삼척시" class="depth_1_id_강원" style="display: none;">삼척시</option></span>              <span><option value="강원 속초시" class="depth_1_id_강원" style="display: none;">속초시</option></span>              <span><option value="강원 양구군" class="depth_1_id_강원" style="display: none;">양구군</option></span>              <span><option value="강원 양양군" class="depth_1_id_강원" style="display: none;">양양군</option></span>              <span><option value="강원 영월군" class="depth_1_id_강원" style="display: none;">영월군</option></span>              <span><option value="강원 원주시" class="depth_1_id_강원" style="display: none;">원주시</option></span>              <span><option value="강원 인제군" class="depth_1_id_강원" style="display: none;">인제군</option></span>              <span><option value="강원 정선군" class="depth_1_id_강원" style="display: none;">정선군</option></span>              <span><option value="강원 철원군" class="depth_1_id_강원" style="display: none;">철원군</option></span>              <span><option value="강원 춘천시" class="depth_1_id_강원" style="display: none;">춘천시</option></span>              <span><option value="강원 태백시" class="depth_1_id_강원" style="display: none;">태백시</option></span>              <span><option value="강원 평창군" class="depth_1_id_강원" style="display: none;">평창군</option></span>              <span><option value="강원 홍천군" class="depth_1_id_강원" style="display: none;">홍천군</option></span>              <span><option value="강원 화천군" class="depth_1_id_강원" style="display: none;">화천군</option></span>              <span><option value="강원 횡성군" class="depth_1_id_강원" style="display: none;">횡성군</option></span>              <span><option value="경남 거제시" class="depth_1_id_경남" style="display: none;">거제시</option></span>              <span><option value="경남 거창군" class="depth_1_id_경남" style="display: none;">거창군</option></span>              <span><option value="경남 고성군" class="depth_1_id_경남" style="display: none;">고성군</option></span>              <span><option value="경남 김해시" class="depth_1_id_경남" style="display: none;">김해시</option></span>              <span><option value="경남 남해군" class="depth_1_id_경남" style="display: none;">남해군</option></span>              <span><option value="경남 밀양시" class="depth_1_id_경남" style="display: none;">밀양시</option></span>              <span><option value="경남 사천시" class="depth_1_id_경남" style="display: none;">사천시</option></span>              <span><option value="경남 산청군" class="depth_1_id_경남" style="display: none;">산청군</option></span>              <span><option value="경남 양산시" class="depth_1_id_경남" style="display: none;">양산시</option></span>              <span><option value="경남 의령군" class="depth_1_id_경남" style="display: none;">의령군</option></span>              <span><option value="경남 진주시" class="depth_1_id_경남" style="display: none;">진주시</option></span>              <span><option value="경남 창녕군" class="depth_1_id_경남" style="display: none;">창녕군</option></span>              <span><option value="경남 창원시" class="depth_1_id_경남" style="display: none;">창원시</option></span>              <span><option value="경남 통영시" class="depth_1_id_경남" style="display: none;">통영시</option></span>              <span><option value="경남 하동군" class="depth_1_id_경남" style="display: none;">하동군</option></span>              <span><option value="경남 함안군" class="depth_1_id_경남" style="display: none;">함안군</option></span>              <span><option value="경남 함양군" class="depth_1_id_경남" style="display: none;">함양군</option></span>              <span><option value="경남 합천군" class="depth_1_id_경남" style="display: none;">합천군</option></span>              <span><option value="전남 강진군" class="depth_1_id_전남" style="display: none;">강진군</option></span>              <span><option value="전남 고흥군" class="depth_1_id_전남" style="display: none;">고흥군</option></span>              <span><option value="전남 곡성군" class="depth_1_id_전남" style="display: none;">곡성군</option></span>              <span><option value="전남 광양시" class="depth_1_id_전남" style="display: none;">광양시</option></span>              <span><option value="전남 구례군" class="depth_1_id_전남" style="display: none;">구례군</option></span>              <span><option value="전남 나주시" class="depth_1_id_전남" style="display: none;">나주시</option></span>              <span><option value="전남 담양군" class="depth_1_id_전남" style="display: none;">담양군</option></span>              <span><option value="전남 목포시" class="depth_1_id_전남" style="display: none;">목포시</option></span>              <span><option value="전남 무안군" class="depth_1_id_전남" style="display: none;">무안군</option></span>              <span><option value="전남 보성군" class="depth_1_id_전남" style="display: none;">보성군</option></span>              <span><option value="전남 순천시" class="depth_1_id_전남" style="display: none;">순천시</option></span>              <span><option value="전남 신안군" class="depth_1_id_전남" style="display: none;">신안군</option></span>              <span><option value="전남 여수시" class="depth_1_id_전남" style="display: none;">여수시</option></span>              <span><option value="전남 영광군" class="depth_1_id_전남" style="display: none;">영광군</option></span>              <span><option value="전남 영암군" class="depth_1_id_전남" style="display: none;">영암군</option></span>              <span><option value="전남 완도군" class="depth_1_id_전남" style="display: none;">완도군</option></span>              <span><option value="전남 장성군" class="depth_1_id_전남" style="display: none;">장성군</option></span>              <span><option value="전남 장흥군" class="depth_1_id_전남" style="display: none;">장흥군</option></span>              <span><option value="전남 진도군" class="depth_1_id_전남" style="display: none;">진도군</option></span>              <span><option value="전남 함평군" class="depth_1_id_전남" style="display: none;">함평군</option></span>              <span><option value="전남 해남군" class="depth_1_id_전남" style="display: none;">해남군</option></span>              <span><option value="전남 화순군" class="depth_1_id_전남" style="display: none;">화순군</option></span>              <span><option value="전북 고창군" class="depth_1_id_전북" style="display: none;">고창군</option></span>              <span><option value="전북 군산시" class="depth_1_id_전북" style="display: none;">군산시</option></span>              <span><option value="전북 김제시" class="depth_1_id_전북" style="display: none;">김제시</option></span>              <span><option value="전북 남원시" class="depth_1_id_전북" style="display: none;">남원시</option></span>              <span><option value="전북 무주군" class="depth_1_id_전북" style="display: none;">무주군</option></span>              <span><option value="전북 부안군" class="depth_1_id_전북" style="display: none;">부안군</option></span>              <span><option value="전북 순창군" class="depth_1_id_전북" style="display: none;">순창군</option></span>              <span><option value="전북 완주군" class="depth_1_id_전북" style="display: none;">완주군</option></span>              <span><option value="전북 익산시" class="depth_1_id_전북" style="display: none;">익산시</option></span>              <span><option value="전북 임실군" class="depth_1_id_전북" style="display: none;">임실군</option></span>              <span><option value="전북 장수군" class="depth_1_id_전북" style="display: none;">장수군</option></span>              <span><option value="전북 전주시" class="depth_1_id_전북" style="display: none;">전주시</option></span>              <span><option value="전북 정읍시" class="depth_1_id_전북" style="display: none;">정읍시</option></span>              <span><option value="전북 진안군" class="depth_1_id_전북" style="display: none;">진안군</option></span>              <span><option value="제주 서귀포시" class="depth_1_id_제주" style="display: none;">서귀포시</option></span>              <span><option value="제주 제주시" class="depth_1_id_제주" style="display: none;">제주시</option></span>                                        </select>
                    </div>
                  </li>
                  <li>
                    <div class="label">
                      <h3>
                        목적
                        <span id="purposes-mobile" onclick="$('#id04').fadeIn(300)" style="background: #eee;
    float: right;
    font-size: 11px;
    font-weight: normal;
    color: #999;
    padding: 3px 12px;
    border-radius: 13px;">
	                                        	목적별 설명 보기 <i class="xi-help"></i>
	                                        </span>
                      </h3>

                    </div>
                    <div class="filter-box">
                                    	<span id="purposes-pc" style="background: rgb(238, 238, 238); cursor: pointer; float: right; font-size: 12px; font-weight: normal; color: rgb(153, 153, 153); padding: 3px 12px; border-radius: 13px; margin-right: 10px;">
	                                        	목적별 설명 보기 <i class="xi-help"></i>
	                                        </span>
                      <div id="id05" style="background: rgb(255, 255, 255); z-index: 2; border: 1px solid rgb(221, 221, 221); width: 400px; position: absolute; display: none; top: 30px; left: -404px;">

                        <span onclick="$('#id05').fadeOut(300);" class="w3-button w3-display-topright">×</span>


                        <img src="/static/img/suggest/purposes.jpg" alt="" style="width: 100%"></div>
                      <div class="yp-checkbox" style="width: 35%;">
                        <input type="checkbox" name="search_data_1" class="uk-checkbox" value="1,2">
                        <span class="text">몸매관리 (다이어트, 근력향상)</span>
                      </div>
                      <div class="yp-checkbox" style="width: 35%;">
                        <input type="checkbox" name="search_data_1" class="uk-checkbox" value="4">
                        <span class="text">바른체형/신체 정렬</span>
                      </div>
                      <div class="yp-checkbox" style="width: 35%;">
                        <input type="checkbox" name="search_data_1" class="uk-checkbox" value="3">
                        <span class="text">스트레스 해소</span>
                      </div>
                      <div class="yp-checkbox" style="width: 35%;">
                        <input type="checkbox" name="search_data_1" class="uk-checkbox" value="5">
                        <span class="text">산전 전문 관리</span>
                      </div>
                      <div class="yp-checkbox" style="width: 35%;">
                        <input type="checkbox" name="search_data_1" class="uk-checkbox" value="6">
                        <span class="text">산후 전문 관리</span>
                      </div>
                      <div class="yp-checkbox" style="width: 35%;">
                        <input type="checkbox" name="search_data_1" class="uk-checkbox" value="7">
                        <span class="text">중증의 통증케어/기능회복</span>
                      </div>
                    </div>
                  </li>
                  <li>
                    <div class="label">
                      <h3>종목</h3>
                    </div>
                    <div class="filter-box">
                      <div class="yp-checkbox" style="width: auto; margin-right: 15px;">
                        <input type="checkbox" name="search_data_5" class="uk-checkbox" value="1">
                        <span class="text">요가</span>
                      </div>
                      <div class="yp-checkbox" style="width: auto; margin-right: 15px;">
                        <input type="checkbox" name="search_data_5" class="uk-checkbox" value="2">
                        <span class="text">필라테스</span>
                      </div>
                      <div class="yp-checkbox" style="width: auto; margin-right: 15px;">
                        <input type="checkbox" name="search_data_5" class="uk-checkbox" value="3">
                        <span class="text">웨이트</span>
                      </div>
                      <div class="yp-checkbox" style="width: auto; margin-right: 15px;">
                        <input type="checkbox" name="search_data_5" class="uk-checkbox" value="4">
                        <span class="text">통증케어</span>
                      </div>
                    </div>
                  </li>
                  <li>
                    <div class="label">
                      <h3>성별</h3>
                    </div>
                    <div class="filter-box">
                      <div class="yp-checkbox" style="width: auto; margin-right: 15px;">
                        <input type="checkbox" name="search_data_12" class="uk-checkbox" value="M">
                        <span class="text">남성</span>
                      </div>
                      <div class="yp-checkbox" style="width: auto; margin-right: 15px;">
                        <input type="checkbox" name="search_data_12" class="uk-checkbox" value="F">
                        <span class="text">여성</span>
                      </div>
                    </div>
                  </li>
                  <li>
                    <div class="label" style="vertical-align: top;">
                      <h3>가능한 시간대</h3>
                    </div>
                    <div class="filter-box schedule">
                      <div id="button">
                        <div style="margin-bottom: 10px">
                          <button type="button" data-toggle="add-timetable" data-value="mon">월
                          </button>
                          <button type="button" data-toggle="add-timetable" data-value="tue">화
                          </button>
                          <button type="button" data-toggle="add-timetable" data-value="wed">수
                          </button>
                          <button type="button" data-toggle="add-timetable" data-value="thu">목
                          </button>
                          <button type="button" data-toggle="add-timetable" data-value="fri">금
                          </button>
                          <button type="button" data-toggle="add-timetable" data-value="sat">토
                          </button>
                          <button type="button" data-toggle="add-timetable" data-value="sun">일
                          </button>
                        </div>
                        <div style="margin-bottom: 10px">
                          <button type="button" data-toggle="add-timetable" data-value="wek">주중
                          </button>
                          <button type="button" data-toggle="add-timetable" data-value="end">주말
                          </button>
                        </div>
                        <div>
                          <button type="button" data-toggle="add-timetable" data-value="all">모든 요일
                          </button>
                        </div>
                      </div>
                      <div style="display: inline-block; width: 100%; margin-top: 20px;" id="timetable">
                        <div class="timetable-wrap" data-value="mon" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              월
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="mon" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="mon" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="mon" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="mon" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="mon" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="mon" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>
                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="tue" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              화
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="tue" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="tue" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="tue" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="tue" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="tue" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="tue" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="wed" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              수
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wed" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wed" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wed" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wed" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wed" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wed" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="thu" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              목
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="thu" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="thu" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="thu" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="thu" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="thu" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="thu" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="fri" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              금
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="fri" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="fri" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="fri" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="fri" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="fri" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="fri" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="sat" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              토
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sat" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sat" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sat" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sat" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sat" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sat" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="sun" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              일
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sun" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sun" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sun" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sun" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sun" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="sun" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="wek" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              주중
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wek" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wek" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wek" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wek" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wek" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="wek" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="end" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              주말
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="end" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="end" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="end" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="end" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="end" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="end" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                        <div class="timetable-wrap" data-value="all" style="display: none;">
                          <div class="timetable">

                            <p class="title">
                              모든 요일
                              <i class="xi-close" style="float: right;"></i>
                            </p>
                            <p class="sub-title"><i class="far fa-clock"></i> 시간을 선택하세요. (복수 선택
                              가능)</p>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="all" value="1">
                              <span class="text">이른 오전 (9시 이전)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="all" value="2">
                              <span class="text">늦은 오전 (9시~12시)</span>
                            </div>

                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="all" value="3">
                              <span class="text">이른 오후 (12시~15시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="all" value="4">
                              <span class="text">늦은 오후 (15시~18시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="all" value="5">
                              <span class="text">이른 저녁 (18시~21시)</span>
                            </div>
                            <div class="yp-checkbox">
                              <input type="checkbox" name="search_data_8" class="uk-checkbox" data-value="all" value="6">
                              <span class="text">늦은 저녁 (21시 이후)</span>
                            </div>

                          </div>
                        </div>
                      </div>
                    </div>
                  </li>
                </ul>

                <!--  <p style="margin-bottom: 5px; font-size: 18px; font-weight: bold;">추천 프로그램 <span
                             class="recommend-count"
                             style="font-size: 16px; font-weight: normal; color: #999;">0건</span></p>
                 <p style="color: #999; font-size: 12px; margin-top: 0;"><i class="xi-volume-up"></i> 홈핏팀이
                     엄선한 프로그램입니다.</p>
                 <div class="programs recommend">

                 </div> -->

                <p class=" hide-no-programs" style="font-size: 18px; font-weight: bold;">신규 프로그램 <span class="new-count" style="font-size: 16px; font-weight: normal; color: #999;">0건</span>
                </p>

                <div class="programs new">

                </div>
                <p class=" hide-no-programs" style="font-size: 18px; font-weight: bold; margin-bottom: -60px !important;">검색 결과 <span class="normal-count" style="font-size: 16px; font-weight: normal; color: #999;">0건</span>
                </p>
                <div class="sort hide-no-programs">
                  <ul style="margin-bottom: 20px;">
                    <li><span uk-icon="icon:list; ratio:0.7" class="uk-icon"><svg width="14" height="14" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"> <rect x="6" y="4" width="12" height="1"></rect> <rect x="6" y="9" width="12" height="1"></rect> <rect x="6" y="14" width="12" height="1"></rect> <rect x="2" y="4" width="2" height="1"></rect> <rect x="2" y="9" width="2" height="1"></rect> <rect x="2" y="14" width="2" height="1"></rect></svg></span></li>
                    <li>
                      <button class="hf_search_filter_button" type="button" aria-expanded="false">
                                            <span class="hf_search_filter_button_text">
                                                수업횟수 순                          </span>
                        <span class="hf_search_filter_button_icon uk-icon" uk-icon="icon: chevron-down; ratio: 1"><svg width="20" height="20" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"> <polyline fill="none" stroke="#000" stroke-width="1.03" points="16 7 10 13 4 7"></polyline></svg></span>
                      </button>
                      <div class="hf_search_filter_list uk-dropdown uk-dropdown-bottom-right" uk-dropdown="mode: click; pos: bottom-right;" style="left: 718px; top: 376.094px;">
                        <ul class="uk-nav uk-dropdown-nav hf_search_filter_list_ul">
                          <li class="hf_search_filter_list_li sort_popular uk-active" data-value="1">수업횟수 순</li>
                          <li class="hf_search_filter_list_li sort_review" data-value="2">후기 순</li>
                          <li class="hf_search_filter_list_li sort_schedule" data-value="3">수업시간 업데이트 순</li>
                        </ul>
                      </div>
                    </li>
                  </ul>
                </div>
                <div class="programs all">

                </div>

                <div class="programs normal">

                </div>

                <div class="no-programs" style="text-align: center; margin-top:40px;">
                  <i class="fas fa-exclamation-circle" style="display: block;
    margin: 0px auto 12px auto;
    font-size: 64px;
    color: #be9b67;"></i>

                  조건에 맞는 프로그램이 없습니다.<br>
                  위 검색 옵션을 변경해 보세요.
                </div>
              </div>

            </div>

            <div class="wrap text-right" id="flow_10">
              <button type="button" class="prev" style="display: none;">이전</button>
              <button type="button" class="next">다음</button>
            </div>
            <div class="wrap text-center" id="flow_11" style="display: none;">
              <button type="button" class="more">검색 결과 더보기</button>
            </div>
          </form>
        </div>

      </div>

      <div class="pii_sub_box">
        <div class="pii_sub_text"><i class="xi-error"></i> 홈핏 <a href="/price" target="_blank">가격정책</a> 확인하기</div>
        <div class="pii_sub_img"><img src="/static/img/suggest/pii_layer_info.png"></div>
        <div class="pii_sub_img_mobile"><img src="/static/img/suggest/pii_layer_info_mobile.png"></div>
      </div>

    </div>
    <div class="request" style="display: none;">
      <button style="border: 0 !important; font-size: 16px; font-weight: normal;" type="buton" class="request">홈핏팀이 직접 찾아주세요</button>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'
import homefit from "../layouts/homefit";

export default {
  layout: 'homefit'
}
</script>
