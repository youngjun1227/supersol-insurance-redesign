# 3D 일러스트 원본 — Microsoft Fluent Emoji 3D

Figma 컴포넌트 세트 `3D 일러스트 (Fluent)` **`292:3927`**. 섹션 `292:3926` 🔒, 안내 프레임 `292:3928`, 페이지 `🧩 컴포넌트 · 토큰` `5:6`.

## 라이선스
**MIT** (Microsoft Corporation) — 상업적 사용·수정·재배포 허용, **고지 불필요**. 발표·공개 저장소 모두 안전.
원본: https://github.com/microsoft/fluentui-emoji · 전체 1,285개 (3D PNG 기준)

## 왜 이걸 골랐나 (2026-08-23)
- 실제 SOL 앱이 쓰는 건 **3D 오브젝트**다. 라인 아이콘(Phosphor)으로는 그 자리를 못 메운다.
- 먼저 **unDraw**를 넣었다가 **뺐다** — 인물 중심 플랫 벡터라 형태 언어가 어긋나 "딴 앱"이 됐다.
- **3dicons.co**(CC0)는 GitHub에 에셋이 없고(웹사이트 소스뿐) 122개짜리 범용 UI 세트라 치아·리본 같은 **보험 오브젝트가 없다**.
- Fluent 3D는 ① MIT ② 1,285개라 보험 카테고리 9개가 전부 덮이고 ③ AS-IS가 쓰는 **배터리·말풍선** 모티프가 그대로 있다.

## 목록 (파일명 = Figma `Name=` 값)

### 보험 카테고리 9 (S2 체계)
| 파일 | Fluent 원본 | 비고 |
|---|---|---|
| `암.png` | **Microbe** (세포) | ⚠️ 최초에 Reminder ribbon(노란 리본)을 썼다가 **교체(8/23)**. 한국에서 노란 리본은 **세월호 추모 상징**으로 읽혀 상품 카테고리에 부적절. 세포는 라인 세트의 Phosphor `virus`와 같은 모티프라 라인/3D가 일관됨 |
| `건강.png` | Stethoscope | Anatomical heart는 **의도적으로 배제** — 사실적 심장이라 거부감 |
| `치매간병.png` | Handshake | 돌봄 |
| `치아.png` | Tooth | |
| `상해.png` | Adhesive bandage | |
| `여행레저.png` | Airplane | |
| `그밖의보장.png` | Shield | |
| `연금저축.png` | **Abacus** (주판) | Money bag에 `$` 표시가 있어 원화 화면에 안 맞아 **교체(8/23)** |
| `변액.png` | **Seedling** (새싹) | Chart increasing은 격자가 납작해 3D 결이 약해 **교체(8/23)**. 단, 새싹은 '성장'만 담고 변액의 '변동(손실 가능성)'은 담지 않음 — 한계로 기록 |

### 배너·팝업·기타 9
| 파일 | Fluent 원본 | 쓰는 자리 |
|---|---|---|
| `보장에너지.png` | Battery | 보장에너지 카드 — **AS-IS와 같은 모티프** |
| `청구서류.png` | Receipt | S4-A 팝업·바텀시트 |
| `상담.png` | Speech balloon | 상담 진입 — **AS-IS와 같은 모티프** |
| `이벤트.png` | Wrapped gift | 프로모션 배너 (곰 자리 대체) |
| `축하.png` | Party popper | 프로모션 배너 |
| `포인트.png` | Coin | 리워드 · `$` 없음 |
| `공지.png` | Megaphone | 공지 배너 |
| `혜택.png` | Trophy | 혜택 배너 |
| `신규추천.png` | Sparkles | 신규·추천 뱃지 |

## ⚠️ 주의
- **래스터(PNG) 256×256.** 색상 변수 바인딩 불가, SOL 모드 전환에 안 따라옴. 톤을 맞춰야 하는 자리는 Phosphor.
- **색이 오브젝트마다 다르다.** SOL 블루 단색이 아님. (AS-IS도 컬러 미니 일러스트가 뒤섞여 있어 실물에 더 가까움 — `디자인.md` §7 측정 한계 문단 참고)
- 크기: 카테고리 아이콘 **48~64** / 배너·팝업 **96~160**.

## 새 오브젝트가 필요하면
`https://raw.githubusercontent.com/microsoft/fluentui-emoji/main/assets/<이름>/3D/<소문자_밑줄>_3d.png`
예: `assets/Tooth/3D/tooth_3d.png`. 전체 목록은 GitHub API 트리로 확인.
**임의로 다른 3D 세트(3dicons·Iconscout 등)를 섞지 말 것** — 렌더 스타일이 달라 결이 갈린다.
