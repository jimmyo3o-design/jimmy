<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>학교 안내좌표 구축 가이드</title>
<style>
  :root {
    --bg: #0d0d0e;
    --bg-panel: #17181a;
    --border: #2a2b2e;
    --text: #f2f2f2;
    --text-dim: #9a9ba0;
    --accent-blue: #5b9dff;
    --green-bg: #16302090;
    --green-text: #6ede8a;
    --red-bg: #35141690;
    --red-text: #ff8080;
    --amber-bg: #332a0e90;
    --amber-text: #f0c65a;
  }

  * { box-sizing: border-box; }

  body {
    margin: 0;
    background: var(--bg);
    color: var(--text);
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", "Apple SD Gothic Neo", "Malgun Gothic", sans-serif;
    line-height: 1.65;
  }

  .wrap {
    max-width: 900px;
    margin: 0 auto;
    padding: 48px 24px 96px;
  }

  .breadcrumb {
    color: var(--accent-blue);
    text-decoration: none;
    font-size: 14px;
  }
  .breadcrumb:hover { text-decoration: underline; }

  h1 {
    font-size: 28px;
    font-weight: 700;
    margin: 24px 0 16px;
    letter-spacing: -0.01em;
  }

  h2 {
    font-size: 20px;
    font-weight: 700;
    margin: 48px 0 12px;
    padding-top: 24px;
    border-top: 1px solid var(--border);
  }

  h3 {
    font-size: 16px;
    font-weight: 700;
    margin: 32px 0 6px;
  }

  p {
    color: var(--text);
    margin: 0 0 12px;
  }

  .meta {
    color: var(--text-dim);
    font-size: 14px;
    font-weight: 400;
    margin-left: 6px;
  }

  strong { color: #fff; font-weight: 700; }

  .panel {
    background: var(--bg-panel);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 20px 24px;
    margin: 20px 0;
  }

  .badges {
    display: flex;
    gap: 8px;
    margin-top: 14px;
    flex-wrap: wrap;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 6px 14px;
    border-radius: 8px;
    font-size: 14px;
    font-weight: 600;
  }
  .badge.green { background: var(--green-bg); color: var(--green-text); }
  .badge.red   { background: var(--red-bg); color: var(--red-text); }
  .badge.amber { background: var(--amber-bg); color: var(--amber-text); }

  table {
    width: 100%;
    border-collapse: collapse;
    margin: 16px 0;
    font-size: 15px;
  }
  th, td {
    text-align: left;
    padding: 10px 14px;
    border-bottom: 1px solid var(--border);
  }
  th {
    color: var(--text-dim);
    font-weight: 600;
    font-size: 13px;
    text-transform: uppercase;
    letter-spacing: 0.03em;
  }

  .case {
    margin-top: 36px;
    padding-top: 28px;
    border-top: 1px solid var(--border);
  }

  .case-title {
    font-size: 16px;
    font-weight: 700;
  }

  .case-desc {
    color: var(--text-dim);
    font-size: 14.5px;
    margin: 6px 0 16px;
  }

  .media-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .media-box {
    background: var(--bg-panel);
    border: 1px dashed var(--border);
    border-radius: 10px;
    aspect-ratio: 4 / 3;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--text-dim);
    font-size: 13px;
    text-align: center;
    padding: 12px;
  }

  .media-caption {
    text-align: center;
    color: var(--accent-blue);
    font-size: 13px;
    margin-top: 8px;
    text-decoration: underline;
  }

  @media (max-width: 640px) {
    .media-grid { grid-template-columns: 1fr; }
  }
</style>
</head>
<body>
<div class="wrap">

  <a class="breadcrumb" href="index.html">← 안내좌표 구축 가이드</a>

  <h1>1. 학교 안내좌표 구축</h1>

  <p>
    학교 카테고리는 <strong>주차장 · 정문 · 후문</strong> 위치를 기준으로 안내좌표를 구축한다.
    기본 순서는 <strong>1-주차장 → 2-정문 → 3-후문</strong>이며,
    <strong>후문에 주차장이 있는 경우</strong>에는 후문 지점에 안내좌표가 2개 생성되는 예외가 발생한다.
  </p>

  <div class="panel">
    대상 학교 카테고리 구축 기준 &nbsp;&nbsp;<strong>기본형</strong> + <strong>예외형(후문 주차장)</strong> 2가지 케이스
    <div class="badges">
      <span class="badge green">기본형 · 1-주차장 / 2-정문 / 3-후문</span>
      <span class="badge amber">예외형 · 후문 주차장 시 좌표 2개</span>
    </div>
  </div>

  <h2>기본 구축 기준</h2>
  <p>주차장, 정문, 후문이 각각 별도 위치에 있는 일반적인 학교에 적용한다.</p>

  <table>
    <tr><th>순위</th><th>위치</th><th>안내좌표 수</th></tr>
    <tr><td>1</td><td>주차장</td><td rowspan="3" style="vertical-align:middle">총 3개</td></tr>
    <tr><td>2</td><td>정문</td></tr>
    <tr><td>3</td><td>후문</td></tr>
  </table>

  <div class="case">
    <div class="case-title">예시 학교명 <span class="meta">초등학교 · 기본형</span></div>
    <div class="case-desc">주차장·정문·후문이 각각 독립된 위치에 있어 기본 순서(1-주차장/2-정문/3-후문) 그대로 구축.</div>
    <div class="media-grid">
      <div class="media-box">위성+도로망 스크린샷<br>(추가 예정)</div>
      <div class="media-box">로드뷰 스크린샷<br>(추가 예정)</div>
    </div>
  </div>

  <h2>예외 구축 기준 — 후문에 주차장이 있는 경우</h2>
  <p>
    후문 인근에 주차장이 위치한 학교는 후문 지점에 <strong>주차장용 좌표</strong>와
    <strong>후문 자체 좌표</strong>를 각각 구축하여, 후문에서만 안내좌표 2개가 생성된다.
  </p>

  <table>
    <tr><th>순위</th><th>위치</th><th>안내좌표 수</th></tr>
    <tr><td>1</td><td>후문(주차장)</td><td rowspan="3" style="vertical-align:middle">총 4개 (후문 2개 포함)</td></tr>
    <tr><td>2</td><td>정문</td></tr>
    <tr><td>3</td><td>후문</td></tr>
  </table>

  <div class="case">
    <div class="case-title">예시 학교명 <span class="meta">중학교 · 예외형(후문 주차장)</span></div>
    <div class="case-desc">주차장이 후문 쪽에 위치하여 후문 지점에 주차장 좌표와 후문 좌표가 각각 구축됨.</div>
    <div class="media-grid">
      <div class="media-box">위성+도로망 스크린샷<br>(추가 예정)</div>
      <div class="media-box">로드뷰 스크린샷<br>(추가 예정)</div>
    </div>
  </div>

  <h2>정리</h2>
  <p>주차장 유무와 위치에 따라 케이스가 나뉘며, 판단 기준은 아래와 같다.</p>
  <table>
    <tr><th>케이스</th><th>1순위</th><th>2순위</th><th>3순위</th><th>좌표 개수</th></tr>
    <tr><td>기본형</td><td>주차장</td><td>정문</td><td>후문</td><td>3개</td></tr>
    <tr><td>예외형 (주차장이 후문에 위치)</td><td>후문(주차장)</td><td>정문</td><td>후문</td><td>4개 (후문 2개)</td></tr>
  </table>

  <p class="case-desc" style="margin-top:32px;">
    ※ 위 기준은 표준 프로세스이며, 예외 상황 발견 시 파트장/담당자에게 공유 후 가이드에 반영합니다.
  </p>

</div>
</body>
</html>
