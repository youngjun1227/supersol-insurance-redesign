# 슈퍼쏠 디자인 토큰 (유지 대상)

> 2026-08-17 캡처 16장 픽셀 분석으로 1차 추출. 기기 iPhone 393×852pt @3x.
> ✅ 픽셀에서 직접 확인 / ❓ 추정(안티앨리어싱·압축 오차 ±1~2pt, 라운드는 ±4) / 🔷 결정 필요
> 실제 값을 아시면 덮어써 주세요.

## ⚠️ 핵심 발견: 팔레트가 2개 섞여 있음
보험 영역 안에서 **슈퍼SOL(신한은행) 계열**과 **신한라이프 제공 화면 계열**이 서로 다른 토큰을 씀.

| | SOL 계열 (화면 01·02·03·06) | 신한라이프 계열 (화면 04·05, 01의 일부 카드) |
|---|---|---|
| Primary 블루 | `#005DF9` ✅ | `#265BF0` ✅ (텍스트/테두리는 `#3668F6`) |
| 텍스트 최상위 | `#101828` ✅ | `#111726` ✅ |
| 텍스트 본문 | `#344054` ✅ | `#495365` ✅ |
| 텍스트 보조 | `#475467` / `#667085` ✅ | `#495365` |
| 비활성/아이콘 | `#818DA2` ✅ | — |
| 페이지 배경 | `#F0F4FA` ✅ (상단 그라데이션 `#EDF1F8`) | `#FFFFFF` / 히어로 `#F8F9FC` ✅ |
| 연한 블루 배경 | `#F4F6FE` ✅ (유틸카드) | `#F1F4F9` ✅ (소개카드), `#ECF0FE` ✅ (아이콘 버튼) |
| 테두리 | `#E3E7EE` ✅ (세그먼트 트랙) | `#E4E7EB` ✅ (상품 카드) |
| Primary 버튼 | h 48 · r 8 ✅ | h 56 · r 16 ✅ |
| 텍스트 크기 | 제목 24 | 제목 25~31(더 큼) |

✅ **결정 (2026-08-17, 영준): SOL 계열(`#005DF9`, `#101828`~`#818DA2` 그레이, r 8 버튼)로 통일.**
근거·적용 방식: `docs/2026-08-17_팔레트-2계열-발견-및-기준-결정.md`. 리뷰 메모: R-01.
아래 표는 SOL 계열 기준. 신한라이프 값은 참고로만 병기.

---

## 색상 (Color)
| 토큰 | 값 | 용도 | 상태 |
|---|---|---|---|
| `color/primary` | `#005DF9` | 하단탭 선택, 링크, 카운트 숫자, 회사명 강조, Primary 버튼 | ✅ |
| `color/primary-alt` | `#265BF0` | (신한라이프 화면 CTA·SOLmate 라벨) | ✅ 참고 |
| `color/text/primary` | `#101828` | 제목, 선택된 탭 | ✅ |
| `color/text/secondary` | `#344054` | 리스트 항목, 카드 제목, 본문 | ✅ |
| `color/text/tertiary` | `#475467` | 비선택 탭, 키-값 라벨 | ✅ |
| `color/text/caption` | `#667085` | 부제, 푸터, 비선택 상단탭 | ✅ |
| `color/text/disabled` / `icon/inactive` | `#818DA2` | 하단탭 비선택, chevron | ✅ |
| `color/text/black` | `#000000` | 페이지 큰 제목("금융") | ✅ |
| `color/bg/page` | `#F0F4FA` | 금융›보험 페이지 배경 | ✅ |
| `color/bg/page-top` | `#EDF1F8` → `#F0F4FA` | 상단 그라데이션 | ✅ |
| `color/bg/surface` | `#FFFFFF` | 카드, 하단탭바, 상품 탭 페이지 배경 | ✅ |
| `color/bg/tint` | `#F4F6FE` | 유틸 카드, 캐러셀 섹션 (`#F5F7FE`) | ✅ |
| `color/bg/tint-alt` | `#F1F4F9` / `#F8F9FC` | 소개 카드 / 히어로·칩 비선택 배경 | ✅ |
| `color/bg/icon-btn` | `#ECF0FE` | 아이콘 버튼(공유) 배경 | ✅ |
| `color/bg/chip-selected` | `#344054` | 필터 칩 선택 (다크) | ✅ |
| `color/bg/segment-track` | `#E3E7EE` | 세그먼트 컨트롤 트랙 | ✅ |
| `color/border/default` | `#E4E7EB` | 상품 카드 테두리, 구분선 | ✅ |
| `color/border/light` | `#EAECF0` | 카테고리 아이콘 배경, 옅은 구분선 | ✅ |
| `color/border/strong` | `#182230` | 키-값 테이블 상단 굵은 선 | ✅ |
| `color/border/outline-btn` | `#3668F6` | 아웃라인 버튼 테두리·텍스트 | ✅ |
| `color/accent/yellow` | `#FEB201` | 스탯 아이콘 포인트 | ✅ |
| `color/accent/green` | (아이콘용) | 보험금청구 아이콘 | ❓ |

## 라운드 (Radius)
| 토큰 | 값 | 용도 | 상태 |
|---|---|---|---|
| `radius/button` | 8 | Primary 버튼 (SOL, 화면 06) | ✅ |
| `radius/button-lg` | 16 | 신한라이프 CTA (화면 05) | ✅ 참고 |
| `radius/card` | 20 | 유틸 카드, 상품 카드, 검색 인풋 | ❓ (16~24) |
| `radius/card-lg` | 24 | 금융›보험 홈 큰 카드 | ❓ |
| `radius/card-sm` | 12 | 소개 카드, 카테고리 아이콘 박스 | ✅ (12.7) |
| `radius/segment` | 16 | 세그먼트 컨트롤 | ❓ (15.3, pill일 수도) |
| `radius/pill` | 999 | 필터 칩, 하단 탭바, 뱃지 | ✅ |
| `radius/circle` | 50% | 스탯 아이콘 원(64), 하단탭 선택 원(22) | ✅ |

## 크기 (Size)
| 토큰 | 값 (pt) | 용도 | 상태 |
|---|---|---|---|
| `size/screen-width` | 393 | iPhone 기준 | ✅ |
| `size/statusbar` | ~54 | 상태바 (Dynamic Island 기기) | ✅ |
| `size/header` | ~56 | 앱 헤더 (제목 y≈78, 텍스트 21 높이) | ❓ |
| `size/tab-height` | ~48 | 상단 텍스트 탭 영역 | ❓ |
| `size/button-lg` | 48 | Primary 버튼 (SOL) | ✅ |
| `size/button-xl` | 56 | CTA 버튼 (신한라이프), 검색 인풋 | ✅ |
| `size/icon-btn` | 56 | 공유 아이콘 버튼 (56×60) | ✅ |
| `size/chip` | 36 | 필터 칩 높이 | ✅ (34.7) |
| `size/segment` | 52 | 세그먼트 컨트롤 높이 | ✅ (53.3) |
| `size/tabbar` | 62 | 하단 탭바 (플로팅 필, 폭 363) | ✅ |
| `size/tabbar-active-dot` | 22 | 선택 탭 파란 원 | ✅ |
| `size/icon-category` | 44 | 카테고리 아이콘 박스 | ✅ |
| `size/icon-stat` | 64 | 스탯 원형 아이콘 | ✅ |
| `size/icon-list` | 24 | 리스트 아이템 아이콘 | ❓ |
| `size/card-hero-home` | 140 | 금융›보험 홈 추천 카드 높이 | ✅ |

## 여백 (Spacing)
| 토큰 | 값 | 용도 | 상태 |
|---|---|---|---|
| `space/screen-h` | 20 | 기본 좌우 여백 (상품 카드, 버튼, 헤더) | ✅ |
| `space/screen-h-card` | 12 | 금융›보험 홈 큰 카드 좌우 여백 (369폭) | ✅ |
| `space/tabbar-h` | 15 | 하단 탭바 좌우 여백 | ✅ |
| `space/button-gap` | 8 | 버튼 2개 나란히 간격 | ✅ |
| `space/card-padding` | 20~24 | 카드 내부 패딩 | ❓ |
| `space/section-gap` | 16~24 | 카드 사이 세로 간격 | ❓ |
| `space/list-item-h` | 56~60 | 리스트 아이템 행 높이 (chevron형) | ❓ |

## 타이포그래피 (Typography)
글리프 높이 → 폰트 크기 환산(÷0.88). 굵기는 시각 판단.
| 토큰 | 크기 | 굵기 | 용도 | 상태 |
|---|---|---|---|---|
| `font/display` | 28~30 | Bold | 상품 상세 상품명 (화면 06) | ❓ |
| `font/h1` | 24 | Bold | 페이지 제목("금융", "모든상품"), 신한라이프 상품명 | ✅ |
| `font/h2` | 20 | Bold | 섹션 제목(보장에너지, 건강사전, "보장 7"), 상품 카드 제목 | ✅ (19~21) |
| `font/h3` | 18 | Bold | 추천 카드 제목, 유틸카드 제목 | ✅ |
| `font/body-lg` | 16~17 | Medium/Bold | 상단 탭, 리스트 아이템, 상품명, 그리드 라벨, 스탯 값, 버튼 | ✅ |
| `font/body` | 15 | Regular | 배너 문구, 키-값 라벨 | ✅ |
| `font/body-sm` | 14 | Regular | 상품 설명, 카드 본문 | ✅ |
| `font/caption` | 13 | Regular | 부제, 이벤트 링크, 푸터, 스탯 라벨 | ✅ |
| `font/label` | 12 | Medium | 하단 탭바 라벨 | ✅ |
| 패밀리 | (신한 전용 서체 추정) | | Figma에선 `Noto Sans KR` 대체 | 🔷 |

## 컴포넌트별 스펙 요약 (와이어프레임 컴포넌트 제작용)
| 컴포넌트 | 스펙 |
|---|---|
| Primary 버튼 (SOL) | h48 · r8 · bg primary · 텍스트 흰 16 Bold · 2분할 시 gap 8 |
| CTA 버튼 (신한라이프) | h56 · r16 · bg #265BF0 · 좌측 아이콘버튼 56×60 bg #ECF0FE |
| 아웃라인 버튼 | h~52 · r~12 · border #3668F6 1px · 텍스트 #3668F6 |
| 필터 칩 | h36 · pill · 선택 bg #344054 텍스트 흰 / 비선택 bg #F8F9FC border 옅음 |
| 세그먼트 | h52 · r16 · 트랙 #E3E7EE · 선택 흰 배경 |
| 하단 탭바 | 363×62 · pill · 흰 배경 · 5탭 · 선택 아이콘 원 22 primary + 라벨 12 primary |
| 카드 (홈) | 폭 369 · r24 · 흰 · h140 · 패딩 ~24 |
| 상품 카드 | 폭 353 · r~16 · border #E4E7EB · 패딩 20 |
| 유틸 카드 | 폭 367 · r~20 · bg #F4F6FE · 2행 + 구분선 |
| 카테고리 아이콘 | 44×44 · r12 · bg #EAECF0 · 라벨 16 아래 |
| 검색 인풋 | h56 · r~16 · border · 좌 텍스트 우 돋보기 |
| 스탯 아이콘 | 원 64 흰 · 라벨 13 · 값 16 Bold |
