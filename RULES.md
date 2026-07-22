


---

## 2. CSS 규칙

### 2-1. 반드시 지켜야 할 것
- **하드코딩 hex 색상 금지** → 반드시 변수 사용
- **`!important` 사용 금지** → 구조로 해결할 것
- **`body` 클래스 셀렉터 금지** → `.vision-page`, `.business-page` 등 사용 금지
- **font-weight 800 사용 금지** → 최대 700


```

---

## 3. 컬러 규칙

### 3-1. 시맨틱 변수만 사용할 것
| 용도 | 변수명 |
|------|--------|
| 기본 텍스트 | `var(--text-primary)` |
| 보조 텍스트 | `var(--text-secondary)` |
| 비활성 텍스트 | `var(--text-disabled)` |
| 흰색 텍스트 | `var(--text-inverse)` |
| 블루 강조 텍스트 | `var(--text-accent)` |
| 기본 배경 | `var(--bg-primary)` |
| 섹션/카드 배경 | `var(--bg-secondary)` |
| 다크 배경 | `var(--bg-dark)` |
| 기본 보더 | `var(--border-color)` |
| 강조 보더 | `var(--border-strong)` |
| 메인 블루 | `var(--primary)` |
| 호버 블루 | `var(--primary-hover)` |

### 3-2. 절대 사용 금지 하드코딩 값
```
#4e6eff  →  var(--primary)
#2D65F3  →  var(--primary)
#001cff  →  var(--primary-700)
#2B3A8B  →  var(--primary-dark)
#111111  →  var(--text-primary)
#666666  →  var(--text-secondary)
#E4E4E4  →  var(--border-color)
```

### 3-3. 시스템 컬러(신호등) — 상태 4색 고정 세트 (`css/tokens.css`)
진행/처리 상태를 나타낼 때는 색을 새로 정하지 말고 아래 4개만 사용한다. 빨강/주황/초록/파랑 4색이며, 의미가 고정되어 있다.

| 색 | 변수명 | 의미 |
|----|--------|------|
| 초록 | `--status-positive` / `--status-positive-bg` | 완료 |
| 파랑 | `--status-info` / `--status-info-bg` | 조치중 |
| 주황 | `--status-caution` / `--status-caution-bg` | 미조치 |
| 빨강 | `--status-negative` / `--status-negative-bg` | 지연(기한초과) |

- **긍정 위계(좋은 순 → 나쁜 순): 초록 > 파랑 > 주황 > 빨강** — 진행률 바, 상태 정렬 등에서 이 순서를 따른다
- 등급/카테고리용 파스텔 4색(`--label-*`, 9-3 참고)과는 별개 — 이쪽은 "상태"에만 쓰는 고정 의미 색이라 임의로 다른 용도에 섞어 쓰지 않는다

---

## 4. 타이포그래피 규칙

### 4-1. 폰트 사이즈 — 이 변수만 사용
| 변수명 | 크기 | 용도 |
|--------|------|------|
| `--fs-display` | 50px+ | 메인 비주얼 전용 |
| `--fs-h1` | 42px | 서브 섹션 대제목 (국문) ★ |
| `--fs-h1-en` | 44px | 서브 섹션 대제목 (영문) ★ |
| `--fs-sub-h1` | 50px | 서브 페이지 H1 |
| `--fs-40` | 40px | h1~h2 사이 대제목 |
| `--fs-38` | 38px | h1~h2 사이 중제목 |
| `--fs-36` | 36px | h1~h2 사이 소제목 |
| `--fs-h2` | 32px | 섹션 소제목 |
| `--fs-h3` | 24px | 카드 타이틀 |
| `--fs-h4` | 20px | 강조 본문 |
| `--fs-body` | 18px | 기본 본문 ★ |
| `--fs-small` | 15px | 보조 텍스트 |
| `--fs-caption` | 14px | 라벨/배지 |

### 4-2. 폰트 굵기
```
700 → display 전용 (비주얼 큰 타이틀)
600 → 제목류 (h1~h4)
400 → 본문
```

### 4-3. 행간 (line-height)
| 변수명 | 값 | 용도 |
|--------|-----|------|
| `--lh-tight` | 1.1 | 대형 비주얼, hero 숫자 |
| `--lh-heading` | 1.2 | 1줄 제목 |
| `--lh-title` | 1.4 | 2줄 제목 ★ |
| `--lh-normal` | 1.5 | 일반 텍스트 |
| `--lh-body` | 1.8 | 본문 |

### 4-4. 폰트 패밀리 — SamsungOne 단일 사용
전사 기준 한글/영문/숫자 모두 `SamsungOne` 하나로 통일. 별도 영문 전용 폰트(Poppins 등) 사용 금지.
```css
font-family: var(--font-base); /* = var(--font-point), SamsungOne */
letter-spacing: var(--ls-point); /* 영문 타이틀/숫자 자간 보정 시에만 */
```



| 항목 | 변수 | 값 |
|------|-----|-----|
| 컨텐츠 상단 | `var(--space-25)` | 100px |
| 섹션 내부 간격 | `var(--space-20)` | 80px |
| 컨텐츠 하단 | `var(--space-37)` | 150px |



## 8. Border Radius 규칙

### 8-1. 변수만 사용할 것
| 변수명 | 값 | 용도 |
|--------|-----|------|
| `--radius-none` | 0px | 라운드 없음 |
| `--radius-xs` | 2px | 배지, 태그, 필터버튼 |
| `--radius-sm` | 4px | 이미지, 카드 기본 **★ 주력**, 인풋/드롭다운/버튼 |
| `--radius-md` | 8px | 팝업 |
| `--radius-lg` | 16px | 큰 카드, 모달 |
| `--radius-xl` | 24px | 특수 컴포넌트 |
| `--radius-full` | 50px | 필 버튼, 태그 |
| `--radius-circle` | 50% | 프로필, 로고 원형 |

### 8-2. 기본 원칙
- 사이트 전체 기조는 **샤프(Sharp)** → `--radius-sm(4px)` 위주 사용
- 강조/인터랙티브 요소만 `--radius-md(8px)` 이상 사용
- 특수 컴포넌트(다이어그램 박스 등)는 예외적으로 하드코딩 허용

---

## 9. 차트 색상 규칙

### 9-1. 도넛차트 — 고정 4색 세트 (`css/tokens.css`)
차트마다 색을 새로 정하지 말고, 비중이 큰 세그먼트부터 작은 세그먼트 순서로 아래 4개를 고정 사용한다.

| 변수명 | 실제 값 | 순서 |
|--------|---------|------|
| `--chart-donut-1` | `#1E6FF7` 진한 블루 | 1순위 (최대 비중) |
| `--chart-donut-2` | `#00D0FF` 브라이트 시안 | 2순위 |
| `--chart-donut-3` | `#A5ECFA` 페일 시안 | 3순위 |
| `--chart-donut-4` | `#BACDFC` 라이트 라벤더블루 | 4순위 (최소 비중) |

- 범례 dot도 대응하는 `.legend-dot--chart-1` ~ `.legend-dot--chart-4` 클래스만 사용
- 세그먼트가 5개 이상 필요하면 이 규칙에 없는 것이므로, 임의로 색을 추가하지 말고 먼저 협의

### 9-2. 바차트(세그먼트 바) — 고정 6색 세트 (`css/tokens.css`)
바차트도 마찬가지로 색을 새로 정하지 말고, 아래 6개를 순서대로 고정 사용한다.

| 변수명 | 실제 값 | 순서 |
|--------|---------|------|
| `--chart-bar-1` | `#2DA1FE` 블루 | 1순위 (해칭 적용) |
| `--chart-bar-2` | `#6889FE` 인디고 | 2순위 |
| `--chart-bar-3` | `#B470FE` 퍼플 | 3순위 |
| `--chart-bar-4` | `#FF71C5` 핑크 | 4순위 |
| `--chart-bar-5` | `#FD9E42` 오렌지 | 5순위 |
| `--chart-bar-6` | `#B7CFFE` 라이트 블루 | 6순위 |

- 범례 swatch는 `.swatch--chart-1` ~ `.swatch--chart-6`, 바 세그먼트는 `.segment-bar__seg--chart-1` ~ `--chart-6`만 사용
- 도넛과 바차트는 색 순서/의미가 다르므로(`--chart-donut-*` vs `--chart-bar-*`) 서로 섞어 쓰지 않는다
- **바차트(`.segment-bar--lg`) 세그먼트는 서로 붙이지 않고 4px 간격으로 끊어서 표현한다** — 컨테이너는 `gap: 4px; overflow: visible;`, 각 세그먼트는 `border-radius: var(--radius-sm)`로 개별 pill 형태.

### 9-3. 라벨/뱃지 — 파스텔 4색 고정 세트 (`css/tokens.css`)
등급 배지(A/B/S급 등), 상태 라벨(진행중/완료), KPI 트렌드 pill처럼 색 있는 작은 텍스트 칩이 필요한 모든 곳에서 아래 4개만 사용한다. 색을 새로 만들지 말 것 — 자리마다 의미(등급, 상태 등)에 맞게 이 중에서 고른다.

| 변수명 | 실제 값 | 용도 예시 |
|--------|---------|-----------|
| `--label-blue` / `--label-blue-bg` | `var(--primary)` / `var(--primary-50)` | A급, 진행중, 당월 등 |
| `--label-green` / `--label-green-bg` | `var(--status-positive)` / `var(--status-positive-bg)` | 완료, 증가(+n%) 등 |
| `--label-purple` / `--label-purple-bg` | `#A855F7` / `#F3E8FF` | B급 등 |
| `--label-orange` / `--label-orange-bg` | `var(--status-caution)` / `var(--status-caution-bg)` | S급 등 |

- 공통 컴포넌트는 `.label-pill--blue/green/purple/orange` (표·리스트용 소형 pill), `.kpi-pill--blue/green/purple/orange` (KPI 카드용, 아이콘+텍스트) 두 종류. 새 화면에서 색 있는 라벨이 필요하면 이 중 맞는 컴포넌트+색을 그대로 가져다 쓴다.
- 적용 예: `site-dashboard.html`의 "전체 협력사 현황"(+21, green) / "신규 등록 협력사"(당월, blue) 카드

---

## 10. 버튼 규칙

### 10-1. 위계(Hierarchy) — 4단계 고정
버튼은 아래 4단계 중요도 순서를 따른다. 새 버튼을 추가할 때 이 표에서 맞는 단계를 그대로 고른다.

| 단계 | 클래스 | 스타일 | 용도 |
|------|--------|--------|------|
| 1. CTA | `.btn-primary` | 프라이머리 컬러 Fill + 흰색 텍스트 | 핵심 CTA — 페이지당 1개 원칙 (예: 작성, 결재상신) |
| 2. 보조 CTA | `.btn-outline.btn-outline--primary` | 프라이머리 스트록 + 프라이머리 텍스트 | Primary와 나란히 쓰는, 그보다 한 단계 낮은 중요 액션 (예: 검색, 보고서출력) |
| 3. 일반 액션 | `.btn-outline` | 회색 스트록 + 검정(`--text-primary`) 텍스트 | 목록/수정/삭제처럼 일반적인 보조 액션. `--negative` 조합 시 삭제 등 위험 액션(빨강 스트록/텍스트) — 단, 위험도가 다른 액션과 같은 급이면 굳이 빨강 안 씀 |
| 4. 아이콘 버튼 | `.icon-btn` / `.attach-icons i` / `.pagination__arrow` 등 | 회색 스트록 + 아이콘만 | 텍스트 라벨 없이 아이콘 하나로 의미가 통하는 기능성 버튼 (10-3 예외 규정과 동일) |

- `.btn-outline`(및 `--primary`/`--negative`)은 기본 `--control-height`(40px), 표 안 등 좁은 자리에서는 `.btn-outline--sm`(`--control-height-sm`, 32px) 조합
- `.btn-ghost`(텍스트만, 테두리 없음)는 취소/뒤로가기처럼 4단계보다도 더 낮은 강조가 필요할 때 예외적으로 사용
- **필(Fill, 배경색+반대색 텍스트) 스타일은 원칙적으로 CTA(1단계) 전용.** CTA가 아닌데 필 버튼이 꼭 필요하면 프라이머리 블루 대신 진한 그레이(`--gray-800`) 배경 + 흰 텍스트를 쓴다 — 블루 필은 항상 "이 페이지의 핵심 액션"이라는 신호로만 남겨둔다
- **페이지네이션 활성 페이지는 버튼 위계에 포함되지 않는다.** 내비게이션 상태 표시일 뿐이라 필/보더 없이 굵은 검정(`--text-primary`) 텍스트로만 구분 (`.pagination__page--active`)
- 상세 화면 예시: `council-detail.html` — 결재상신(1단계) + 보고서출력/수정/목록(3단계) + 삭제(3단계 `--negative`) + 첨부파일 미리보기(4단계 아이콘 버튼)

### 10-2. Size — 세로 높이 기준 3단계
버튼/인풋 등 폼 컨트롤의 크기는 **세로(height) 기준**으로 아래 3단계만 사용한다. 자리에 맞춰 임의로 다른 높이를 쓰지 않는다.

| 변수 | 값 | 용도 |
|------|-----|------|
| `--control-height` | 40px | 기본 — 본문 영역의 버튼/인풋/드롭다운 (검색, 작성, 결재상신, 보고서출력/수정/목록 등) |
| `--control-height-topbar` | 36px | topbar 전용 — 언어/사업장 선택, 알림 아이콘 버튼 |
| `--control-height-sm` | 32px | 컴팩트 — 테이블/리스트 안(서명하기, 첨부파일 아이콘, 페이지네이션 등) |

### 10-3. 아이콘 사용 금지 — 텍스트만
- **텍스트가 있는 버튼(액션 버튼)에는 아이콘을 넣지 않는다.** 검색, 작성, 저장, 언어/사업장 선택 등 라벨이 있는 버튼은 텍스트만으로 구성.
  - 예: `검색` (❌ `<i class="ri-search-line"></i>검색`), `작성`, `한국어`, `수원 사업장`
- **예외 — 아이콘 하나로만 의미가 통하는 기능성 버튼**은 그대로 아이콘만 사용 가능 (텍스트 라벨을 붙이지 않는 버튼에 한함):
  - 알림 벨(`.icon-btn`), 페이지네이션 이전/다음 화살표, 드롭다운/콤보박스 선택 지우기(X), 트리 펼침·접힘 토글 화살표 등
- 판단 기준: **버튼에 텍스트 라벨이 이미 있으면 아이콘 금지. 텍스트 라벨이 아예 없는 순수 아이콘 버튼만 예외.**

---

## 11. 상세화면 공통 컴포넌트 (`council-detail.html` 기준)

새 상세/조회 화면을 만들 때 아래 컴포넌트를 그대로 재사용한다.

| 컴포넌트 | 클래스 | 용도 |
|---------|--------|------|
| 시트 레이아웃 | `.panel.panel--sheet` > `.detail-section` | 상세화면 전체를 **하나의 흰 종이**로. 섹션마다 별도 박스/카드로 나누지 않고, `.detail-section`의 여백(padding)만으로 섹션을 구분 (경계선 없음) |
| 섹션 제목 | `.section-heading` (+ `.section-heading__mark`) | "■ 기본정보" 같은 소제목 — 같은 위계의 섹션(예: 참석자 및 서명 / 내부 참석자 / 협력업체 참석자)은 전부 동일한 `.section-heading` 사용, 크기 줄이지 않음 |
| 라벨/값 표 | `.info-table` (`th.info-table__label` + `td.info-table__value`) | 기본정보, 회의 내용, 서명방식처럼 라벨-값 쌍으로 된 정보는 전부 이 표 하나로 통일. 라벨 셀만 회색 배경(`--bg-secondary`), 셀마다 테두리로 격자 구성. `colspan`으로 넓은 값 칸 처리 |
| 목록형 표 | `.data-table`(리스트 화면) / `.plain-table`(상세화면) | 반복되는 행 데이터(협력업체, 참석자 등). 둘 다 셀마다 테두리 + 헤더 행 회색 배경으로 **동일한 규칙**을 따름 — 10-4 참고 |
| 파일 첨부 | `.file-list` > `.file-chip` | 첨부파일 목록 (아이콘 + 파일명 칩, 세로 나열) — 칩 자체는 개별 요소라 테두리 유지 |
| 이미지 없음 placeholder | `.photo-thumb` | 사진 없을 때 회색 박스 + "이미지 없음" 텍스트 |
| 2열 배치 | `.attendee-grid` > `.attendee-col` | 내부/협력업체 참석자처럼 표 두 개를 나란히. 감싸는 별도 박스 없이 시트 안에 바로 배치 |

- 새 컴포넌트를 만들기 전에 이 표부터 확인
- **원칙: 상세화면은 섹션이 달라도 칸칸이 박스로 끊지 말고 하나의 배경(흰 종이)을 쓴다.** 구분은 `.detail-section`의 여백만으로 표시, 경계선 없음

### 11-1. 표(테이블) 셀 규칙 — 리스트/상세 공통
`.data-table`(리스트)와 `.plain-table`(상세)은 서로 다른 화면에서 쓰이지만 **셀 규칙은 완전히 동일하게 유지한다.**

| 항목 | 값 |
|------|-----|
| 행 높이(th/td 공통) | `height: 44px` (패딩이 아니라 **고정 높이**로 지정) |
| 셀 좌우 패딩 | `0 16px` (상하 패딩 없음 — 높이는 오직 `height`로 통일) |
| 세로 정렬 | `vertical-align: middle` |
| 헤더 행(th) 배경 | `var(--bg-secondary)` |
| 셀 테두리 | 상/하/우 `1px solid var(--border-color)`. **좌측 보더는 아예 없음**, 각 행의 **마지막 칸만 우측 보더도 없음** |

- **행 높이를 패딩으로 맞추지 않는다.** 순수 텍스트 행과 버튼(`.btn-outline--sm` 등)이 든 행은 내용물 크기가 달라서, 상하 패딩으로만 높이를 주면 행마다 높이가 달라진다 — 반드시 `height`로 고정하고 `vertical-align: middle`로 내용을 가운데 맞춘다
- **테두리 원칙: 상/하 보더는 모든 셀에 항상, 좌/우 보더는 칸과 칸 사이(내부)에만.** 표의 가장 바깥쪽 좌측(첫 칸 왼쪽)과 우측(마지막 칸 오른쪽)에는 세로선을 긋지 않는다 — 즉 `border-right`를 모든 셀에 주고 `:last-child`만 `border-right: none`으로 없앤다. `border-left`는 아예 선언하지 않는다
- `.info-table`도 동일한 테두리 원칙을 따른다 (라벨 셀 배경만 다르고, 상/하/내부우측 보더 규칙은 동일)
- 값을 바꿀 때는 `.data-table`, `.plain-table`, `.info-table` 세 클래스를 항상 같이 수정

---

## 12. 팝업(모달) 규칙 — A4 인쇄 대응 (`council-detail.html` "결재정보" 예시)

| 컴포넌트 | 클래스 | 비고 |
|---------|--------|------|
| 오버레이 | `.modal-overlay` (+ `.is-open`로 열기/닫기) | `position: fixed; inset: 0`, 반투명 검정 배경, 중앙 정렬 |
| 팝업 박스 | `.modal` | `max-width: 794px` — **A4 폭(210mm, 96dpi 기준) 그대로 사용**해서 화면과 인쇄 폭이 같음 |
| 헤더 | `.modal__header` > `.modal__title` + `.modal__close`(X, 아이콘 전용이라 10-3 예외) | |
| 본문 | `.modal__body` | 내용은 상세화면과 동일하게 `.detail-section` + `.info-table`/`.plain-table` 재사용 |
| 폼 필드 | `.form-field` (`.form-field__label` + `.form-field__required`), 텍스트는 `.filter-input`, 여러 줄은 `.form-textarea` | 인풋/버튼 색상·라운드·포커스 규칙 전부 기존 시스템 그대로 |

- **팝업 안에서도 새 컴포넌트를 만들지 않는다.** 기본정보/협력업체/회의 내용/참석자 섹션은 상세화면에 이미 있는 `.info-table`/`.plain-table`/`.section-heading`을 그대로 재사용
- **인쇄 시 숨길 요소는 `.no-print` 클래스**로 표시한다 (닫기 버튼, 결재선/상신 버튼, 인풋 지우기 버튼, 파일 업로드 컨트롤 등 — 실제 결재 문서 내용이 아닌 조작용 UI). `@media print`에서 `.modal-overlay` 이외의 body 자식은 전부 숨기고 `.modal`만 출력
- 화면설계서의 버튼 아이콘(결재선 돋보기 등)은 10-3 규칙에 따라 텍스트만 남기고 제거
- 이 "결재정보" 팝업 구조가 **앞으로 만드는 모든 팝업의 기본 틀**이다 — 새 팝업은 여기서부터 시작한다

---

## 13. 등록/수정 폼 규칙 (`council-form.html` 예시)

| 컴포넌트 | 클래스 | 비고 |
|---------|--------|------|
| 필수 항목 표시 | `.info-table__label` 안에 `<span class="form-field__required">*</span>` | 팝업 폼필드와 동일한 빨강 별표 재사용 |
| 읽기 전용 값 | `.info-table__value--readonly` | 작성자/작성일자처럼 자동 입력되고 수정 불가한 값 (인풋 아님, 일반 텍스트 + 보조 텍스트 색) |
| 텍스트 입력 | `.filter-input` (기존 리스트 필터와 동일 컴포넌트) | 날짜처럼 아이콘이 필요하면 `.filter-input-icon` 그대로 재사용 |
| 여러 줄 입력 | `.form-textarea` | 팝업과 동일 컴포넌트 |
| 파일 업로드 | `.btn-outline.btn-outline--sm` "파일 업로드" + `ri-information-line` 안내 아이콘 | 팝업의 파일 업로드와 동일 패턴 |
| 표 행 추가 | `.table-add-btn` (기본), `.table-add-btn--primary` (강조/검색추가 등 대안 액션) | 아이콘 전용 버튼이라 10-3 예외. 헤더 오른쪽 칸에 배치 |
| 표 행 삭제 | `.table-remove-btn` | 각 데이터 행의 마지막 칸에 배치 |
| 표 안 인풋 | `.plain-table__row-input` | `.plain-table` 셀 안에서 쓰는 인라인 입력 (control-height-sm 높이) |
| 빈 상태 | `.plain-table__empty` | 데이터 없을 때 "OO를 추가해 주세요." 안내 텍스트, `colspan`으로 전체 폭 사용 |

- 버튼 위계: **프리셋 불러오기 = CTA**(`.btn-primary`, 맨 오른쪽), **저장/취소 = 3단계**(`.btn-outline`, 회색 스트록+검정 텍스트) — 화면설계서엔 아이콘이 있었지만 10-3 규칙대로 제거
- 표 행 추가/삭제는 매번 새로 만들지 말고 `.table-add-btn`/`.table-remove-btn`/`.plain-table__row-input`/`.plain-table__empty` 조합을 그대로 재사용