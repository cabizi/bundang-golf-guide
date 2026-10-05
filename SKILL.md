<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>{{브로슈어 제목}}</title>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Black+Han+Sans&family=Noto+Sans+KR:wght@400;500;700&display=swap">
<style>
:root{
  --ink:#10261c; --muted:#5b6b62; --paper:#f7faf6; --card:#ffffff; --line:#dbe6dc;
  --fairway:#1f7a4d; --deep:#0c3b29; --sun:#ff7a3d; --sky:#cfeaf5; --sand:#f3e3b8;
  --hero-a:#0c3b29; --hero-b:#1f7a4d; --hero-c:#7fc58a;
  box-sizing:border-box;
  padding-top:env(safe-area-inset-top,0px); padding-bottom:env(safe-area-inset-bottom,0px);
}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --ink:#e8f2ea; --muted:#9db3a5; --paper:#0b1a13; --card:#12261b; --line:#244233;
    --sky:#16384a; --sand:#3a331b;
  }
}
:root[data-theme="dark"]{
  --ink:#e8f2ea; --muted:#9db3a5; --paper:#0b1a13; --card:#12261b; --line:#244233;
  --sky:#16384a; --sand:#3a331b;
}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
*,*::before,*::after{box-sizing:inherit}
body{margin:0;background:var(--paper);color:var(--ink);
  font-family:"Noto Sans KR",system-ui,-apple-system,"Apple SD Gothic Neo","Malgun Gothic",sans-serif;line-height:1.6}
.wrap{max-width:880px;margin:0 auto;padding:0 18px 56px}
h1,h2,h3{font-family:"Black Han Sans","Noto Sans KR","Apple SD Gothic Neo",sans-serif;font-weight:400;margin:0;line-height:1.25}

/* 표지 */
.cover{background:linear-gradient(170deg,var(--hero-a),var(--hero-b) 60%,var(--hero-c));color:#fff;
  padding:44px 18px 0;overflow:hidden}
.cover .wrap{padding-bottom:0}
.cover h1{font-size:clamp(30px,7vw,52px);letter-spacing:-.5px}
.cover p{margin:10px 0 0;font-size:16px;opacity:.92;max-width:34em}
.cover svg{display:block;width:100%;height:auto;margin-top:18px}
.stamp{display:inline-block;background:var(--sun);color:#fff;font-weight:700;border-radius:999px;padding:6px 14px;font-size:14px;margin-bottom:14px}

/* 코스 상품 카드 */
.course{background:var(--card);border:1px solid var(--line);border-radius:20px;margin:28px 0;overflow:hidden}
.photo{position:relative;aspect-ratio:16/8;background:linear-gradient(180deg,var(--sky) 0 46%,#8fd0a0 46% 100%);}
.photo svg,.photo img{position:absolute;inset:0;width:100%;height:100%;object-fit:cover}
.photo .tagline{position:absolute;left:14px;bottom:12px;color:#fff;font-family:"Black Han Sans","Noto Sans KR",sans-serif;
  font-size:clamp(18px,4.4vw,28px);text-shadow:0 2px 10px rgba(0,0,0,.55)}
.badge-row{display:flex;flex-wrap:wrap;gap:6px;padding:14px 18px 0}
.badge{background:var(--sand);color:var(--ink);border-radius:8px;padding:3px 10px;font-size:13px;font-weight:500}
.badge.hot{background:var(--sun);color:#fff}
.head{display:flex;gap:16px;justify-content:space-between;align-items:flex-end;flex-wrap:wrap;padding:10px 18px 0}
.head h2{font-size:clamp(22px,5vw,32px)}
.head .sub{color:var(--muted);font-size:14px}
.price{text-align:right}
.price small{display:block;color:var(--muted);font-size:12px}
.price b{font-family:"Black Han Sans","Noto Sans KR",sans-serif;font-weight:400;font-size:clamp(26px,6vw,36px);color:var(--sun)}
.price b span{font-size:.55em;color:var(--ink)}

.body{padding:6px 18px 20px}
.sec-title{font-family:"Black Han Sans","Noto Sans KR",sans-serif;font-size:18px;margin:22px 0 10px}

/* 이용 정보 */
.info{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:10px}
.info div{background:var(--paper);border:1px solid var(--line);border-radius:12px;padding:10px 12px}
.info dt{font-size:12px;color:var(--muted)}
.info dd{margin:2px 0 0;font-weight:700;font-size:15px}

/* 포함·불포함 */
.inc{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.inc ul{margin:0;padding:12px 14px 12px 30px;border-radius:12px;font-size:14px}
.inc .yes{background:color-mix(in srgb,var(--fairway) 14%,var(--card))}
.inc .no{background:color-mix(in srgb,var(--sun) 12%,var(--card))}
@media (max-width:520px){.inc{grid-template-columns:1fr}}

/* 하루 일정 (순서가 실제로 있는 내용) */
.flow{list-style:none;margin:0;padding:0;border-left:3px solid var(--fairway);margin-left:8px}
.flow li{position:relative;padding:0 0 12px 18px;font-size:14px}
.flow li::before{content:"";position:absolute;left:-9px;top:6px;width:13px;height:13px;border-radius:50%;background:var(--sun);border:2px solid var(--card)}
.flow b{display:inline-block;min-width:3.4em}

/* 장단점 */
.pc{display:grid;grid-template-columns:1fr 1fr;gap:10px}
.pc div{border:1px solid var(--line);border-radius:12px;padding:12px 14px;font-size:14px}
.pc h3{font-size:15px;margin-bottom:6px}
.pc ul{margin:0;padding-left:18px}
@media (max-width:520px){.pc{grid-template-columns:1fr}}

/* 맛집 */
.food{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:12px}
.dish{border:1px solid var(--line);border-radius:14px;overflow:hidden;background:var(--paper)}
.dish .thumb{height:84px;background:linear-gradient(135deg,var(--sand),var(--sun));display:flex;align-items:center;justify-content:center;font-size:38px}
.dish .t{padding:10px 12px;font-size:14px}
.dish .t b{display:block;font-size:15px}
.dish .t span{color:var(--muted)}

.go{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:10px;margin-top:6px}
.go div{background:var(--paper);border:1px solid var(--line);border-radius:12px;padding:10px 12px;font-size:14px}
.go dt{font-size:12px;color:var(--muted)}
.go dd{margin:2px 0 0;font-weight:700;word-break:keep-all;overflow-wrap:anywhere}
.go a{color:var(--fairway);text-decoration:underline}
.total{margin-top:12px;border:2px dashed var(--sun);border-radius:12px;padding:10px 14px;font-size:14px}
.total b{color:var(--sun)}
.share{margin-top:12px;background:var(--sky);border-radius:12px;padding:10px 14px;font-size:14px;white-space:pre-line;user-select:all}
.share small{display:block;color:var(--muted);font-size:12px;margin-bottom:4px}
.cta{margin-top:18px;background:var(--deep);color:#fff;border-radius:14px;padding:14px 16px;font-size:14px}
.cta b{color:var(--sand)}
.note{color:var(--muted);font-size:12px;margin-top:28px}
</style>
</head>
<body>

<!-- ① 표지: 지역·콘셉트를 한 줄로. 숫자는 확인된 값만. -->
<header class="cover">
  <div class="wrap">
    <span class="stamp">{{기준일}} 기준 · 분당 출발</span>
    <h1>{{메인 카피 예: 분당에서 90분, 이번 주말 필드로}}</h1>
    <p>{{서브 카피: 조사한 골프장 수 · 이동 시간 범위 · 가격대 범위}}</p>
  </div>
  <!-- 코스 일러스트(사진 대체). 사진을 못 넣는 환경에서도 표지가 비지 않게 한다. -->
  <svg viewBox="0 0 880 170" preserveAspectRatio="none" aria-hidden="true">
    <circle cx="730" cy="52" r="26" fill="#ffd9a0"/>
    <path d="M0 120 C140 70 260 110 400 90 S660 60 880 100 V170 H0Z" fill="#7fc58a"/>
    <path d="M0 140 C180 105 300 140 460 120 S720 100 880 132 V170 H0Z" fill="#1f7a4d"/>
    <ellipse cx="300" cy="138" rx="46" ry="9" fill="#9be0a8"/>
    <line x1="300" y1="138" x2="300" y2="104" stroke="#fff" stroke-width="2"/>
    <path d="M300 104 l22 7 -22 7z" fill="#ff7a3d"/>
  </svg>
</header>

<main class="wrap">

<!-- ② 골프장 1곳 = course 블록 1개. 골프장 수만큼 복제한다. -->
<article class="course">
  <div class="photo">
    <!-- 사진이 있을 때만 교체: <img src="data:image/jpeg;base64,..." alt="{{골프장명}} 전경">
         외부 이미지 URL은 게시 페이지에서 차단되므로 쓰지 않는다. 없으면 아래 일러스트를 유지. -->
    <svg viewBox="0 0 800 400" preserveAspectRatio="xMidYMid slice" aria-hidden="true">
      <circle cx="640" cy="90" r="38" fill="#ffe3b0"/>
      <path d="M0 220 C140 160 280 210 420 180 S680 150 800 200 V400 H0Z" fill="#6fbf85"/>
      <path d="M0 270 C200 230 320 280 500 250 S720 230 800 270 V400 H0Z" fill="#1f7a4d"/>
      <path d="M120 400 C230 330 330 310 470 300" stroke="#e9dcae" stroke-width="22" fill="none" opacity=".8"/>
      <ellipse cx="520" cy="296" rx="70" ry="13" fill="#a5e5b2"/>
      <line x1="520" y1="296" x2="520" y2="244" stroke="#fff" stroke-width="3"/>
      <path d="M520 244 l30 10 -30 10z" fill="#ff7a3d"/>
    </svg>
    <div class="tagline">{{코스 특징 한 줄 카피. 후기 근거가 있는 표현만}}</div>
  </div>

  <div class="badge-row">
    <span class="badge hot">{{예: 분당에서 55분}}</span>
    <span class="badge">{{대중제 · 18홀}}</span>
    <span class="badge">{{평점 4.5 (출처명)}}</span>
    <span class="badge">#{{키워드}}</span>
  </div>

  <div class="head">
    <div>
      <h2>{{골프장명}}</h2>
      <div class="sub">{{시·군 · 분당 기준 OO km / 약 OO분}}</div>
    </div>
    <div class="price"><small>1인 합계 {{평일/주말}} · {{확인일}}</small><b>{{OO만}}<span>원~</span></b></div>
  </div>

  <div class="body">
    <h3 class="sec-title">이용 정보</h3>
    <dl class="info">
      <div><dt>위치</dt><dd>{{주소 요약}}</dd></div>
      <div><dt>코스</dt><dd>{{18홀 · 파OO}}</dd></div>
      <div><dt>그린피</dt><dd>{{OO원 (평일/주말)}}</dd></div>
      <div><dt>카트·캐디</dt><dd>{{카트 OO · 캐디 OO}}</dd></div>
      <div><dt>예약</dt><dd>{{오픈 시점/채널}}</dd></div>
      <div><dt>편의시설</dt><dd>{{샤워 · 식당 · 연습장 등}}</dd></div>
    </dl>

    <h3 class="sec-title">포함 · 불포함</h3>
    <div class="inc">
      <ul class="yes"><li>{{포함 항목}}</li></ul>
      <ul class="no"><li>{{불포함 항목}}</li></ul>
    </div>

    <h3 class="sec-title">이런 하루는 어때요</h3>
    <ol class="flow">
      <li><b>{{06:30}}</b> 분당 출발 · {{경로}}</li>
      <li><b>{{07:45}}</b> 도착, 아침 식사 또는 연습</li>
      <li><b>{{08:30}}</b> 티오프</li>
      <li><b>{{13:00}}</b> 라운딩 후 식사 · 귀가</li>
    </ol>

    <h3 class="sec-title">후기로 본 장단점</h3>
    <div class="pc">
      <div><h3>좋았던 점</h3><ul><li>{{반복된 장점}}</li></ul></div>
      <div><h3>아쉬운 점</h3><ul><li>{{반복된 단점}}</li></ul></div>
    </div>

    <h3 class="sec-title">라운딩 전후 맛집</h3>
    <div class="food">
      <div class="dish"><div class="thumb" aria-hidden="true">🍲</div>
        <div class="t"><b>{{상호}}</b>{{대표 메뉴}}<br><span>{{가격대}} · 골프장에서 OO분</span></div></div>
      <div class="dish"><div class="thumb" aria-hidden="true">🥩</div>
        <div class="t"><b>{{상호}}</b>{{대표 메뉴}}<br><span>{{가격대}} · 골프장에서 OO분</span></div></div>
      <div class="dish"><div class="thumb" aria-hidden="true">🍜</div>
        <div class="t"><b>{{상호}}</b>{{대표 메뉴}}<br><span>{{가격대}} · 골프장에서 OO분</span></div></div>
    </div>

    <h3 class="sec-title">예약 바로가기</h3>
    <!-- 확인된 항목만 남기고 나머지 div는 삭제. 링크는 공식 사이트만. -->
    <dl class="go">
      <div><dt>공식 홈페이지</dt><dd><a href="{{공식 URL}}" target="_blank" rel="noopener">{{도메인}}</a></dd></div>
      <div><dt>전화</dt><dd>{{공식 전화번호}}</dd></div>
      <div><dt>내비 검색명</dt><dd>{{지도 앱 검색 상호}}</dd></div>
      <div><dt>우천·취소</dt><dd>{{우천 시 규정 한 줄}}</dd></div>
    </dl>
    <div class="total"><b>1인 예상 총지출 {{OO만 원}}</b> · 라운딩 {{OO}} + 식사 {{OO}}{{ + 통행료·유류는 별도}}</div>
    <div class="share"><small>카톡으로 보내기 (길게 눌러 복사)</small>{{골프장명}} · 분당에서 약 {{OO}}분
1인 {{OO만 원}}~ ({{조건}}, {{확인일}} 기준)
{{추천 이유 한 줄}}</div>

    <div class="cta"><b>예약 전 확인</b> · 요금과 운영 정보는 시즌·요일에 따라 바뀝니다. 공식 채널에서 최종 확인하세요.</div>
  </div>
</article>

<p class="note">정보 기준일 {{YYYY-MM-DD}}. 평점·요금은 {{출처 목록}}에서 확인한 값이며 실제와 다를 수 있습니다. 본 자료는 정보 제공용입니다.</p>
</main>
</body>
</html>
