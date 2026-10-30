# Free LLM Tracker — 기준선 (2026-10-30)

<p class="notice">
Hermes Agent(OCI 무료 인스턴스)에 연결할 무료 LLM API 제공자 조사 기준선.<br>
모든 수치는 2026-10-30 기준 공식 문서·가격 페이지 또는 3자 검증 자료 기준이며,<br>
'미확인'은 조사 시점에 확인되지 않은 항목임.
</p>

**읽는 법**
- 제공자는 **Hermes에서 쓰기 좋은 순서**로 정렬 (판단 기준: API 제공 여부 → 무료 한도 → 도구 호출 지원 → 안정성).
  API를 제공하지 않는 곳(Cline)은 맨 아래 '연동 불가' 섹션에 분리.
- 각 제공자의 무료 모델은 **사용성 좋은 순으로 대표 3개만 목록으로 표시**하고, 전체 목록은 '더보기'를 눌러 공식 페이지 링크에서 확인 ('더보기'는 GitHub 저장소 화면에서도 펼쳐볼 수 있음).
- 제공자명 옆의 색상 뱃지는 우선순위 (초록=높음, 노랑=중간, 회색=낮음, 빨강=연동 불가).
- 정기 체크(매일 06:00 / 18:00 KST)는 본문을 항상 최신 상태로 갱신하고,
  변경된 사실은 맨 아래 '변경 이력'에 날짜순으로 한 줄씩 추가함.

<details>
<summary>목차</summary>

- [성능 비교](#perf)
- [Groq](#groq)
- [NVIDIA NIM](#nvidia-nim)
- [OrcaRouter](#orcarouter)
- [Google AI Studio — Gemini](#gemini)
- [OpenRouter](#openrouter)
- [AIHubMix](#aihubmix)
- [Z.ai](#z-ai)
- [LLM7.io](#llm7)
- [OpenCode Zen](#opencode-zen)
- [Token Harbor](#token-harbor)
- [Nous Portal (Hermes Agent)](#nous-portal)
- [AnyAPI](#anyapi)
- [Api.Airforce](#api-airforce)
- [Agnes AI](#agnes-ai)
- [BazaarLink](#bazaarlink)
- [Ollama Cloud](#ollama-cloud)
- [Cline](#cline)
- [기간 한정 무료](#limited-free)
- [변경 이력](#changelog)

</details>

<a id="perf"></a>

## 성능 비교

- [추천 무료 모델 바로 비교](https://artificialanalysis.ai/models/comparisons?compare=kimi-k2-5,gpt-oss-120b,deepseek-v4-1-flash): 클릭하면 바로 비교 화면이 열립니다.
  <details>
  <summary>링크 구성 안내</summary>

  - 상단 표: 대표 무료 3종 (Kimi K2.5, gpt-oss-120b, DeepSeek V4.1 Flash) 순서대로 표시
  - 하단 차트: AA 기본 28종 표시 (비교 중인 3종 포함)
  - Gemini 2.5 Flash는 상단 표 선택기에서 고를 수 없어 제외
  - 프론티어 모델(GPT·Claude·Gemini 최신)은 페이지에서 직접 추가 가능

  </details>

  <details>
  <summary>대표 모델 선정 기준</summary>

  - 이 링크의 모델은 Hermes Agent 무료 플랜 후보 중 제공자별 대표 플래그십입니다.
  - 제공자는 Hermes 적합도 순으로 정렬하며, 기준은 **API 제공 여부 → 무료 한도 → 도구 호출 지원 → 안정성**입니다.
  - 제공자별 별칭(`:free`, `-free` 등)이나 스냅샷 표기(`-0731` 등)는 제외하고 기반 모델명으로 비교합니다. (AA에서는 기반 모델명으로 검색)

  </details>

- [Artificial Analysis 모델 비교](https://artificialanalysis.ai/models): 모델 선택기로 여러 모델을 지정해 지능(Intelligence Index)·속도·가격을 차트에서 나란히 비교 가능. 모델별 전용 페이지에서는 유사 모델과의 직접 비교도 제공.

<a id="groq"></a>

## Groq (이전 조사) <span class="prio p-high">높음</span>

- **대표 무료 모델 (사용성 순):**
  - `openai/gpt-oss-120b` — 한도 문서에 명시된 무료 모델
  - `openai/gpt-oss-20b` — 경량·고속
  - `qwen/qwen3.8-27b` — 한도 문서에 명시된 무료 모델
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - GPT/Claude/Gemini/Llama 채팅 계열은 무료 테이블에 없음.
  - 전체 무료 모델 목록: [Groq 한도 문서](https://console.groq.com/docs/rate-limits) — 무료 테이블에 명시된 모델 기준 (정확한 목록은 가입 후 계정 limits 페이지에서 확인)

  </details>

- **한도**: 공식 한도 문서의 공개 테이블 기준 — gpt-oss-120b/20b, qwen3.8-27b에 30 RPM / 1K RPD / 8K TPM / 200K TPD (2026-09-24 직접 확인). `openai/gpt-oss-safeguard-20b`는 2026-10-05 18:00 확인 기준 한도 하향 — 5 RPM / 1K RPD / 2K TPM / 200K TPD (공식 한도 문서 직접 추출) 후, 2026-10-06 18:00 재확인에서 RPM 5→3으로 추가 하향 (3 RPM / 1K RPD / 2K TPM / 200K TPD). Llama 3.1/3.3 채팅 모델은 2026-08-16 종료 이후 무료 테이블에 없음 (2026-09-17 3자 검증 "free plan에 Llama 없음"). 정확한 무료 티어 수치는 계정 limits 페이지에서 확인 필요.
- **API**: OpenAI 호환. 엔드포인트 `https://api.groq.com/openai/v1`
- **도구 호출**: 지원
- **제한**: 카드 불필요. 학습 활용 안 함 (커뮤니티 보고 기준).
- **출처**: https://console.groq.com/docs/rate-limits
- **비고**: 속도 매우 빠름 (LPU, 300~1000+ tok/s). 완전 무료 조합의 메인 후보. 2026-10-20 06:00 확인: 공식 한도 문서에서 "free" 문구가 사라지고 "Developer plan의 기본 한도" 표기로 변경 — 수치(30 RPM / 1K RPD / 8K TPM / 200K TPD 등)는 동일. 실제 무료 정책 폐지인지는 텍스트만으로 확정 불가 — 관찰 유지 (출처: https://console.groq.com/docs/rate-limits).

<a id="nvidia-nim"></a>

## NVIDIA NIM (build.nvidia.com) <span class="prio p-high">높음</span>

- **대표 무료 모델 (사용성 순):**
  - `nvidia/nemotron-3.5-super-vl-120b-a12b` — 멀티모달 VL MoE (2026-10-16 공식 무료 라인업 교체 확인)
  - `deepseek-ai/deepseek-v4.1-flash` — 고속 플래그십 (2026-10-09 무료 라인업 교체 확인)
  - `nvidia/nemotron-3-ultra-550b-a55b` — 초대형 MoE (2026-09-30 확인)
  - `nvidia/nemotron-3.5-lightning-30b-a3b` — 경량 고속 (2026-09-30 확인)
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 전체 무료 모델 목록: [NVIDIA NIM 무료 모델 목록 — Free Endpoint 필터](https://build.nvidia.com/models?filters=nimType%3Anim_type_preview) — 모델 목록 페이지에서 'Free Endpoint' 필터를 켠 주소로, 무료 엔드포인트 모델만 모아볼 수 있음 (2026-10-21 18:00 라이브 브라우저 직접 확인 — 필터 적용 시 42종 표시. 2026-10-23 18:00 재확인에서 43종 (42→43, 1종 증가), 모든 카드에 'Free Endpoint' 배지, 주소를 직접 열어도 필터 유지됨). 기존에 걸려 있던 메인 주소(`https://build.nvidia.com`)는 무료 목록으로 바로 가지 않아 이 주소로 교체함.
  - 2026-10-30 06:00 라이브 브라우저 직접 확인 (뒤늦게 도착한 결과로 확정): Free Endpoint 필터 44종→45종 (1종 증가, 필터 카운트 'Free Endpoint 45', 본문 '45 models' 표시 — 증가 모델 특정 불가, 단 3자 자료의 `mistralai/mistral-large-4-1t-a52b` 무료 엔드포인트 추가 단서와 일치). 메인 'Free inference' 대표 무료 4종(`nvidia/nemotron-3.5-super-vl-120b-a12b`·`deepseek-ai/deepseek-v4.1-flash`·`nvidia/nemotron-3.5-lightning-30b-a3b`·`nvidia/nemotron-3-ultra-550b-a55b`)은 유지 — 대표 변경 없음 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview).

  - 2026-10-29 18:00 라이브 브라우저 직접 확인: Free Endpoint 필터 44종 유지 (필터 카운트 'Free Endpoint 44', 본문 '44 models' 표시). 메인 'Free inference' 대표 무료 4종(`nvidia/nemotron-3.5-super-vl-120b-a12b`·`deepseek-ai/deepseek-v4.1-flash`·`nvidia/nemotron-3.5-lightning-30b-a3b`·`nvidia/nemotron-3-ultra-550b-a55b`)은 유지 — 아침 워치의 텍스트 추출본이 2026-10-20 스냅샷이라 재확인으로 쓰지 못했던 공백을 이번 저녁 라이브 확인으로 해소 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview).

  - 2026-10-28 18:00 라이브 브라우저 직접 확인: Free Endpoint 필터 45종→44종 (1종 감소, 제거 모델 특정 불가 — 필터 카운트 'Free Endpoint 44', 본문 '44 models' 표시). 메인 'Free inference' 대표 무료 4종(`nvidia/nemotron-3.5-super-vl-120b-a12b`·`deepseek-ai/deepseek-v4.1-flash`·`nvidia/nemotron-3.5-lightning-30b-a3b`·`nvidia/nemotron-3-ultra-550b-a55b`)은 유지 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview).

  - 2026-10-25 06:00 라이브 브라우저 직접 확인: Free Endpoint 필터 45종 유지 (필터 카운트 'Free Endpoint 45'). 메인 'Free inference' 대표 무료 4종(`nvidia/nemotron-3.5-super-vl-120b-a12b`·`deepseek-ai/deepseek-v4.1-flash`·`nvidia/nemotron-3.5-lightning-30b-a3b`·`nvidia/nemotron-3-ultra-550b-a55b`)은 유지 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview).
  - 2026-10-24 06:00 라이브 브라우저 직접 확인: Free Endpoint 필터 43종→45종 (필터 카운트 'Free Endpoint 45', 2종 증가). 메인 'Free inference' 대표 무료 4종(`nvidia/nemotron-3.5-super-vl-120b-a12b`·`deepseek-ai/deepseek-v4.1-flash`·`nvidia/nemotron-3.5-lightning-30b-a3b`·`nvidia/nemotron-3-ultra-550b-a55b`)은 유지 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview).
  - 메인 페이지 'Free inference with leading models' 섹션의 대표 무료 라인업 (예고 없이 변경됨, 2026-10-16 기준 4종: `nvidia/nemotron-3.5-super-vl-120b-a12b`, `deepseek-ai/deepseek-v4.1-flash`, `nvidia/nemotron-3.5-lightning-30b-a3b`, `nvidia/nemotron-3-ultra-550b-a55b`). `moonshotai/kimi-k3`는 2026-10-16 확인에서 `nvidia/nemotron-3.5-super-vl-120b-a12b`로 교체됨 (페이지 전체 텍스트에 'kimi' 언급 없음, 라이브 브라우저 재확인).
  - `meta/llama-3.3-70b-instruct`는 2026-09-30 기준 전면 무료 라인업 노출에서 제외됨 — 무료 종료 여부는 공식 미확인 (모델 페이지는 로그인 요구로 가려져 있음)

  </details>

- **한도**: 분당 최대 40회 + 일 10,000회 (2026-08-20 이후 표기 시작 — 2026-09-29 페이지 추출 텍스트에서는 직접 확인 불가, 3자 인용 기준). 모델·트래픽·계정에 따라 실제 제공 여부는 유동적.
- **API**: OpenAI 호환. 엔드포인트 `https://integrate.api.nvidia.com/v1`, 인증은 `Bearer nvapi-...` 키.
- **도구 호출**: 모델별 상이 (DeepSeek V3/R1, Kimi K2, GLM, GPT-OSS 계열이 function calling 광고하나 품질 편차 있음)
- **제한**: 카드 불필요. 단, 가입 시 고유 이메일+전화번호 인증 필요. 공식 약관상 프롬프트/응답을 학습에 사용하지 않음(커뮤니티 보고 기준). 프로덕션 용도 아님(프로토타이핑용).
- **출처**: https://github.com/miztertea/nim-proxy/blob/HEAD/knowledge/research/nim-free-tier-40rpm-no-credits.md , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/nvidia-nim.md
- **비고**: OpenAI 호환이라 Hermes 연결 가능. 분당 40회는 에이전트 루프에 넉넉한 편. 도구 호출 품질이 모델별로 들쭉날쭉하므로 메인 모델은 DeepSeek/Kimi 계열로 테스트 권장.
- **2026-09-07 3자 프로브 기준 주석 (공식 문서 아님)**: 한 계정에서 81개 카탈로그 중 실제 응답한 12종은 nemotron-3-super-120b·gpt-oss-20b(선언 기본)·kimi-k3·minimax-m3·nemotron-3-ultra-550b·gemma-4-31b-it 등. 반면 `moonshotai/kimi-k2.6`·Llama 계열은 'Not found for account', `deepseek-ai/deepseek-v4-flash-0731`은 타임아웃으로 도달 불가 — 카탈로그가 계정별로 다르므로 대표 모델은 실제 키로 검증 필요 (출처: https://github.com/murathanx12/aegis-finance/blob/HEAD/docs/BUILD_2026-09-07b_L_FREE_INFERENCE.md).

<a id="orcarouter"></a>

## OrcaRouter <span class="prio p-high">높음</span>

- **대표 무료 모델 (사용성 순, 2026-10-18 기준 — 로테이션됨):**
  - `tencent/hy4-preview-free` — 770B MoE·1M 컨텍스트, 최신 (2026-10-01 공개 API 직접 확인)
  - `deepseek/deepseek-v4-flash-free` — 고속
  - `tencent/hy3-free` — 무료 풀 잔류
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 2026-10-30 06:00 pricing API 직접 확인: $0 `-free` 7종 유지이나 구성 변경 — `orca/orcacyber-glm-5.3-flash-free`가 카탈로그에서 제거되고 `orca/orcacyber-minimax-m3.1-flash-free` 신규 등재 (pricing API에서 model_price 0·is_free_tier true 확인, 단 locked·Security Research 티어 접근 제한 — 대표 편입 없음). 기존 6종 전부 잔류 — 대표 변경 없음 (출처: https://www.orcarouter.ai/api/pricing).

  - 2026-10-28 06:00 pricing API 직접 확인: $0 `-free` 6종→7종 — `orca/orcacyber-glm-5.3-flash-free` 신규 등재 (pricing API에서 model_price 0·is_free_tier true 확인, 단 locked·Security Research 티어 접근 제한이 있어 일반 무료 풀과는 다름 — 대표 편입 없음). 기존 6종 전부 잔류 — 대표 변경 없음 (출처: https://www.orcarouter.ai/api/pricing).

  - 2026-10-25 06:00 pricing API 직접 확인: $0 `-free` 6종 유지 (`tencent/hy4-preview-free`·`tencent/hy3-free`·`deepseek/deepseek-v4.1-flash-free`·`deepseek/deepseek-v4-flash-free`·`z-ai/glm-5.3-flash-free`·`orca/orcaverify-text1.0-free`) — 대표 변경 없음 (출처: https://www.orcarouter.ai/api/pricing).

  - 2026-10-24 06:00 pricing API 직접 확인: $0 `-free` 6종 유지 (`tencent/hy4-preview-free`·`tencent/hy3-free`·`deepseek/deepseek-v4.1-flash-free`·`deepseek/deepseek-v4-flash-free`·`z-ai/glm-5.3-flash-free`·`orca/orcaverify-text1.0-free`) — 대표 변경 없음 (출처: https://www.orcarouter.ai/api/pricing).

  - 무료 7종 (2026-10-18 라이브 브라우저 직접 확인 — `?price=free` 페이지의 FREE 배지 카드): `tencent/hy4-preview-free`, `tencent/hy3-free`, `deepseek/deepseek-v4.1-flash-free`(신규 — V4 Flash의 production successor, 1M 컨텍스트·비전·도구 호출), `deepseek/deepseek-v4-flash-free`, `z-ai/glm-5.3-flash-free`, `orca/orcaverify-text1.0-free`, `orcarouter/free`(자동 라우팅 별칭 — 신규 목록 포함). 공식 pricing API에는 6개 `-free` ID가 $0 (`deepseek/deepseek-v4-pro-free`는 무료 풀에서 제외됨 — 모델 페이지 404).
  - 무료 라인업: [OrcaRouter 무료 모델](https://www.orcarouter.ai/models?price=free) · [공식 pricing API](https://www.orcarouter.ai/api/pricing) — 로테이션됨. `orcarouter/free` 자동 라우팅 별칭도 제공.

  </details>

- **한도**: 무료 모델은 $0/토큰, 요청 속도(request rate) 기준으로 상한 적용 — 구체적 수치 미확인. 무료 "Hacker" 티어는 200+ 모델 카탈로그 접근 포함.
- **API**: OpenAI 호환. 엔드포인트 `https://api.orcarouter.ai/v1` (Anthropic·Gemini 호환 엔드포인트도 제공). 키 발급: GitHub 로그인 후 대시보드에서 발급.
- **도구 호출**: 지원
- **제한**: 카드 등록 불필요(Hacker 티어 무료). 무료 모델 외에는 upstream 제공자 요금 그대로 과금(zero markup). 무료 모델 라인업이 자주 교체됨.
- **출처**: https://www.orcarouter.ai/pricing , https://runtimewire.com/article/orcarouter-glm-5-3-flash-free-tier , https://github.com/vava-nessa/free-coding-models/blob/HEAD/changelog/v0.5.92.md (`qwen3.8-27b-free` 딜리스트 확인)
- **비고**: 형님이 언급한 "Orcarouter"는 실제 서비스명 "OrcaRouter"임. OpenAI 호환이라 Hermes에 바로 연결 가능. 무료 모델은 rate-limited이므로 메인보다는 폴백/서브용 적합. `z-ai/glm-5.3-flash-free`는 2026-09-07 무료 티어에서 Qwen3.8-27B를 대체 (멀티모달·약 1M 컨텍스트, 첫 토큰 느림).

<a id="gemini"></a>

## Google AI Studio — Gemini (이전 조사) <span class="prio p-mid">중간</span>

- **대표 무료 모델 (사용성 순, 신규 사용자 기준):**
  - Gemini 3.8 Flash — 최신 플래그십 무료 (2026-09-18 공식 공지 기준 신규 권장 모델)
  - Gemini 3.5 Flash-Lite — 한도 최다 (신규 권장 모델)
  - Gemma 4 계열 — 일 14,400회 (2026-09-13 1개 무료 키 측정)
  <details>
  <summary>더보기 — 무료 모델 범위 안내</summary>

  - Flash 계열만 무료 (Gemini 3.x Flash, Flash-Lite, Gemma 4). Pro 모델은 2026년 4월부터 무료 티어 제외 (유료 전용).
  - TTS 모델 2종(`gemini-3.8-flash-tts`·`gemini-3.8-flash-lite-tts`)도 Free Tier "Free of charge"로 GA (2026-09-22 changelog, 2026-10-05 18:00 가격표 직접 확인) — 음성 합성 전용이라 Hermes 채팅 연결 대상 아님, 대표 모델 변경 없음.
  - 2026-09-18 공식 공지: `gemini-2.5-flash`, `gemini-2.5-flash-lite`, `gemini-2.5-pro`의 무료 접근은 과거에 실제 사용한 사용자(기존 키)로 제한 — 신규 프로젝트·신규 키는 무료 티어로 사용 불가. 기존에 2.5를 무료로 쓰던 키는 계속 접근 가능.
  - 전체 모델 목록: [Gemini API 가격 페이지](https://ai.google.dev/gemini-api/docs/pricing) — 모델별 Free Tier/Paid Tier 표에서 무료 여부 확인

  </details>

- **한도**: 3.8 Flash — 분당 5회 / 일 20회 (2026-09-13 1개 무료 키 측정). 3.5 Flash-Lite — 분당 15회 / 일 500회. 한도는 모델·프로젝트·리전별로 변동 큼 (정확한 수치는 AI Studio rate-limit 페이지에서 확인). ※ 3.x 계열의 정확한 무료 한도는 공식 가격 페이지 라이브 확인 전까지 미확정.
- **API**: OpenAI 호환 엔드포인트 제공 — `https://generativelanguage.googleapis.com/v1beta/openai/`
- **도구 호출**: 지원 (function calling, JSON 모드, 구조화 출력)
- **제한**: 카드 불필요(Google 계정만). 무료 티어 데이터 학습 활용 가능 (과금 활성화 시 opt-out). 한도가 예고 없이 삭감된 전례 있음 (250→20 RPD 보고).
- **출처**: https://ai.google.dev/gemini-api/docs/changelog (2026-09-18 공지 — 2.5 모델 무료 접근 기존 실사용자 제한) , https://help.apiyi.com/en/google-ai-studio-free-quota-limits-solution-en.html
- **비고**: 한국어 성능 강점. 신규 키 발급 시 2.5 Flash 무료는 쓸 수 없으므로 Hermes에 새로 붙일 땐 3.8-flash 또는 3.5-flash-lite 기준. 단, 한도 변동 리스크가 있어 메인 단독 사용은 주의.

<a id="openrouter"></a>

## OpenRouter (이전 조사) <span class="prio p-mid">중간</span>

- **대표 무료 모델 (사용성 순, 2026-10-28 06:00 기준 — 로테이션됨):**
  - `dots-studio/dots-3-note-preview:free` — 유지 확인 (기존 #2 → #1 승격)
  - `cohere/north-mini-code:free` — 코딩 계열, 무료 잔류 확인 (기존 #3 → #2 승격)
  - `nvidia/nemotron-3-ultra-550b-a55b:free` — 초대형 (기존 목록 잔류, #3 신규 편입)
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 전체 무료 모델: [OpenRouter 무료 모델 목록 — 가격 $0 필터](https://openrouter.ai/models?max_price=0) — 가격 필터(max_price=0)가 적용된 주소로, 열면 $0 모델만 보임 (2026-10-21 라이브 브라우저 직접 확인 — 직접 열어도 필터 유지, 표시 모델 전부 `(free)`·$0 표기, 모델명 끝에 `:free`, 로테이션됨). 무료 전용 컬렉션 [Free AI Models on OpenRouter](https://openrouter.ai/collections/free-models)도 있음 (사용량 기준 상위 무료 모델 랭킹)
  - 2026-10-28 06:00 공개 API 라이브 확인: `:free` 17종→16종. `nvidia/nemotron-3-super-120b-a12b:free`(기존 대표 #1)가 카탈로그에서 제거됨 — `:free` 없는 `nvidia/nemotron-3-super-120b-a12b`만 잔류 (무새 직접 대조로 제거 재확인). 잔류 16종: `recursive/flint-v1.0:free`·`xingchen-agi/xing4.0-29b-a4b:free`·`nvidia/nemotron-3.5-super-vl:free`·`dots-studio/dots-3-note-preview:free`·`liquid/lfm-2.5-2.6b:free`·`nvidia/nemotron-3.5-lightning:free`·`thinkingmachines/inkling-small:free`·`poolside/laguna-s-2.1:free`·`thinkingmachines/inkling:free`·`poolside/laguna-xs-2.1:free`·`cohere/north-mini-code:free`·`nvidia/nemotron-3.5-content-safety:free`·`nvidia/nemotron-3-ultra-550b-a55b:free`·`nvidia/nemotron-3-nano-omni-30b-a3b-reasoning:free`·`google/gemma-4-26b-a4b-it:free`·`google/gemma-4-31b-it:free`. 만료일 표기는 기준선 유지 (laguna 2종 2026-10-31 — 3일 남음, `dots-3-note-preview:free` 2026-12-31) — 항목 단위 만료일 재확인은 브라우저 뷰에서 id·만료일 줄 분리로 불가. 대표 변경: `dots-3-note-preview:free`를 #1으로, `cohere/north-mini-code:free`를 #2로 승격, `nvidia/nemotron-3-ultra-550b-a55b:free`를 #3으로 신규 편입 (출처: https://openrouter.ai/api/v1/models).

  - 2026-10-25 06:00 공개 API 라이브 확인: `:free` 17종 유지 (전원 prompt/output $0 재확인). 만료일 표기 유지 (`poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free` 2026-10-31 — 6일 남음, `dots-studio/dots-3-note-preview:free` 2026-12-31). 대표 3종(`nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`) 전부 잔류 — 대표 변경 없음 (출처: https://openrouter.ai/api/v1/models).

  - 2026-10-24 06:00 공개 API 라이브 확인: `:free` 17종 유지 (전원 prompt/output $0 재확인). 만료일 표기 유지 (`poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free` 2026-10-31 — 7일 남음, `dots-studio/dots-3-note-preview:free` 2026-12-31). 대표 3종(`nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`) 전부 잔류 — 대표 변경 없음 (출처: https://openrouter.ai/api/v1/models).

  - 2026-10-23 06:00 공개 API 라이브 확인: `:free` 18종→17종 (prompt/output $0 직접 확인). `minimax/minimax-m3.1-flash:free`가 카탈로그에서 제거됨 — 공식 X 10/19 "72시간 무료" 프로모션 종료 (만료 예정이던 2026-10-22 21:00 KST경 이후 제거 확인). 기존 17종 전부 잔류. 만료일 표기 유지 (`dots-3-note-preview:free` 2026-12-31·laguna 2종 2026-10-31). 대표 3종(`nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`) 전부 잔류 — 대표 변경 없음. 현재 17종 전체: `recursive/flint-v1.0:free`·`xingchen-agi/xing4.0-29b-a4b:free`·`nvidia/nemotron-3.5-super-vl:free`·`dots-studio/dots-3-note-preview:free`·`liquid/lfm-2.5-2.6b:free`·`nvidia/nemotron-3.5-lightning:free`·`thinkingmachines/inkling-small:free`·`poolside/laguna-s-2.1:free`·`thinkingmachines/inkling:free`·`poolside/laguna-xs-2.1:free`·`cohere/north-mini-code:free`·`nvidia/nemotron-3.5-content-safety:free`·`nvidia/nemotron-3-ultra-550b-a55b:free`·`nvidia/nemotron-3-nano-omni-30b-a3b-reasoning:free`·`google/gemma-4-26b-a4b-it:free`·`google/gemma-4-31b-it:free`·`nvidia/nemotron-3-super-120b-a12b:free` (출처: https://openrouter.ai/api/v1/models).
  - 2026-10-22 06:00 공개 API 라이브 확인: `:free` 17종→18종 (prompt/output $0 직접 확인). `recursive/flint-v1.0:free` 신규 등재 — Recursive가 10/21 공개한 40B/2.5B MoE 오픈 웨이트 코딩 모델 (SWE-bench Pro v2 89.7% 자체 보고·Apache 2.0·262K 컨텍스트·도구 호출·추론 지원 — 출처: https://techcrunch.com/2026/10/21/recursive-launches-flint-a-laptop-coding-model-it-says-was-largely-built-by-ai/). 기존 17종 전부 잔류. 만료일 표기 유지 (`dots-3-note-preview:free` 2026-12-31·`laguna-s-2.1`·`laguna-xs-2.1` :free 2종 2026-10-31). 대표 3종 전부 잔류 — 대표 변경 없음. 현재 18종 전체: 기존 17종 + `recursive/flint-v1.0:free` (출처: https://openrouter.ai/api/v1/models).
  - 2026-10-21 06:00 공개 API 라이브 확인: `:free` 17종 유지 (전원 prompt/output $0 재확인). `thinkingmachines/inkling:free`·`inkling-small:free`의 expiration_date 표기가 사라짐 (10/20 기준 4종 모두 2026-10-31이었으나 laguna-s-2.1·laguna-xs-2.1 2종만 2026-10-31 유지) — 기간 한정 요약표 정정 (출처: https://openrouter.ai/api/v1/models).
  - 2026-10-20 06:00 라이브 확인: `:free` 19종→17종 (공개 API 직접 확인, prompt/output $0). `minimax/minimax-m3.1-flash:free` 신규 등재. `google/lyria-3-clip-preview`·`google/lyria-3-pro-preview`(오디오 계열 — 곡당 과금이라 실질 무료 아님)는 집계 제외, `openrouter/free` 자동 라우팅 별칭도 모델 집계에서 제외. 기존 16종 전부 잔류 — 대표 3종(`nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`) 변경 없음. 현재 17종 전체: `minimax/minimax-m3.1-flash:free`·`xingchen-agi/xing4.0-29b-a4b:free`·`nvidia/nemotron-3.5-super-vl:free`·`dots-studio/dots-3-note-preview:free`·`liquid/lfm-2.5-2.6b:free`·`nvidia/nemotron-3.5-lightning:free`·`thinkingmachines/inkling-small:free`·`poolside/laguna-s-2.1:free`·`thinkingmachines/inkling:free`·`poolside/laguna-xs-2.1:free`·`cohere/north-mini-code:free`·`nvidia/nemotron-3.5-content-safety:free`·`nvidia/nemotron-3-ultra-550b-a55b:free`·`nvidia/nemotron-3-nano-omni-30b-a3b-reasoning:free`·`google/gemma-4-26b-a4b-it:free`·`google/gemma-4-31b-it:free`·`nvidia/nemotron-3-super-120b-a12b:free`. ※ `laguna-s-2.1`·`laguna-xs-2.1` :free 2종은 expiration_date 2026-10-31 (10/21 확인 — inkling 2종의 만료일 표기는 사라짐), `dots-3-note-preview:free`는 2026-12-31 만료 (출처: https://openrouter.ai/api/v1/models).
  - 2026-10-19 06:00 라이브 확인: `:free` 16종→19종 — 기존 16종 전부 잔류. 신규 3종 (prompt/output $0 직접 확인): `google/lyria-3-clip-preview`·`google/lyria-3-pro-preview`(오디오 계열 — 채팅 용도 아님, 대표 대상 제외)·`openrouter/free`(자동 라우팅 별칭). 대표 3종(`nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`) 전부 잔류 — 대표 변경 없음. 현재 19종 전체: 기존 16종 + `google/lyria-3-clip-preview`·`google/lyria-3-pro-preview`·`openrouter/free` (출처: https://openrouter.ai/api/v1/models).
  - 2026-10-17 06:00 라이브 확인: `:free` 15종→16종 — `xingchen-agi/xing4.0-29b-a4b:free` 신규 등재 (China Telecom TeleAI의 29B MoE 오픈 웨이트 모델, 262K 컨텍스트, prompt/output $0 직접 확인). 대표 3종(`nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`) 전부 잔류 — 대표 변경 없음. 현재 16종 전체: `nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`·`nvidia/nemotron-3-ultra-550b-a55b:free`·`nvidia/nemotron-3.5-lightning:free`·`nvidia/nemotron-3-nano-omni-30b-a3b-reasoning:free`·`nvidia/nemotron-3.5-content-safety:free`·`nvidia/nemotron-3.5-super-vl:free`·`google/gemma-4-26b-a4b-it:free`·`google/gemma-4-31b-it:free`·`thinkingmachines/inkling:free`·`thinkingmachines/inkling-small:free`·`poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`liquid/lfm-2.5-2.6b:free`·`xingchen-agi/xing4.0-29b-a4b:free` (출처: https://openrouter.ai/api/v1/models).
  - 2026-10-16 06:00 라이브 확인: `:free` 14종→15종 (공개 API 직접 확인, 프롬프트/출력 전부 $0). 대표 3종은 전부 잔류. 10/14 06:00 등재 시 명단이 기준선에 개별 기록되지 않아 신규 1종 특정 불가 — 현재 15종 전체: `nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`·`nvidia/nemotron-3-ultra-550b-a55b:free`·`nvidia/nemotron-3.5-lightning:free`·`nvidia/nemotron-3-nano-omni-30b-a3b-reasoning:free`·`nvidia/nemotron-3.5-content-safety:free`·`nvidia/nemotron-3.5-super-vl:free`·`google/gemma-4-26b-a4b-it:free`·`google/gemma-4-31b-it:free`·`thinkingmachines/inkling:free`·`thinkingmachines/inkling-small:free`·`poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`liquid/lfm-2.5-2.6b:free` (출처: https://openrouter.ai/api/v1/models).

  </details>

- **한도**: 분당 20회 / 일 50회 (누적 $10 이상 구매 시 일 1,000회)
- **API**: OpenAI 호환. 엔드포인트 `https://openrouter.ai/api/v1`
- **도구 호출**: 무료 라우트별 상이 (각 라우트의 supported_parameters 확인 필요)
- **제한**: 카드 불필요. 무료 라우트별 데이터 정책 상이 (일부는 학습 활용 경고 있음). upstream 429 빈발 보고.
- **출처**: https://buldrr.com/openrouter-free-api-keys-free-models-simple-guide/
- **비고**: Hermes 공식 문서의 기본값이라 설정 예제가 가장 풍부. 일 50회는 에이전트 실사용에 빠듯. $10 1회 충전 시 한도 20배 상승이 가성비 최고. 구 무료 모델(DeepSeek R1·Llama 3.3 70B·Qwen3 Coder 등)의 `:free` 버전은 2026-09-28 확인 기준 유료 전용으로 전환됨. 2026-09-29 18:00 라이브 스냅샷 기준 `:free` 16종 — `qwen3.8-27b:free`·`liquid/lfm-2.5-2.6b:free` 신규 등록. `inclusionai/ling-3.0-flash-fin:free`는 유료 전환 (input $0.06/1M, output $0.18/1M). 2026-10-03 06:00 라이브 확인: `:free` 17종 — 10/01에 제거됐던 `nemotron-3-super-120b-a12b:free`·`cohere/north-mini-code:free`·`liquid/lfm-2.5-2.6b:free`가 복귀하고, `apodex/apodex-1.1-mini:free`·`nvidia/nemotron-3.5-lightning:free`·`thinkingmachines/inkling-small:free`·`poolside/laguna-s-2.1:free`·`thinkingmachines/inkling:free`·`poolside/laguna-xs-2.1:free`·`nvidia/nemotron-3.5-content-safety:free`·`nvidia/nemotron-3-ultra-550b-a55b:free`·`nvidia/nemotron-3-nano-omni-30b-a3b-reasoning:free`·`google/gemma-4-26b-a4b-it:free`·`google/gemma-4-31b-it:free`가 신규 등재. `:free` 라인업은 일 단위 로테이션이므로 대표 교체는 유지 확인 기준으로만. `stealth/space-bunny-alpha`는 만료일 2026-10-05 경과 후 카탈로그에서 완전 제거됨 (2026-10-06 06:00 확인, OpenRouter·Nous Portal 양쪽) — 기간 한정 요약표에서 정리. `qwen/qwen3.8-27b:free`는 유료 전용으로 전환 확인 (유료 `qwen/qwen3.8-27b`만 잔류, 입력 $0.425/1M) → 대표 모델에서 `nemotron-3-super-120b-a12b:free`로 교체. 2026-10-06 06:00 라이브 확인: `:free` 16종. Thinking Machines Inkling은 에이전트 하네스에서만 응답하고 일반 API 호출에는 403을 반환하므로 Hermes 직접 연결 폴백에서 제외 권장 (2026-09-28 3자 검증). 2026-10-09 06:00 라이브 확인: `:free` 15종 — `inclusionai/ling-3.0-flash-sante:free`(당시 대표 #1)가 무료에서 제거됨. 잔류 15종 전부 pricing prompt/output "0" 확인. 2026-10-13 18:00 라이브 확인: `:free` 19종 (공개 API 직접 확인, prompt/output $0 전원 개별 재조회 확정). 10/09 전체 명단 부재로 개별 추가/제거 대조는 불가 — 대표 3종(`nemotron-3-super-120b-a12b:free`·`dots-3-note-preview:free`·`cohere/north-mini-code:free`)은 잔류 확인. `inclusionai/ling-3.1-flash`도 $0 유지 (체험 종료일 10/13 당일). `google/lyria-3-clip-preview`·`google/lyria-3-pro-preview`(오디오 계열 추정)·`openrouter/free`(자동 라우팅 별칭) 등재. 2026-10-14 06:00 라이브 확인: `:free` 19종→14종 — `apodex/apodex-1.1-mini:free`가 카탈로그에서 완전 삭제됨. 나머지 4종도 카탈로그에서 삭제됐으나 10/13 저녁 등재 시 명단이 기준선에 개별 기록되지 않아 대조 불가 (잔류 14종은 기존 추적 모델 전부 유지 — 위에 나열된 14종). 대표 3종은 전부 잔류 확인. `inclusionai/ling-3.1-flash`는 2주 체험 종료 후 유료 전환 (입력 $0.075/1M, 출력 $0.225/1M). `openrouter/free` 자동 라우팅 별칭은 $0 유지.

<a id="aihubmix"></a>

## AIHubMix <span class="prio p-mid">중간</span>

- **대표 무료 모델 (2026-10-05 공식 무료 모델 문서 확인):**
  - `coding-glm-5.1-free` — 오픈소스 최초 SWE-bench Pro 1위 (58.4%), 코딩 특화
  - `gpt-5.5-free` — OpenAI 최신 플래그십 무료 제공
  - `xiaomi-mimo-v2.5-free` — 1M 컨텍스트·에이전트/도구 호출 특화
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 전체 목록: [AIHubMix 무료 모델 문서](https://docs.aihubmix.com/en/blogs/free-ai-models) — 공식 표기 '27+ models'이나 2026-10-17 실제 나열된 고유 모델은 25종 확인 (일반 목적 8·코딩 12·이미지 2·Agent/추론 2·최신 업데이트 1). 무료 ID는 전부 `-free` 접미사
  - 한도 (3자 검증, 2026-09-28): 모델별 일일 캡 — 최신 코딩 모델 5 RPM·일 100회·일 100만 토큰, 그 외 일 500회 수준. 일 리셋, 체험 만료 없음
  - 2026-10-24 아침 공식 문서 직접 확인: '27+' 표기 유지, 대표 3종(`coding-glm-5.1-free`·`gpt-5.5-free`·`xiaomi-mimo-v2.5-free`) 모두 무료 등재 유지 — 대표 변경 없음. 3자 추적(2026-10-23 커밋)의 'AIHubMix withdrawals and new Gemma routes' 주장은 공식 문서에서 확인되지 않음 (출처: https://docs.aihubmix.com/en/blogs/free-ai-models).

  </details>

- **한도**: 모델별 일일 캡 (상단 더보기 참조), 일 리셋. 체험 만료 없음 (공식 문서 "No trial expiry")
- **API**: OpenAI 호환. 엔드포인트 `https://aihubmix.com/v1`. Anthropic 형식(`/v1/messages`)도 지원 — Claude Code 직접 연결 가능
- **도구 호출**: 지원 (코딩·에이전트 모델 중심, 모델별 상이)
- **제한**: **카드 불필요**. API 키는 사이트에서 발급
- **출처**: https://docs.aihubmix.com/en/blogs/free-ai-models
- **비고**: 800+ 모델 게이트웨이 중 25종을 플랫폼이 비용 부담하며 $0 제공 (공식 표기 '27+ models' — 2026-10-17 실제 나열 기준 25종). 유료 플래그십(GPT-5.5·Gemini 3 등)을 무료로 쓸 수 있는 몇 안 되는 경로 (2026-10-05 형님 승인 등록).

<a id="z-ai"></a>

## Z.ai <span class="prio p-mid">중간</span>

- **대표 무료 모델 (사용성 순, 2026-10-07 공식 가격표 확인 — 3종 모두 영구 Free):**
  - `glm-4.7-flash` — 131K 컨텍스트·도구 호출·추론 지원, 코딩/에이전트에 가장 유망 (컨텍스트·도구 호출은 3자 확인)
  - `glm-4.5-flash` — 경량 텍스트 모델
  - `glm-4.6v-flash` — 비전(텍스트·이미지) 모델
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 2026-10-23 06:00 확인: Flash 3종(`GLM-4.7-Flash`·`GLM-4.5-Flash`·`GLM-4.6V-Flash`) 가격표에 잔류 — Input·Cached Input·Cached Input Storage·Output 전부 Free (가격표 HTML 직접 추출 확인). 접힘 섹션에 있어 라이브 브라우저 텍스트 추출에서는 누락으로 오인될 수 있음 — 무료 상태 변화 없음 (출처: https://docs.z.ai/guides/overview/pricing).
  - 2026-10-22 18:00 확인: 유료 모델(GLM-5.3 등)의 Cached Input Storage 열 "Limited-time Free" 표기 유지 (페이지 Updated 2026-10-21) — 신설 시점은 페이지에서 확인 불가. 무료 3종에는 "Limited-time Free" 표기 없음 — 무료 상태 변화 없음 (공식 가격표 직접 확인 — https://docs.z.ai/guides/overview/pricing).
  - 2026-10-15 확인: 공식 가격표에서 무료 3종이 본문 요금 테이블→"Other Pricing"(레거시) 접힘 섹션으로 이동 (라이브 브라우저 직접 확인). 3종 모두 입력·캐시·출력 전부 Free 유지, "Limited-time Free" 라벨 없음 — 무료 상태 변화 없음. 향후 변경 전조일 수 있어 관찰 유지.
  - 2026-10-07 공식 가격표 확인 기준 Free 3종: `glm-4.7-flash`·`glm-4.5-flash`·`glm-4.6v-flash` (입력·캐시 입력·출력 전부 Free, "Limited-time Free" 표기 없음 — 상시 무료). 유료 플래그십(GLM-5.3 등)은 별도 유료
  - 전체 목록: [Z.ai 공식 가격표](https://docs.z.ai/guides/overview/pricing)
  - 한도: 공식 RPM/RPD 수치 미공개 — concurrency(동시성) 기반 제한 (3자 검증, 2026-09-28). 사용량이 늘면 키당 제한 확인 필요

  </details>

- **한도**: 공식 수치 미공개 — 동시성 기반 제한 (상단 더보기 참조). 무료 토큰 한도는 공식 문서에 별도 명시 없음
- **API**: OpenAI 호환. 엔드포인트 `https://api.z.ai/api/paas/v4`. Anthropic 형식(`https://api.z.ai/api/anthropic`)도 지원 — Claude Code 직접 연결 가능
- **도구 호출**: `glm-4.7-flash` 지원 (3자 확인)
- **제한**: **카드 불필요**. 휴대폰 인증도 불필요 (3자 검증, 2026-08-13·2026-09-28). 이메일 가입 후 사이트에서 API 키 발급
- **출처**: https://docs.z.ai/guides/overview/pricing
- **비고**: Zhipu AI(지푸 AI)의 글로벌 브랜드. 2026-03부터 무료 서비스 중 (2026-10-07 형님 승인 등록). Terms of Use는 "경쟁 알고리즘·모델의 개발·학습·개선" 목적 사용을 금지하나, 일반 상용 이용은 허용 (3자 확인).

<a id="llm7"></a>

## LLM7.io <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순, turbo 티어 — 2026-10-22 06:00 라이브 API 직접 확인, turbo 5종):**
  - `gpt-oss:20b` — 128K 컨텍스트·도구 호출 지원 (잔류 유일 기존 대표, #1 승격)
  - `codestral-latest` — Mistral Codestral, 코딩 특화
  - `minimax-m2.7` — 180K 컨텍스트·도구 호출·추론 지원 (10/10 카탈로그 제거→10/14 turbo 복귀 이력)
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 2026-10-25 06:00 라이브 API 직접 확인 기준 turbo(무료) 티어 5종 유지: `codestral-latest`·`gpt-oss:20b`·`minimax-m2.7`·`mistral-Nemo-Instruct-2407`·`nemotron-3-nano:30b` — 대표 변경 없음 (출처: https://api.llm7.io/v1/models).

  - 2026-10-24 06:00 라이브 API 직접 확인 기준 turbo(무료) 티어 5종 유지: `codestral-latest`·`gpt-oss:20b`·`minimax-m2.7`·`mistral-Nemo-Instruct-2407`·`nemotron-3-nano:30b` — 대표 변경 없음 (출처: https://api.llm7.io/v1/models).

  - 2026-10-22 06:00 라이브 API 직접 확인 기준 turbo(무료) 티어 7종→5종: `DeepSeek-V4-Flash-0731`(기존 대표 #1)·`GLM-5.3-Flash`(기존 대표 #2)가 카탈로그에서 완전 삭제됨 (동일 ID의 deepseek/glm-5.3 변형은 전부 `pro` 티어 — 유료 전환). 잔류 5종: `codestral-latest`·`gpt-oss:20b`·`minimax-m2.7`·`mistral-Nemo-Instruct-2407`·`nemotron-3-nano:30b`. 대표 변경: 잔류 유일 기존 대표 `gpt-oss:20b`를 #1으로 승격, `codestral-latest`(코딩 특화)·`minimax-m2.7`(180K·도구 호출·추론)을 #2·#3으로 편입 (대표 선정 기준: 에이전트 적합성 최우선 — 2026-10-14 형님 확립). 라인업이 뒤집히는 중이라 사용 전 재확인 권장 (출처: https://api.llm7.io/v1/models).

  - 2026-10-14 06:00 라이브 API 직접 확인 기준 turbo(무료) 티어 7종: `DeepSeek-V4-Flash-0731`, `GLM-5.3-Flash`, `codestral-latest`, `gpt-oss:20b`, `mistral-Nemo-Instruct-2407`, `nemotron-3-nano:30b`, `minimax-m2.7` (7종 유지). `gemma4:31b`이 turbo→pro 티어로 유료 전환, `minimax-m2.7`은 10/10 카탈로그 제거 후 turbo로 복귀. 대표 3종(`DeepSeek-V4-Flash-0731`·`GLM-5.3-Flash`·`gpt-oss:20b`)은 전부 turbo 유지.
  - 2026-10-10 06:00 라이브 API 직접 확인 기준 turbo(무료) 티어 7종: `DeepSeek-V4-Flash-0731`, `GLM-5.3-Flash`, `codestral-latest`, `gpt-oss:20b`, `mistral-Nemo-Instruct-2407`, `nemotron-3-nano:30b`, `gemma4:31b`. `minimax-m2.7`은 카탈로그에서 제거, `glm-5.2`·`minimax-m3`는 turbo→pro 티어 강등 (유료 전환). `deepseek-v4-pro`는 turbo→pro 티어로 강등 (유료 전환, 10/09 반영). `deepseek-v4-flash:0731`(소문자·콜론 표기)은 별개 ID로 pro 티어 유지. 확인 직전 분 단위로 9→10→11종으로 변동 후 11종으로 안정 — 라인업이 로테이션 중이라 사용 전 재확인이 안전.
  - 전체 목록: [LLM7.io 모델 카탈로그](https://api.llm7.io/v1/models) — `tier: "turbo"` 행이 무료

  </details>

- **한도**: 무료 토큰(dash.llm7.io 발급) — 초당 1회 / 분당 60회 / 시간당 250회 / 24시간 100,000 토큰 (2026-10-01 공식 한도 문서 기준 — 24시간 토큰 허용량이 기존 100만에서 1/10로 축소됨). 익명(키 없음) 티어 표기는 공식 문서에서 사라짐 (삭제인지 표기 누락인지 미확인).
- **API**: OpenAI 호환. 엔드포인트 `https://api.llm7.io/v1`. 익명 사용 시 api_key에 "unused" 입력.
- **도구 호출**: 미확인
- **제한**: 카드·가입 불필요(익명 가능). 운영자가 upstream을 공개하지 않음. 무료 모델 구성이 변경될 수 있음.
- **출처**: https://docs.llm7.io/limits , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/llm7.md , https://github.com/velo4705/awesome-free-byok-models
- **비고**: Hermes 연결 가능. 가입 없이 바로 쓸 수 있어 테스트용으로 가장 간편. 단, 24시간 10만 토큰은 에이전트 루프 몇 바퀴면 소진이므로 에이전트 실사용 폴백으로는 사실상 부적합 — '가입 없이 짧게 시험' 용도로만 유효. 2026-10-10 아침 기준 turbo 7종으로 추가 축소 (`minimax-m2.7` 제거, `glm-5.2`·`minimax-m3` 유료 전환) — 단, 확인 직전 분 단위 로테이션 중이라 사용 전 재확인 권장.

<a id="opencode-zen"></a>

## OpenCode Zen <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순, OpenCode 내부 전용 — 2026-10-30 18:00 `/v1/models` API 확인, 무료 7종):**
  - `deepseek-v4.1-flash-free` — 고속 플래그십
  - `glm-5.3-flash-free` — 멀티모달 플래시
  - `flint-40b-free` — 오픈 웨이트 코딩 모델 (40B MoE, 10/21 공개)
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 2026-10-30 18:00 기준 무료 8종→7종 (`/v1/models` API 직접 확인, 3회 확인 동일): `jev-1.13-free`가 카탈로그에서 제거됨 (유료 변형도 카탈로그에 없음 — 완전 제거). `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종 중 `jev-1.13-free` 제외, `flint-40b-free` 편입. 현재 7종: `beam-free`·`deepseek-v4.1-flash-free`·`flint-40b-free`·`glm-5.3-flash-free`·`mimo-v2.6-flash-free`·`nemotron-3.5-lightning-free`·`nemotron-3.5-super-vl-free` (출처: https://opencode.ai/zen/v1/models).

  - 2026-10-25 06:00 기준 무료 8종 유지 (`/v1/models` API 직접 확인): 기존 8종 전부 잔류. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`)은 전부 잔류 — 대표 변경 없음 (출처: https://opencode.ai/zen/v1/models).

  - 2026-10-24 06:00 기준 무료 8종 유지 (`/v1/models` API 직접 확인): 기존 8종 전부 잔류. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`)은 전부 잔류 — 대표 변경 없음 (출처: https://opencode.ai/zen/v1/models).

  - 2026-10-23 06:00 기준 무료 9종→8종 (`/v1/models` API 직접 확인): `minimax-m3.1-flash-free`가 카탈로그에서 제거됨 — MiniMax M3.1 Flash 기간 한정 무료 종료 (OpenRouter `:free`도 같은 날 제거 확인). 기존 8종 전부 잔류. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`)은 전부 잔류 — 대표 변경 없음. 현재 8종: `beam-free`·`deepseek-v4.1-flash-free`·`flint-40b-free`·`glm-5.3-flash-free`·`jev-1.13-free`·`mimo-v2.6-flash-free`·`nemotron-3.5-lightning-free`·`nemotron-3.5-super-vl-free` (출처: https://opencode.ai/zen/v1/models).

  - 2026-10-22 18:00 기준 무료 10종→9종 (`/v1/models` API 직접 확인): `longcat-2.5-preview-free`가 카탈로그에서 제거됨. 기존 9종 전부 잔류. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`)은 전부 잔류 — 대표 변경 없음. 현재 9종: `beam-free`·`deepseek-v4.1-flash-free`·`flint-40b-free`·`glm-5.3-flash-free`·`jev-1.13-free`·`mimo-v2.6-flash-free`·`minimax-m3.1-flash-free`·`nemotron-3.5-lightning-free`·`nemotron-3.5-super-vl-free` (출처: https://opencode.ai/zen/v1/models).

  - 2026-10-22 06:00 기준 무료 9종→10종 (`/v1/models` API 직접 확인): `flint-40b-free` 신규 등재 (Recursive Flint의 Zen ID — 10/21 공개, 40B/2.5B MoE 오픈 웨이트 코딩 모델 — 출처: https://techcrunch.com/2026/10/21/recursive-launches-flint-a-laptop-coding-model-it-says-was-largely-built-by-ai/). 기존 9종 전부 잔류. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`)은 전부 잔류 — 대표 변경 없음. 현재 10종: `beam-free`·`deepseek-v4.1-flash-free`·`flint-40b-free`·`glm-5.3-flash-free`·`jev-1.13-free`·`longcat-2.5-preview-free`·`mimo-v2.6-flash-free`·`minimax-m3.1-flash-free`·`nemotron-3.5-lightning-free`·`nemotron-3.5-super-vl-free` (출처: https://opencode.ai/zen/v1/models).
  - 무료 모델 목록: [OpenCode Zen 공식 문서 — Free models 섹션](https://opencode.ai/v2/docs/console/models/#free-models) — 사람이 보는 공식 문서 페이지에 무료 모델이 명시돼 있음 (2026-10-21 라이브 확인 — 구 Docs 주소 `opencode.ai/docs/zen/`는 이 페이지로 리다이렉트됨. 기존에 걸려 있던 `https://opencode.ai/zen` 페이지는 모델 목록 자체가 없는 안내 페이지라 이 문서로 교체함). 단, 문서 목록(스텔스·기간 한정 포함 14종 표기)과 API 카탈로그가 서로 달라, 무료 집계는 [`/v1/models` API](https://opencode.ai/zen/v1/models)의 `-free` ID 기준 (로테이션됨). 2026-10-21 08:10 API 재확인에서도 9종 동일. 2026-10-20 18:00 기준 무료 9종 (10종→9종, `/v1/models` API 직접 확인): `space-bunny-free`가 카탈로그에서 제거됨. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`)은 전부 잔류 — 대표 변경 없음. 현재 9종: `beam-free`·`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`·`longcat-2.5-preview-free`·`mimo-v2.6-flash-free`·`minimax-m3.1-flash-free`·`nemotron-3.5-lightning-free`·`nemotron-3.5-super-vl-free` (출처: https://opencode.ai/zen/v1/models).
  - 2026-10-17 18:00 기준 무료 9종 (12종→9종, `/v1/models` API 재확인): `ll-alpha-free`(10/16 저녁 신규 스텔스 — 하루 만에 제거)·`muse-spark-1.2-contributor-free`·`muse-spark-1.3-contributor-free`가 카탈로그에서 제거됨. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종: `deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free` (출처: https://opencode.ai/zen/v1/models). 2026-10-17 06:00 기준 무료 12종: `beam-free`·`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`·`ll-alpha-free`·`longcat-2.5-preview-free`·`mimo-v2.6-flash-free`·`muse-spark-1.2-contributor-free`·`muse-spark-1.3-contributor-free`·`nemotron-3.5-lightning-free`·`nemotron-3.5-super-vl-free`·`space-bunny-free` (당시 `cat-jam-free` 제거·`beam-free` 신규 등재).
  - 2026-10-16 18:00 기준 무료 12종 (11종→12종): `step-5-preview-free`가 카탈로그에서 제거됨 (대표 #1이었음 — 대표에서 제외, `deepseek-v4.1-flash-free`로 교체), `ll-alpha-free`(신규 스텔스 모델)·`glm-5.3-flash-free` 신규 등재. `big-pickle`(스텔스, `-free` 접미사 없음)이 카탈로그에 재등장 (10/15 아침 제거 후 복귀 — `-free` ID 기준이 아니라 무료 집계에서 제외). 잔류 12종: `cat-jam-free`, `deepseek-v4.1-flash-free`, `glm-5.3-flash-free`, `jev-1.13-free`, `ll-alpha-free`, `longcat-2.5-preview-free`, `mimo-v2.6-flash-free`, `muse-spark-1.2-contributor-free`, `muse-spark-1.3-contributor-free`, `nemotron-3.5-lightning-free`, `nemotron-3.5-super-vl-free`, `space-bunny-free`.
  - 2026-10-16 06:00 기준 무료 11종 (10종→11종): `nemotron-3.5-super-vl-free` 신규 등재 (기존 10종 잔류 — 대표 변경 없음). 2026-10-15 18:00 기준 무료 10종 (9종→10종): `deepseek-v4.1-flash-free` 신규 등재 (재확인에서도 10종 유지, 기존 9종 잔류 — 대표 변경 없음). 2026-10-15 06:00 기준 무료 9종 (11종→9종): `ling-3.1-flash-free`가 체험 종료일(10/13) 이틀 만에 목록에서 제거됨 (Nous Portal·OpenRouter는 10/14 아침에 이미 유료 전환 — Zen만 이틀 유예), `big-pickle`(스텔스 모델)도 목록에서 제거됨. 잔류 9종: `cat-jam-free`, `jev-1.13-free`, `longcat-2.5-preview-free`, `mimo-v2.6-flash-free`, `muse-spark-1.2-contributor-free`, `muse-spark-1.3-contributor-free`, `nemotron-3.5-lightning-free`, `space-bunny-free`, `step-5-preview-free`. 대표에서 `big-pickle` 제외, `jev-1.13-free` 편입.
  - 스텔스 모델 관련 정보:
    - LL Alpha: [OpenCode 공식 모델 페이지](https://opencode.ai/v2/docs/console/models/) — "LL Alpha Free is a stealth model that's free on OpenCode for a limited time" (정체 미공개, 기간 한정 무료 — 2026-10-16 저녁 `ll-alpha-free`로 신규 등재됐으나 10/17 저녁 카탈로그에서 제거 확인, 하루 만에 종료)
    - Space Bunny: [지문 분석](https://github.com/majiayu000/stealthprint/blob/main/docs/case-space-bunny.md) — MiniMax 계열 토크나이저, 1M 컨텍스트 확인. Space Bunny Alpha는 2026-10-05 만료 후 OpenRouter·Nous Portal 양쪽 카탈로그에서 제거 확인 (OpenCode Zen의 `space-bunny-free`와는 별개 ID)
    - Big Pickle: 2026-10-15 아침 카탈로그에서 제거됐다가 10/16 저녁 재등장 확인 (`big-pickle`, `-free` 접미사 없음 — 무료 집계 제외). 정체는 커뮤니티 추측 수준이라 '추정'으로만 표기. ※ 10/15 아침 제거 시 스텔스 관련 정보 링크를 정리했음 — 재등장이 유지되면 링크 복원 검토
    - Fledge Alpha: [정체 분석 영상](https://www.youtube.com/watch?v=4Zb9my4MI3U) — 2026-10-01 등장, Thinking Machines Inkling 프로젝트와 연결 (PR 추적 기준 '추정'). [OpenCode 데이터 페이지](https://opencode.ai/data/unknown/fledge-alpha). ※ 2026-10-09 확인에서 Zen Free 목록에서 제거됨
    - Beam: 정체 미공개 — 2026-10-17 아침 `beam-free`로 신규 등재, 관련 정보 확인 시 링크 추가

  </details>

- **한도**: 커뮤니티 보고 기준 일 약 100회 요청 (공식 문서에 무료 티어 수치 미기재 → 미확인)
- **API**: OpenAI 호환. 엔드포인트 `https://opencode.ai/zen/v1` — 단, **무료 티어는 OpenCode 외부 하네스에서 사용 불가**
- **도구 호출**: 지원 (3자 검증 기준)
- **제한**: **2026-09-17부터 무료 티어가 OpenCode가 아닌 모든 클라이언트를 403으로 차단** (`FreeTierError: OpenCode's free tier can only be used from within OpenCode`) — 2026-09-18 OpenCode maintainer가 "무료 티어는 다른 하네스에서 사용 불가" 확인. Hermes 등 외부 하네스에서 무료 티어 사용 불가 확정. 무료 모델 데이터가 학습에 활용될 수 있음.
- **출처**: https://opencode.ai/zen , https://opencode.ai/zen/v1/models , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/opencode.md , https://github.com/decolua/9router/issues/4103
- **비고**: Hermes에서 Zen 무료 티어는 쓸 수 없으므로 폴백 후보에서 제외. 유료 Zen 잔액이 있으면 연동 가능.

<a id="token-harbor"></a>

## Token Harbor <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-16 06:00 라이브 브라우저 직접 확인 — Free 카테고리 2종):**
  - `deepseek-v4.1-flash:free` — FREE (뱃지 없음)
  - `mimo-v2.6-flash:free` — FREE (뱃지 없음)
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 2026-10-30 06:00 텍스트 추출 확인: Free 카테고리 2종 유지 (`deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`) — 'Free' 표기, 페이지 하단 '2 models' 표기, 'FREE LIMITED TIME' 배지·만료일 표시 없음.

  - 2026-10-29 18:00 라이브 브라우저 직접 확인: Free 카테고리 2종 유지 (`deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`) — 'FREE LIMITED TIME' 배지·만료일 표시 없음, 페이지 하단 '2 models' 표기.

  - 2026-10-25 06:00 라이브 브라우저 직접 확인: Free 카테고리 2종 유지 (`deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`) — 'FREE LIMITED TIME' 배지·만료일 표시 없음.

  - 2026-10-24 06:00 라이브 브라우저 직접 확인: Free 카테고리 2종 유지 (`deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`) — 'FREE LIMITED TIME' 배지·만료일 표시 없음.

  - 2026-10-21 18:00 라이브 브라우저 직접 확인: Free 카테고리 2종 유지 (`deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`) — 'FREE LIMITED TIME' 배지·만료일 표시 없음.
  - 무료 모델 목록: [Token Harbor 무료 모델](https://tokenharbor.ai/models?category=free) — 로테이션됨 ("Promotional models added over time"). 2026-10-16 06:00 라이브 브라우저 직접 확인 기준 Free 카테고리 3종→2종: `claude-haiku-5.5:free`가 무료 종료일(2026-10-15 22:00 KST, 툴팁 "Free until 10/15/2026, 1:00:00 PM") 경과로 Free 카테고리에서 제외 — Value(유료) 탭의 `claude-haiku-5.5`(입력 $0.10/1M·출력 $0.50/1M)로 전환. 잔류: `deepseek-v4.1-flash:free`(FREE)·`mimo-v2.6-flash:free`(FREE). 무료 라인업이 분 단위로 뒤집히는 중 — 사용 전 재확인이 안전.
  - 2026-10-30 18:00 텍스트 추출 확인: Free 카테고리 2종 유지 (`deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`) — 'Free' 표기, 페이지 하단 '2 models' 표기, 'FREE LIMITED TIME' 배지·만료일 표시 없음.
  - `qwen3.8-flash:free`는 2026-10-04 13:00 UTC 무료 프로모 종료로 Free 목록에서 제거됨 — 현재 유료 "value" 티어 ($0.15/1M 입력, isFree:false)
  - `deepseek-v4-flash:free` (구형 V4 Flash)는 2026-09-30 pricing Free 목록에서 제외됨 — 공식 블로그(9/23 업데이트)에서는 여전히 무료로 기술 중이라 완전 단정은 불가, 최근 1주 내 무료 라인업에서 빠진 것으로 보임
  - `TH-Rudder` — 2026-09-30 Free 플랜 Includes 신규 표시 (Token Harbor 자체 채팅 제품, API 제공 여부 미확인)

  </details>

- **한도**: $0/월 플랜 — 4주 롤링 주기로 갱신되는 무료 할당량 (정확한 양 미공개, 이월 여부는 보고가 상충). 분당 60회·시간당 1,800회 제한 (2026-09-28 3자 재검증). 카드 불필요.
- **API**: OpenAI 호환. 엔드포인트 `https://tokenharbor.ai/v1` (Anthropic 호환 `/v1/messages`도 제공)
- **도구 호출**: 미확인
- **제한**: 소규모 게이트웨이 — 중국 본토/홍콩/마카오에서 region_blocked. 무료 요청이 플랫폼에 저장될 수 있음. 할당량·라인업이 예고 없이 바뀔 수 있어 프로토타입/폴백용 권장.
- **출처**: https://tokenharbor.ai/pricing , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/token-harbor.md
- **비고**: DeepSeek V4.1 Flash(공식 API는 상시 무료 티어 없음)를 무료로 쓸 수 있는 몇 안 되는 경로. 성능 비교 링크의 대표 모델이라 테스트 가치가 있음. `qwen3.8-flash:free` 무료 프로모는 2026-10-04 13:00 UTC에 종료되어 유료(value 티어)로 전환됨 — 10/05 아침 워치에서 만료 확인. `claude-haiku-5.5:free` 기간 한정 프로모는 2026-10-15 22:00 KST에 종료되어 Free 목록에서 제외됨 (10/16 아침 워치에서 만료 확인, 유료 value 티어로 전환). 무료 목록 등재가 불안정하므로 사용 전 재확인 필수.

<a id="nous-portal"></a>

## Nous Portal (Hermes Agent) <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순, 2026-10-30 18:00 기준 — 무료 6종):**
  - `stepfun/step-3.7-flash:free` — StepFun 플래시, 에이전트용 (10/20 `step-5-preview:free` 제거로 편입)
  - `poolside/laguna-s-2.1:free`
  - `reflection/beam-1.0-501b-a23b:free` — 신규 등재 (501B MoE)
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 무료 모델 확인: [Nous Portal 모델 목록](https://portal.nousresearch.com/models) — 페이지를 열면 'Free Models' 섹션과 FREE 필터 버튼으로 무료 모델을 바로 볼 수 있음 (단, 필터 상태가 URL에 남지 않아 주소만으로는 필터 화면을 공유할 수 없음 — 2026-10-21 라이브 브라우저 확인). 기계적 확인 원본은 [공식 API 모델 목록](https://inference-api.nousresearch.com/v1/models)의 `:free`·가격 $0 항목.
  - 2026-10-30 18:00 기준 무료 7종→6종 (공식 API 가격 $0 기준, 직접 확인, 재확인 동일): 아침에 재등재됐던 `inclusionai/ling-3.1-flash:free`가 카탈로그에서 다시 제거됨 (유료 변형 `inclusionai/ling-3.1-flash`는 입력 $0.075/1M·출력 $0.225/1M 유지, 별개 ID — 당일 재등재→재제거). `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free` expiration_date 2026-10-31 유지 (내일 만료). 대표 3종(`stepfun/step-3.7-flash:free`·`poolside/laguna-s-2.1:free`·`reflection/beam-1.0-501b-a23b:free`)은 전부 잔류 — 대표 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

  - 2026-10-30 06:00 기준 무료 6종→7종 (공식 API 가격 $0 기준, 직접 확인): `inclusionai/ling-3.1-flash:free`가 카탈로그에 재등재됨 (가격 $0 확인 — 유료 변형 `inclusionai/ling-3.1-flash`는 입력 $0.075/1M·출력 $0.225/1M 유지, 별개 ID). 잔류 7종: `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`upstage/solar-mini4:free`·`stepfun/step-3.7-flash:free`·`reflection/beam-1.0-501b-a23b:free`·`ornith/ornith-1.5-122b:free`·`inclusionai/ling-3.1-flash:free`. `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free` expiration_date 2026-10-31 유지 (내일 만료). 대표 3종(`stepfun/step-3.7-flash:free`·`poolside/laguna-s-2.1:free`·`reflection/beam-1.0-501b-a23b:free`)은 전부 잔류 — 대표 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

  - 2026-10-29 06:00 기준 무료 7종→6종 (공식 API 가격 $0 기준, 직접 확인): `meituan/longcat-2.0:free`가 카탈로그에서 제거됨 (유료 변형 `meituan/longcat-2.0`만 잔류 — 가격 $0 아님). 잔류 6종: `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`upstage/solar-mini4:free`·`stepfun/step-3.7-flash:free`·`reflection/beam-1.0-501b-a23b:free`·`ornith/ornith-1.5-122b:free`. `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free` expiration_date 2026-10-31 유지 (2일 남음). 대표 3종(`stepfun/step-3.7-flash:free`·`poolside/laguna-s-2.1:free`·`reflection/beam-1.0-501b-a23b:free`)은 전부 잔류 — 대표 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

  - 2026-10-27 06:00 기준 무료 8종→7종 (공식 API 가격 $0 기준, 직접 확인, 재확인 동일): `meituan/longcat-2.5-preview:free`가 카탈로그에서 제거됨 (유료 변형 `meituan/longcat-2.5-preview`도 카탈로그에 없음 — 완전 제거). 잔류 7종: `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`upstage/solar-mini4:free`·`meituan/longcat-2.0:free`·`stepfun/step-3.7-flash:free`·`reflection/beam-1.0-501b-a23b:free`·`ornith/ornith-1.5-122b:free`. `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free` expiration_date 2026-10-31 유지 (4일 남음). 대표 3종(`stepfun/step-3.7-flash:free`·`poolside/laguna-s-2.1:free`·`reflection/beam-1.0-501b-a23b:free`)은 전부 잔류 — 대표 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

  - 2026-10-25 06:00 기준 무료 8종 유지 (공식 API 가격 $0 기준, 직접 확인): 기존 8종 전부 잔류. `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free` expiration_date 2026-10-31 유지 (6일 남음). 대표 3종 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

  - 2026-10-24 06:00 기준 무료 8종 유지 (공식 API 가격 $0 기준, 직접 확인): 기존 8종 전부 잔류. `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free` expiration_date 2026-10-31 유지 (7일 남음). 대표 3종 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

  - 2026-10-21 08:10 기준 무료 7종→8종 (공식 API 가격 $0 기준, 무새 직접 확인): `ornith/ornith-1.5-122b:free` 신규 등재. 현재 8종: `meituan/longcat-2.0:free`·`meituan/longcat-2.5-preview:free`·`ornith/ornith-1.5-122b:free`·`poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`reflection/beam-1.0-501b-a23b:free`·`stepfun/step-3.7-flash:free`·`upstage/solar-mini4:free`. 대표 3종 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).
  - 2026-10-20 06:00 기준 무료 8종→7종 (공식 API 가격 $0 기준, 직접 확인): `stepfun/step-5-preview:free`가 카탈로그에서 제거됨 (유료 변형 `step-5-preview`만 잔류). 잔류 7종: `meituan/longcat-2.0:free`·`meituan/longcat-2.5-preview:free`·`poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`reflection/beam-1.0-501b-a23b:free`·`stepfun/step-3.7-flash:free`·`upstage/solar-mini4:free`. 대표에서 `step-5-preview:free` 제외, `step-3.7-flash:free` 편입 (출처: https://inference-api.nousresearch.com/v1/models).
  - 2026-10-17 18:00 기준 무료 8종 유지이나 구성 변경 (공식 API 가격 $0 기준, 재확인): `stealth/missingno`가 카탈로그에서 제거되고 `reflection/beam-1.0-501b-a23b:free`가 신규 등재. 대표 3종: `stepfun/step-5-preview:free`·`poolside/laguna-s-2.1:free`·`reflection/beam-1.0-501b-a23b:free`. 현재 8종: `meituan/longcat-2.0:free`·`meituan/longcat-2.5-preview:free`·`poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`reflection/beam-1.0-501b-a23b:free`·`stepfun/step-3.7-flash:free`·`stepfun/step-5-preview:free`·`upstage/solar-mini4:free` (출처: https://inference-api.nousresearch.com/v1/models).
  - 2026-10-14 06:00 기준 무료 8종 (공식 API 가격 $0 기준): `stealth/missingno`, `stepfun/step-5-preview:free`, `meituan/longcat-2.5-preview:free`, `meituan/longcat-2.0:free`, `stepfun/step-3.7-flash:free`, `upstage/solar-mini4:free`, `poolside/laguna-s-2.1:free`, `poolside/laguna-xs-2.1:free`. `inclusionai/ling-3.1-flash`는 2주 체험 종료 후 유료 전환 확인 (입력 $0.075/1M, 출력 $0.225/1M) — 무료 목록에서 제거. `inclusionai/ling-3.0-flash-sante:free`·`inclusionai/ling-3.0-flash-fin:free`는 카탈로그에서 완전 삭제됨 (유료 variant `inclusionai/ling-3.0-flash`는 별도 유지, $0 아님). 대표 3순위에서 `sante:free` 제외, `step-5-preview:free` 편입. ※ `inclusionai/ling-3.1-flash`는 2026-09-30 출시 2주 무료 체험 모델 (**체험 종료 2026-10-13 확정** — Vercel AI Gateway "free to use through October 13, 2026"·Cline 10/3 발표·LLMTR 조건 공식 확인 — 10/14 아침에 Nous Portal·OpenRouter 양쪽에서 유료 전환 확인, 이후 오픈소스 공개 예정 — TechNode 보도). OpenCode Zen의 `ling-3.1-flash-free`는 10/14 아침에도 목록 유지 — 제거 미발생 (반영 지연 또는 유예, 다음 워치 재확인). `poolside/laguna-s-2.1:free`·`laguna-xs-2.1:free`는 API 응답상 `expiration_date`가 2026-10-31로 표기됨 — 이후 무료 지속 여부는 다음 워치에서 확인 (2026-10-08 라이브 확인).
  - 스텔스 모델 관련 정보: MissingNo — 공식 설명상 "free reasoning model, 262K-token context, tool calling and structured outputs, reasoning is always on" (추론 깊이 조절: low/medium/high/xhigh/max). 정체 미공개 — [실사용 영상](https://www.youtube.com/watch?v=LWlW-TXBLsk) (Hermes Cloud에서 MissingNo 사용법·토큰 효율 실측, 코딩 작업은 중상급 수준이라는 평가 — 10/12 게시). ※ 2026-10-17 저녁 카탈로그에서 제거 확인 (10/11 등재 후 6일 만에 종료).
  - 카탈로그: [Nous Portal 모델 목록](https://portal.nousresearch.com/models) — 'Free Models' 섹션 및 FREE 필터로 무료 모델 직접 확인 (로그인 불필요), 공식 API: https://inference-api.nousresearch.com/v1/models

  </details>

- **한도**: Free $0 플랜 — "$0 행 모델만, Standard rate limits" (구체 수치 미공개). 카드 불필요.
- **API**: OpenAI 호환. 엔드포인트 `https://inference-api.nousresearch.com/v1`
- **도구 호출**: 미확인
- **제한**: Privacy Mode를 켜지 않으면 추론 페이로드가 학습·개선에 활용될 수 있음. 2026-09-16에 처음 포착된 신규 항목이라 안정성 검증 중 (3자 추적 기준 provisional).
- **출처**: https://portal.nousresearch.com/models , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/nous-portal.md
- **비고**: Nous Research(Hermes Agent 제작사)의 공식 추론 포털. 형님이 세팅 중인 Hermes Agent와 같은 생태계라 연동 테스트 가치가 높음. Nous 무료 라인업은 일 단위로 뒤집히는 로테이션 패턴이 반복되므로 보조·폴백용으로만 권장. `space-bunny-alpha`는 2026-10-06 06:00 카탈로그에서 완전 제거 확인 — 기간 한정 요약표에서 정리.

<a id="anyapi"></a>

## AnyAPI <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-26 06:00 라이브 브라우저 직접 확인 — Tier 필터 Free, 5종):**
  - Qwen3.8 27B (free) — 10/06 신규 Free 등재 (Free 뱃지 직접 확인)
  - Ling 3.0 Flash Sante (free) — inclusionAI
  - Ling 3.0 Flash Fin (free) — inclusionAI
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 전체 목록: [AnyAPI AI 모델 카탈로그](https://anyapi.ai/ai-models) — 좌측 Tier 필터에서 Free 선택 (각 무료 모델에 "Free" 배지 표시)
  - 2026-10-30 06:00 라이브 브라우저 직접 확인 (뒤늦게 도착한 결과로 확정): Free 티어 5종 유지 — Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Qwen2.5 Coder 32B Instruct (free), Google Gemma 3n 4B (free) (각 카드 Free 배지, 만료일 표시 없음). 대표 3종은 전부 잔류 — 대표 변경 없음. 아침 워치 마감 시점에는 텍스트 추출만으로 Free 뱃지 매핑이 안 됐던 공백을 뒤늦게 도착한 라이브 확인 결과로 해소 (출처: https://anyapi.ai/ai-models).

  - 2026-10-29 18:00 라이브 브라우저 직접 확인 (Tier 필터 Free): Free 티어 5종 유지 — Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Google Gemma 3n 4B (free), Qwen2.5 Coder 32B Instruct (free) (각 카드 Free 배지, 만료일 표시 없음). 대표 3종은 전부 잔류 — 대표 변경 없음. 아침 워치에서 텍스트 추출만으로 Free 뱃지 확인이 안 됐던 공백을 이번 저녁 라이브 확인으로 해소 (출처: https://anyapi.ai/ai-models).

  - 2026-10-26 06:00 라이브 브라우저 직접 확인 (Tier 필터 Free): Free 티어 4종→5종 — `Qwen2.5 Coder 32B Instruct (free)`가 목록에 복귀 (2026-10-22 제거 후 복귀). 5종: Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Google Gemma 3n 4B (free), Qwen2.5 Coder 32B Instruct (free) (각 카드 Free 배지, 만료일 표시 없음). 대표 3종은 전부 잔류 — 대표 변경 없음. ※ 워치 마감 시점에는 라이브 결과가 늦게 도착해 텍스트 추출로만 확인했으나 (Free 3종 노출, Gemma 3n 텍스트 미노출), 뒤늦게 도착한 라이브 브라우저 확인 결과로 5종 복귀를 확정 (출처: https://anyapi.ai/ai-models).

  - 2026-10-25 06:00 라이브 브라우저 직접 확인 (Tier 필터 Free): Free 티어 4종 유지 — Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Google Gemma 3n 4B (free) (각 카드 Free 배지, 만료일 표시 없음). 대표 3종은 전부 잔류 — 대표 변경 없음 (출처: https://anyapi.ai/ai-models).
  - 2026-10-24 06:00 라이브 브라우저 직접 확인 (Tier 필터 Free): Free 티어 4종 유지 — Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Google Gemma 3n 4B (free) (각 카드 Free 배지, 만료일 표시 없음). 대표 3종은 전부 잔류 — 대표 변경 없음 (출처: https://anyapi.ai/ai-models).
  - 2026-10-22 06:00 라이브 브라우저 직접 확인 (Tier 필터 Free): Free 티어 5종→4종 — `Qwen2.5 Coder 32B Instruct (free)`가 목록에서 제거됨 (Free 필터 상태에서 모델 검색 시 'No items found.' — 제거 확인). 잔류 4종: Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Google Gemma 3n 4B (free). 대표 3종은 전부 잔류 — 대표 변경 없음 (출처: https://anyapi.ai/ai-models).
  - 2026-10-21 18:00 라이브 브라우저 직접 확인 (Tier 필터 Free): Free 티어 5종 유지 — Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Qwen2.5 Coder 32B Instruct (free), Google Gemma 3n 4B (free) — 각 카드 Free 배지, 만료일 표시 없음 (텍스트 추출에는 Gemma 3n이 미노출됐으나 라이브에서는 5종 전부 확인).
  - 2026-10-17 06:00 라이브 브라우저 직접 확인 (Tier 필터 Free) 기준 Free 티어 5종 유지 (전일 동일): Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Qwen2.5 Coder 32B Instruct (free), Google Gemma 3n 4B (free) — 각 카드에 "Free" 배지 표시 확인, 만료일 툴팁 없음. 대표 3종은 전부 잔류 — 대표 변경 없음.
  - 2026-10-16 18:00 라이브 브라우저 직접 확인 기준 Free 티어 5종 유지: Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Qwen2.5 Coder 32B Instruct (free), Google Gemma 3n 4B (free). 각 모델 카드에 "Free" 배지 표시 확인. ※ 텍스트 추출만으로는 Gemma 3n이 보이지 않아 제거로 오인할 뻔했으나, 라이브 브라우저(JS 렌더링)에서 5종 전부 확인 — 텍스트 추출의 false negative였음. 대표 3종은 전부 잔류 — 대표 변경 없음.
  - 2026-10-14 06:00 라이브 브라우저 직접 확인 기준 Free 티어 5종: Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Qwen2.5 Coder 32B Instruct (free), Google Gemma 3n 4B (free). Gemma 3n 4B (free)는 10/11 아침 06:00 복귀→06:15 제거→10/12 18:03 재복귀→10/13·10/14 06:00 유지 — 분 단위 로테이션 중. Ling 3.0 Flash Fin (free)은 10/04 오전 Premium 티어 표기→저녁 Free 복귀 이력 — 하루 새 뒤집히는 불안정 라인업.

  </details>

- **한도**: Free $0/월 — 일 100,000 ANY Tokens (가격 페이지 "100K / day" 표기)
- **API**: OpenAI 호환 ("Drop-in replacement for OpenAI SDK" — base URL만 교체)
- **도구 호출**: 미확인
- **제한**: **카드 불필요** — 가격 페이지 Free 플랜 카드에 "No credit card required" 명시. 무료 모델의 API 호출용 정확한 모델 ID 형식은 키 발급 후 확인 필요.
- **출처**: https://anyapi.ai/pricing , https://anyapi.ai/ai-models
- **비고**: Hermes 연결 가능(예상). 로그인 없이 무료 모델 목록을 미리 볼 수 있어 검증이 쉬움. 일 10만 토큰은 에이전트 실사용에는 빠듯 — 테스트·가벼운 용도 적합. 무료 티어 모델이 10/16 저녁 기준 5종 유지 — 10/11 아침 이후 복귀↔제거를 반복하는 불안정 라인업이라 사용 전 재확인 권장.

<a id="api-airforce"></a>

## Api.Airforce <span class="prio p-low">낮음</span>

- **대표 무료 모델 (`tier: "free"` 기준 — 2026-10-30 18:00 공개 API 라이브 확인 + 재확인, 정상 5종):**
  - `gpt-oss-20b` — 무료 티어, 정상 운영 (유지)
  - `mistral-large-4` — 무료 티어, 정상 운영 (유지)
  - `llama-instant` — 무료 티어, 정상 운영 (유지)
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 전체 목록: [Api.Airforce 무료 모델 목록](https://api.airforce/ko/models/?plans=free) (한국어, Free 플랜 필터) · [모델 카탈로그 API](https://api.airforce/v1/models) — `tier: "free"`인 항목이 무료 (2026-10-15 기준 전체 657종 중 29종). ※ `access_tiers`는 유료 모델도 전부 `["free"]`라 무료 지표로 사용 불가.
  - 2026-10-30 18:00 공개 API 라이브 확인 + 재확인 (2회 동일 스냅샷, last_check 2026-10-30T09:01:58Z): tier-free 29종 유지. 아침 major_outage였던 `kimi-k2.7-code`가 operational로 복귀 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`). `rnj-1`은 operational→partial_outage로 전환 (아침 정상), `gemma3-270m:free`·`unmoderated-gpt`는 major_outage 유지. 대표 3종(`gpt-oss-20b`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-30 06:00 공개 API 라이브 확인 + 재확인 (2회 동일 스냅샷): tier-free 29종 유지. `kimi-k2.7-code`가 major_outage로 전환 (2회 연속 확정) — 대표에서 제외, `gpt-oss-20b` 편입. `gemma3-270m:free`·`glm-4.7-flash`·`rnj-1`이 정상 복귀 — 현재 정상 6종 (`gpt-oss-20b`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`·`gemma3-270m:free`). `unmoderated-gpt`는 major_outage. 대표 3종(`gpt-oss-20b`·`mistral-large-4`·`llama-instant`)은 모두 정상. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-29 18:00 공개 API 라이브 확인 + 재확인 (2회 동일 스냅샷, last_check 2026-10-29T09:01:09Z): tier-free 29종 유지. `rnj-1`이 operational→major_outage로 전환 — 현재 정상 4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). `glm-4.7-flash`·`unmoderated-gpt`는 degraded, `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-29 06:00 공개 API 라이브 확인 (last_check 2026-10-28T20:54:09Z): tier-free 29종 유지. `rnj-1`이 major_outage→operational, `gpt-oss-20b`가 degraded→operational로 복귀 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). `glm-4.7-flash`·`unmoderated-gpt`는 degraded, `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-28 18:00 공개 API 라이브 확인 + 재확인 (2회 연속 동일 스냅샷, last_check 2026-10-28T09:02:09Z): tier-free 29종 유지. 1차(08:58:09Z)에서는 정상 5종이었으나 수 분 만에 뒤집힘 — 최종 정상 3종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). `rnj-1`은 major_outage, `gpt-oss-20b`·`glm-4.7-flash`·`unmoderated-gpt`는 degraded, `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-28 06:00 공개 API 라이브 확인 + 재확인 (1차 last_check 2026-10-27T20:55:50Z, 2차 2026-10-27T21:17:50Z — 2회 연속 tier-free 29종 동일): tier-free 29종 유지. `rnj-1`이 major_outage→operational, `glm-4.7-flash`가 partial_outage→operational로 복귀 — 현재 정상 7종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`·`rnj-1`·`glm-4.7-flash`). 단 `gpt-oss-20b`는 1차 degraded→2차 operational로 뒤집힘 (최종 정상). `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-27 18:00 공개 API 라이브 확인 + 재확인 (2회 연속 동일, last_check 2026-10-27T08:57:41Z → 08:59:41Z): tier-free 29종 유지. `rnj-1`이 operational→major_outage, `glm-4.7-flash`가 operational→partial_outage로 전환 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`). `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-27 06:00 공개 API 라이브 확인 + 재확인 (2회 연속 동일, last_check 2026-10-26T20:56:21Z): tier-free 29종 유지. `rnj-1`이 major_outage→operational, `glm-4.7-flash`가 partial_outage→operational로 복귀 — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`). `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 degraded 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-26 18:00 공개 API 라이브 확인 + 재확인 (2회 연속 동일, last_check 2026-10-26T09:00:02Z): tier-free 29종 유지. `rnj-1`이 operational→major_outage로 전환 — 현재 정상 4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). `glm-4.7-flash`는 degraded→partial_outage, `gemma3-270m:free`는 major_outage→degraded, `unmoderated-gpt`는 degraded 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-25 18:00 공개 API 라이브 확인 + 재확인 (2회 연속 동일, last_check 2026-10-25T09:03:47Z): tier-free 29종 유지. `kimi-k2.7-code`가 major_outage→operational, `gpt-oss-20b`가 major_outage→operational로 복귀. 반면 `glm-4.7-flash`는 operational→degraded로 전환. `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 비정상 유지 (1차 degraded↔2차 partial_outage 변동) — 현재 정상 5종 (`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`llama-instant`·`gpt-oss-20b`). 대표에서 `glm-4.7-flash` 제외(degraded 확정), `kimi-k2.7-code` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-25 06:00 공개 API 라이브 확인 + 재확인 (1차 last_check 2026-10-24T20:54:03Z, 2차 20:57:03Z): tier-free 29종 유지. `kimi-k2.7-code`가 operational→major_outage, `gpt-oss-20b`가 degraded→major_outage로 악화. 반면 `glm-4.7-flash`는 degraded→operational로 정상 복귀. `rnj-1`·`llama-instant`·`mistral-large-4`는 operational 유지, `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 비정상 유지 (1차 partial_outage↔2차 degraded 변동). 현재 정상 4종 (`glm-4.7-flash`·`mistral-large-4`·`rnj-1`·`llama-instant`). 대표에서 `kimi-k2.7-code` 제외(major_outage 확정), `glm-4.7-flash` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-24 18:00 공개 API 라이브 확인 + 재확인 (2회 연속 동일, last_check 2026-10-24T08:59:17Z): tier-free 29종 유지. `gpt-oss-20b`가 operational→degraded, `unmoderated-gpt`가 operational→degraded, `glm-4.7-flash`가 operational→degraded로 전환. 반면 `rnj-1`은 major_outage→operational, `llama-instant`은 partial_outage→operational로 복귀. `gemma3-270m:free`는 major_outage 유지 — 현재 정상 4종 (`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`llama-instant`). 대표에서 `glm-4.7-flash` 제외(degraded 확정), `llama-instant` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-24 06:00 공개 API 라이브 확인 + 재확인 (2회 연속 동일): tier-free 29종 유지. `glm-4.7-flash`가 degraded→operational로 정상 복귀. 반면 `rnj-1`은 operational→major_outage, `llama-instant`은 operational→partial_outage로 악화 (둘 다 재확인에서도 유지). `gemma3-270m:free`는 major_outage 유지 — 현재 정상 5종 (`gpt-oss-20b`·`mistral-large-4`·`unmoderated-gpt`·`kimi-k2.7-code`·`glm-4.7-flash`). 대표에서 `llama-instant` 제외(partial_outage 확정), `glm-4.7-flash` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-23 18:00 공개 API 라이브 확인 (1차 18:03 / 2차 18:08 KST): tier-free 29종 유지. `glm-4.7-flash`가 operational→degraded로 전환, `rnj-1`은 1차 major_outage→2차 operational로 5분 만에 뒤집힘 (불안정). 반면 `gpt-oss-20b`는 degraded→operational로 복귀, `gemma3-270m:free`는 major_outage→degraded로 개선 — 2차 기준 정상 6종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`·`gpt-oss-20b`). 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-23 06:00 공개 API 라이브 확인 (last_check 2026-10-22T20:53:32Z, 재확인 20:58:33Z — 2회 연속 동일): tier-free 29종 유지. `gpt-oss-20b`가 operational→degraded로 전환 — 현재 정상 6종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`·`rnj-1`·`unmoderated-gpt`). `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-22 18:00 공개 API 라이브 확인 (last_check 2026-10-22T09:16:57Z, 재확인 09:20:06Z — 2회 연속 동일): tier-free 29종 유지. `glm-4.7-flash`가 major_outage→operational로 정상 복귀, `unmoderated-gpt`는 partial_outage→operational로 복귀, `gemma3-270m:free`는 major_outage→degraded로 개선 — 현재 정상 7종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`·`unmoderated-gpt`). 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

  - 2026-10-22 06:00 공개 API 라이브 확인 + 5분 간격 재확인 (2회 연속 동일): tier-free 29종 유지. `gpt-oss-20b`가 partial_outage→operational로 정상 복귀, `unmoderated-gpt`는 operational→partial_outage로 악화, `glm-4.7-flash`는 degraded→major_outage로 악화. `kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`은 operational 유지, `gemma3-270m:free`는 major_outage 유지 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-21 18:00 공개 API 라이브 확인 + 18:05 재확인 (last_check 2026-10-21T09:02:39Z, 2회 연속 동일): tier-free 29종 유지. `gpt-oss-20b`가 operational→partial_outage로 전환, `glm-4.7-flash`는 operational→degraded로 전환. 반면 `kimi-k2.7-code`(major_outage→정상)·`unmoderated-gpt`(partial_outage→정상)는 복귀, `llama-instant`·`mistral-large-4`는 정상 유지 — 현재 정상 4종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`). 대표에서 `gpt-oss-20b` 제외, `kimi-k2.7-code` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-21 06:00 공개 API 라이브 확인: tier-free 29종 유지. `kimi-k2.7-code`가 operational→major_outage로 전환, `unmoderated-gpt`는 operational→partial_outage로 전환. 반면 `glm-4.7-flash`(degraded→정상)·`rnj-1`(major_outage→정상)·`gpt-oss-20b`(degraded→정상)는 복귀, `gemma3-270m:free`는 major_outage→partial_outage로 완화 — 현재 정상 5종 (`gpt-oss-20b`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`·`rnj-1`). 대표 3종(`gpt-oss-20b`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-20 18:00 공개 API 라이브 확인: tier-free 29종 유지. `glm-4.7-flash`가 degraded로 전환 (06:25 정상), `gemma3-270m:free`·`rnj-1`은 major_outage 유지 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`). 대표 3종(`gpt-oss-20b`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-20 06:00 공개 API 라이브 확인 (last_check 2026-10-19T20:57:20Z): tier-free 29종 유지. `glm-4.7-flash`가 operational→major_outage로 전환. `gpt-oss-20b`·`llama-instant`·`mistral-large-4`는 operational 확인. `kimi-k2.7-code`·`unmoderated-gpt`·`gemma3-270m:free`·`rnj-1`은 JSON 잘림으로 상태 미확인 (카탈로그 존재는 확인 — 추측 없이 미확인 표기). 대표에서 `kimi-k2.7-code` 제외, `llama-instant` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-19 18:00 공개 API 라이브 확인 (last_check 2026-10-19T08:59:33Z) + 18:04 재확인 (last_check 2026-10-19T09:04:33Z): tier-free 29종 유지. 1차 확인에서 `rnj-1`·`glm-4.7-flash`·`gemma3-270m:free`가 major_outage로 전환, `llama-instant`이 정상 복귀 — 당시 정상 5종. 재확인에서 `glm-4.7-flash`가 major_outage→operational로 5분 만에 복귀 (1차의 major_outage 판정은 일시적 뒤집힘) — 최종 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`·`unmoderated-gpt`), `gemma3-270m:free`·`rnj-1`은 major_outage 유지). 대표에서 `glm-4.7-flash` 제외, `kimi-k2.7-code` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-19 06:00 공개 API 라이브 확인: tier-free 29종 유지. `kimi-k2.7-code`가 operational→major_outage로 전환, `glm-4.7-flash`가 degraded→operational로 복귀, `gemma3-270m:free`·`llama-instant`는 degraded 유지 — 현재 정상 5종 (`gpt-oss-20b`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`·`glm-4.7-flash`). 대표에서 `kimi-k2.7-code` 제외, `glm-4.7-flash` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-18 18:00 공개 API 라이브 확인 (last_check 2026-10-18T09:00:09Z) + 재확인 (동일): tier-free 29종 유지. `llama-instant`이 operational→degraded로 전환 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`). `glm-4.7-flash`·`gemma3-270m:free`는 major_outage→degraded로 개선. 대표에서 `llama-instant` 제외, `gpt-oss-20b` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-18 06:00 공개 API 라이브 확인 (last_check 2026-10-17T20:57:06Z) + 재확인 (last_check 2026-10-17T21:03:06Z, 동일): tier-free 29종 유지. `unmoderated-gpt`가 partial_outage→operational로 복귀 (재확인에서도 유지) — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`). `glm-4.7-flash`는 operational→major_outage로 재전환, `gemma3-270m:free`는 major_outage 유지. 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-17 18:00 공개 API 라이브 확인 (last_check 2026-10-17T08:58:46Z): tier-free 29종 유지. `gemma3-270m:free`가 정상→major_outage로 전환, `glm-4.7-flash`는 partial_outage, `unmoderated-gpt`는 partial_outage — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`). 18:20 재확인에서 `glm-4.7-flash`가 partial_outage→정상 복귀. `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 partial_outage. 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-17 06:00 공개 API 라이브 확인 (last_check 2026-10-16T20:56Z): tier-free 29종 유지. `rnj-1`이 major_outage→정상 복귀, `gemma3-270m:free`도 major_outage→정상 복귀 — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`gemma3-270m:free`). 06:20 재확인에서 `glm-4.7-flash`가 정상→degraded로 전환. `unmoderated-gpt`는 partial_outage (여전히 비정상). 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-16 18:00 공개 API 라이브 확인 (last_check 18:02 KST): tier-free 29종 유지 (추적 모델 전부 tier-free 유지). `rnj-1`이 정상→major_outage로 전환, `gemma3-270m:free`가 major_outage→정상 복귀 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`). 18:20 재확인에서 `gemma3-270m:free`가 정상→major_outage로 다시 전환, `rnj-1`은 major_outage 유지, `unmoderated-gpt`는 degraded (아직 정상 아님). 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-16 06:00 공개 API 라이브 확인 (2회 연속 동일): tier-free 29종 유지. `rnj-1`(major_outage→정상)·`glm-4.7-flash`(partial_outage→정상) 복귀 — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`). `unmoderated-gpt`는 정상→major_outage로 전환, `gemma3-270m:free`는 major_outage 유지. 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-15 18:00 공개 API 라이브 확인 + 재확인: tier-free 29종 유지. `rnj-1`이 major_outage로 재전환 (06:20 정상 복귀 후) — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`, 재확인에서 `unmoderated-gpt`가 degraded→정상 복귀). `glm-4.7-flash`는 degraded→partial_outage로 악화, `gemma3-270m:free`는 major_outage 유지. 대표 3종은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-15 06:00 공개 API 라이브 확인 (last_check 10-14 20:55 UTC): tier-free 29종 유지. `rnj-1`이 정상→major_outage로 전환 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). 06:20 재확인에서 `rnj-1`이 major_outage→정상 복귀. `glm-4.7-flash`는 major_outage→degraded로 개선, `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 partial_outage. 대표에서 `rnj-1` 제외, `kimi-k2.7-code` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-14 18:00 공개 API 라이브 확인: tier-free 29종 유지. `gemma3-270m:free`가 정상→major_outage로 전환, `gpt-oss-20b`가 degraded→정상 복귀 — 현재 정상 5종 (`llama-instant`·`mistral-large-4`·`rnj-1`·`kimi-k2.7-code`·`gpt-oss-20b`). `glm-4.7-flash`는 major_outage 유지, `unmoderated-gpt`는 partial_outage. 대표 3종은 모두 정상 유지 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).
  - 2026-10-14 06:00 공개 API 라이브 확인 (last_check 05:56 KST): tier-free 29종 유지. `gpt-oss-20b`가 degraded로 전환, `rnj-1`이 major_outage에서 정상 복귀 — 현재 정상 5종 (`gemma3-270m:free`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). 06:15 재확인에서 `gemma3-270m:free`가 major_outage→정상 복귀. `gpt-oss-20b`는 degraded, `glm-4.7-flash`는 major_outage 유지, `unmoderated-gpt`는 partial_outage. 대표에서 `gpt-oss-20b` 제외, `rnj-1` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수.
  - 무료 29종: mistral 계열 18종, suno 계열 3종, `gemma3-270m:free`, `glm-4.7-flash`, `rnj-1`, `llama-instant`, `kimi-k2.7-code`, `unmoderated-gpt`, `gpt-oss-20b`, `mistral-large-4` (10/13 저녁 신규 free 티어 확인)
  - 정상 호출 가능 무료 모델은 4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`) — 2026-10-13 18:12 재확인에서 `gemma3-270m:free`·`glm-4.7-flash`·`rnj-1`이 major_outage, `unmoderated-gpt`가 partial_outage로 전환. 18:08 직접 재확인. `unmoderated-gpt`는 partial_outage, `rnj-1`은 major_outage로 전환. 18:00 1차(정상 5종: `gpt-oss-20b`·`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`·`rnj-1`) → 18:06 2차(정상 6종) 사이에도 4종이 뒤집힘 — 분 단위 변동이 계속되므로 사용 전 재확인이 필수. 대표 모델에서 `unmoderated-gpt` 제외, `glm-4.7-flash` 편입. (10/13 06:15 재확인: `gemma3-270m:free` degraded·`rnj-1` major_outage 전환, `kimi-k2.7-code`도 major_outage — 당시 정상 4종. 06:00 재확인: `kimi-k2.7-code` major_outage 전환, `gpt-oss-20b`·`gemma3-270m:free`·`glm-4.7-flash` 정상 복귀. 상태가 분 단위로 뒤집히는 중이라 사용 전 재확인이 안전. (10/12 18:25 재확인: `gpt-oss-20b`이 degraded로 전환 — 당시 정상 4종 (`kimi-k2.7-code`·`llama-instant`·`unmoderated-gpt`·`rnj-1`), `glm-4.7-flash`·`gemma3-270m:free`는 major_outage 유지. (10/12 06:10 재확인: `rnj-1`이 partial_outage로 전환 — 당시 정상 5종. (10/12 06:00 확인: `glm-4.7-flash`가 다시 major_outage로 전환됐으나 5분 간격 재확인에서 정상 복귀, `gemma3-270m:free`도 major_outage로 복귀 — 결과적으로 10/11 저녁과 동일(정상 6종). (10/11 18:00 확인: 아침에 major_outage로 전환됐던 `glm-4.7-flash`가 다시 정상 복귀. `gemma3-270m:free`는 major_outage 유지. 상태가 분 단위로 뒤집히는 중이라 사용 전 재확인이 안전. (10/11 06:00 확인: `glm-4.7-flash` major_outage로 전환, 정상 5종. (10/10 18:00 확인: `glm-4.7-flash`가 major_outage에서 정상 복귀 — 당시 정상 6종. (10/09 18:00 확인: `glm-4.7-flash`가 다시 major_outage로 전환, `unmoderated-gpt`(major_outage→정상)·`rnj-1` 정상 복귀. ※ 18:15 재확인에서 `gemma3-270m:free`도 정상 복귀 — 당시 정상 6종. (10/09 06:01엔 2종이었으나 07:10 재확인에서 `llama-instant`(degraded→정상)·`glm-4.7-flash`(major_outage→정상) 복귀. 2026-10-08 18:03 라이브 확인: 아침 정상이던 `rnj-1`이 major_outage로 전환, `unmoderated-gpt`는 partial_outage→operational로 복귀. 4분 간격 재확인에서 `glm-4.7-flash`가 정상→major_outage로 뒤집힘. `gemma3-270m:free`는 major_outage 유지.)

  </details>

- **한도**: Free $0.00/월 — 분당 1회 / 일 1,000회 ("Access to basic models")
- **API**: OpenAI 호환 (공식 홈페이지에서 Cursor·Cline·OpenCode·Claude Code 등 코딩 에이전트/CLI 연동 광고)
- **도구 호출**: 미확인
- **제한**: 카드 등록 필요 여부는 가격 페이지에 표기 없음 (미확인). 무료 플랜의 실제 호출 가능 여부는 계정으로 테스트 필요.
- **출처**: https://api.airforce/pricing , https://api.airforce/v1/models
- **비고**: 공개 카탈로그의 `tier` 표기와 가격 페이지의 "Free models" 표기가 일치하는지는 실제 키 테스트로 검증 필요. 현재 무료 모델 다수가 장애 상태라 폴백 우선순위는 낮음.

<a id="agnes-ai"></a>

## Agnes AI <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-02 공식 가격 페이지 확인 — 프로모션 $0):**
  - `agnes-3.0-flash` — 현재 $0 청구 (프로모션, 종료 시 유료 전환 가능)
  - `agnes-2.5-flash` — 현재 $0 청구 (프로모션, 종료 시 유료 전환 가능)
  <details>
  <summary>더보기 — 무료 조건 안내</summary>

  - 공식 FAQ: "Our core AI models are free to use indefinitely". 가격 페이지에서 `agnes-2.5-flash`·`agnes-3.0-flash` 현재 $0 청구 확인.
  - 무료 확인 링크: [Agnes AI 공식 가격표 (Model Pricing)](https://agnes-ai.com/en/docs/pricing) — 무료 모델만 모아보는 전용 페이지·필터는 없음 (2026-10-21 라이브 확인). 이 가격표의 'Current price' 열에서 `agnes-2.5-flash`·`agnes-3.0-flash` 모두 입력·출력·캐시 입력 전부 '$0 / M'으로 표시되고 'Current offers' 섹션에도 현재 무료로 명시됨. 기존에 걸려 있던 홈페이지 주소(`https://agnes-ai.com`)는 가격을 바로 확인할 수 없어 이 가격표로 교체함. 공식 문구 "Promotional end dates are subject to Agnes AI platform announcements"

  </details>

- **한도**: 일일 쿼터 미공개 (3자 프로브 기준 분당 약 20~30 RPM)
- **API**: OpenAI 호환. 엔드포인트 `https://apihub.agnes-ai.com/v1`
- **도구 호출**: 미확인
- **제한**: 카드 불필요. $0은 상시 계약이 아니라 현재 가격 책정 — 종료 시 유료 전환 가능. 2026-09-14 검증 목록 등록, 9/24 프로브 확인 (provisional 상태)
- **출처**: https://agnes-ai.com/en/docs/pricing , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/agnes-ai.md
- **비고**: 프로모션 $0 제공자라 우선순위 낮음. 무료 종료 시 Tracker에서 제거 검토.

<a id="bazaarlink"></a>

## BazaarLink <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-03 공식 무료 페이지 직접 확인):**
  - `qwen/qwen3.7-flash` — 1M 컨텍스트, 텍스트·이미지·비디오 입력 (24시간 프로브 100%)
  - `deepseek/deepseek-v4-flash-0731free` — 약 1M 컨텍스트, 텍스트 전용 (24시간 프로브 91%·21/23, 2026-10-19 저녁 확인 — 아침 79%에서 회복)
  <details>
  <summary>더보기 — 무료 조건 안내</summary>

  - 공식 페이지: [BazaarLink Free](https://bazaarlink.ai/free) — "Free — No Credit Card Required"
  - 2026-10-30 18:00 확인 (카탈로그 스냅샷 2026-10-30 07:39 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-30 08 UTC 기준): `qwen/qwen3.7-flash` 96%→100%(23/23)로 상승, `deepseek/deepseek-v4-flash-0731free` 91%→96%(22/23)로 상승, 나머지 4종 100% 유지. 대표 2종 중 `qwen/qwen3.7-flash`는 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-30 06:00 확인 (카탈로그 스냅샷 2026-10-29 17:46 UTC, 페이지 텍스트 추출 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-29 20 UTC 기준): `deepseek/deepseek-v4-flash-0731free` 87%→91%(21/23)로 상승, `stealth/glyph-cluster` 100%(23/23) 유지, 나머지 4종(`qwen/qwen3.7-flash` 96%(22/23)·`reflection/beam` 96%(22/23)·`reflection/beam-free`·`nvidia/nemotron-3.5-lightning-free` 100%) 유지. 대표 2종 중 `qwen/qwen3.7-flash`는 96% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-29 18:00 확인 (카탈로그 스냅샷 2026-10-29 02:43 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-29 08 UTC 기준): `qwen/qwen3.7-flash` 100%→96%(22/23)로 하락, `reflection/beam` 100%→96%(22/23)로 하락, `deepseek/deepseek-v4-flash-0731free` 91%→87%(20/23)로 하락, 나머지 3종 100% 유지. 대표 2종 중 `qwen/qwen3.7-flash`는 96% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-29 06:00 확인 (카탈로그 스냅샷 2026-10-28 18:33 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-28 20 UTC 기준): `stealth/glyph-cluster` 87%→100%(23/23)로 상승, `deepseek/deepseek-v4-flash-0731free` 96%→91%(21/23)로 하락, 나머지 4종 100% 유지. 대표 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-28 18:00 확인 (카탈로그 스냅샷 2026-10-28 08:10 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-28 08 UTC 기준): `stealth/glyph-cluster` 75%→87%(20/23)로 상승, `deepseek/deepseek-v4-flash-0731free` 92%→96%(22/23)로 소폭 상승, 나머지 4종 100% 유지. 대표 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-28 06:00 확인 (카탈로그 스냅샷 2026-10-27 17:46 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 24개, 2026-10-27 20 UTC 기준): `stealth/glyph-cluster` 78%→75%(18/24)로 하락, `deepseek/deepseek-v4-flash-0731free` 96%→92%(22/24)로 소폭 하락, 나머지 4종 100% 유지. 대표 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-27 18:00 확인 (카탈로그 스냅샷 2026-10-27 05:19 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-27 08 UTC 기준): `stealth/glyph-cluster` 83%→78%(18/23)로 하락, `deepseek/deepseek-v4-flash-0731free` 100%→96%(22/23)로 소폭 하락, 나머지 4종 100% 유지. 대표 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-27 06:00 확인 (카탈로그 스냅샷 2026-10-26 18:56 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 24개, 2026-10-26 20 UTC 기준): `stealth/glyph-cluster` 78%→83%(20/24)로 소폭 상승, 나머지 5종 100% 유지. 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-26 18:00 확인 (카탈로그 스냅샷 2026-10-26 04:05 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-26 08 UTC 기준): `stealth/glyph-cluster` 87%→78%(18/23)로 하락, 나머지 5종 100% 유지. 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-26 06:00 확인 (카탈로그 스냅샷 2026-10-25 17:46 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-25 20 UTC 기준): `qwen/qwen3.7-flash` 100%(23/23)·`deepseek/deepseek-v4-flash-0731free` 100%(23/23, 96%→상승)·`nvidia/nemotron-3.5-lightning-free` 100%(23/23)·`reflection/beam-free` 100%(23/23)·`reflection/beam` 100%(23/23)·`stealth/glyph-cluster` 87%(20/23, 83%→소폭 상승). 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-25 06:00 확인 (카탈로그 스냅샷 2026-10-24 17:46 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 24개, 2026-10-24 20 UTC 기준): `qwen/qwen3.7-flash` 100%(24/24)·`deepseek/deepseek-v4-flash-0731free` 96%(23/24, 92%→소폭 상승)·`nvidia/nemotron-3.5-lightning-free` 100%(24/24)·`reflection/beam-free` 100%(24/24)·`reflection/beam` 100%(24/24)·`stealth/glyph-cluster` 83%(20/24, 유지). 대표 2종 중 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-24 18:00 확인 (카탈로그 스냅샷 2026-10-24 02:29 UTC, 페이지 직접 확인): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 24개, 2026-10-24 08 UTC 기준): `qwen/qwen3.7-flash` 100%(24/24)·`deepseek/deepseek-v4-flash-0731free` 92%(22/24, 96%→소폭 하락)·`nvidia/nemotron-3.5-lightning-free` 100%(24/24)·`reflection/beam-free` 100%(24/24)·`reflection/beam` 100%(24/24)·`stealth/glyph-cluster` 83%(20/24, 91%→하락). 대표 2종 중 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-24 06:00 확인 (카탈로그 스냅샷 2026-10-23 17:46 UTC, 페이지 HTML 직접 추출): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-23 20 UTC 기준): `qwen/qwen3.7-flash` 100%(23/23)·`deepseek/deepseek-v4-flash-0731free` 96%(22/23, 100%→소폭 하락)·`nvidia/nemotron-3.5-lightning-free` 100%(23/23)·`reflection/beam-free` 100%(23/23)·`reflection/beam` 100%(23/23)·`stealth/glyph-cluster` 91%(21/23, 74%→개선). 대표 2종은 모두 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-23 18:00 확인 (카탈로그 스냅샷 2026-10-23 08 UTC, 페이지 HTML 직접 추출): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개): `qwen/qwen3.7-flash` 100%(23/23)·`deepseek/deepseek-v4-flash-0731free` 100%(23/23)·`nvidia/nemotron-3.5-lightning-free` 100%(23/23)·`reflection/beam-free` 100%(23/23)·`reflection/beam` 96%→100%(23/23, 개선)·`stealth/glyph-cluster` 61%→74%(17/23, 개선). 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-23 06:00 확인 (카탈로그 스냅샷 2026-10-22 17:46 UTC): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-22 20 UTC): `qwen/qwen3.7-flash` 100%(23/23)·`deepseek/deepseek-v4-flash-0731free` 100%(23/23)·`nvidia/nemotron-3.5-lightning-free` 100%(23/23)·`reflection/beam-free` 100%(23/23)·`reflection/beam` 96%(22/23)·`stealth/glyph-cluster` 61%(14/23, 65%→소폭 하락). 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-22 18:00 확인 (카탈로그 스냅샷 2026-10-22 07:44 UTC, 프로브 기준 08 UTC): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개): `qwen/qwen3.7-flash` 100%(23/23)·`deepseek/deepseek-v4-flash-0731free` 100%(23/23)·`nvidia/nemotron-3.5-lightning-free` 100%(23/23)·`reflection/beam-free` 100%(23/23, 96%→상승)·`reflection/beam` 96%(22/23, 100%→소폭 하락)·`stealth/glyph-cluster` 65%(15/23, 63%→소폭 상승). 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

  - 2026-10-22 06:00 확인 (카탈로그 스냅샷 2026-10-21 17:46 UTC): 무료 6종 유지 (동일 ID). 24h 프로브: `qwen/qwen3.7-flash` 100%(24/24)·`deepseek/deepseek-v4-flash-0731free` 100%(24/24)·`nvidia/nemotron-3.5-lightning-free` 100%(24/24)·`reflection/beam` 100%(24/24)·`reflection/beam-free` 96%(23/24)·`stealth/glyph-cluster` 63%(15/24, 52%→상승) (출처: https://bazaarlink.ai/free).
  - 무료 모델은 "enabled free models" 표에서만 제공 (로테이션 가능)

  </details>

- **한도**: 무충전 계정 — 10 RPM · 일 60 가중 단위 / 충전 계정 — 20 RPM · 일 120 가중 단위 (무료 모델 간 공유, 00:00 UTC 일일 리셋). 사이트 전체 무료 RPM 상한 15, 계정당 동시 무료 요청 2개
- **API**: OpenAI 호환. 엔드포인트 `https://api.bazaarlink.ai/v1`
- **도구 호출**: 미확인 (공식 무료 페이지에 언급 없음)
- **제한**: 카드 불필요 (이메일 가입 후 60초 만에 무료 키 발급). 긴 입력은 가중 단위 소모가 커짐 (가중 단위: 입력 길이에 따라 소모량이 달라지는 한도 단위)
- **출처**: https://bazaarlink.ai/free
- **비고**: 영구 무료 티어라 조사 범위 충족. 일 한도가 작아(짧은 요청 기준 일 ~60회 수준) 테스트·가벼운 폴백용. 운영사 대만 소재.

<a id="ollama-cloud"></a>

## Ollama Cloud <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-21 라이브 확인):**
  - `beam` — Reflection의 501B MoE (약 23B 활성), 코딩·에이전트·추론용, 1M 컨텍스트. 클라우드 모델 페이지에 'free' 태그가 붙은 유일한 모델 (2026-10-16 공식 블로그에서 기간 한정 무료 공지 — 종료일 미공지)
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 전체 클라우드 모델: [Ollama 모델 검색 — Cloud 필터](https://ollama.com/search?c=cloud) — 로그인 없이 확인 가능. 클라우드 모델 21개 중 'free' 태그 모델은 `beam` 1개뿐 (2026-10-21 라이브 전수 확인). 나머지 20개는 모델별 가격 표기 (예: `minimax-m3.1-flash` 입력 $0.15 · 출력 $0.60 / 1M 토큰). `beam`은 공식 가격표의 모델 가격 목록에도 유일하게 빠져 있어 무료와 정합함.
  - 2026-10-30 18:00 텍스트 추출 확인: free 태그는 `beam` 1종 유지, `minimax-m3.1-flash` 유료 표기 유지 — 단 텍스트 추출에는 20종만 노출돼 총수 변경 단정 불가, 저녁 라이브 재확인 필요 (출처: https://ollama.com/search?c=cloud).

  - 2026-10-29 18:00 라이브 브라우저 직접 확인: 클라우드 모델 21종 유지 (전수 스크롤 카운트, 마지막에 `gpt-oss` 포함 — 아침 텍스트 추출 20종과의 차이는 노출 차이). free 태그는 `beam` 1종 유지. `minimax-m3.1-flash` 상세 Cost 패널 유료 표기(입력 $0.15·캐시 $0.015·출력 $0.60/1M) 유지 — 무료 배지 복귀 없음 (출처: https://ollama.com/search?c=cloud).

  - 2026-10-28 18:00 라이브 브라우저 직접 확인: 클라우드 모델 20종→21종 (전수 스크롤 카운트 — 저녁 카운트에 `gpt-oss` 포함, 아침 누락 vs 신규 등재 구분 불가; 텍스트 추출에서는 20종만 노출). free 태그는 `beam` 1종 유지. `minimax-m3.1-flash` 상세 Cost 패널 유료 표기(입력 $0.15·캐시 $0.015·출력 $0.60/1M) 유지 — 무료 배지 복귀 없음 (출처: https://ollama.com/search?c=cloud).

  - 2026-10-28 06:00 라이브 브라우저 직접 확인: 클라우드 모델 21종→20종 (free 태그는 `beam` 1종 유지). 제거된 1종은 기준선에 개별 명단이 없어 특정 불가. `minimax-m3.1-flash` 상세 Cost 패널 유료 표기(입력 $0.15·캐시 $0.015·출력 $0.60/1M) 유지 — 무료 배지 복귀 없음 (출처: https://ollama.com/search?c=cloud).

  - 2026-10-25 06:00 라이브 브라우저 직접 확인: 클라우드 모델 21종 중 free 태그는 `beam` 1종 유지 (스크롤 후 gpt-oss까지 전수 21종 확인). `minimax-m3.1-flash` 상세 Cost 패널 유료 표기(입력 $0.15·캐시 $0.015·출력 $0.60/1M) 유지 — 무료 배지 복귀 없음 (출처: https://ollama.com/search?c=cloud).

  - 2026-10-24 06:00 라이브 브라우저 직접 확인: 클라우드 모델 21종 중 free 태그는 `beam` 1종 유지. `minimax-m3.1-flash` 상세 페이지 Cost 패널에서 유료 표기(입력 $0.15·캐시 $0.015·출력 $0.60/1M) 유지 — 무료 배지 복귀 없음 (출처: https://ollama.com/search?c=cloud).

  - 기간 한정 무료 프로모션 (상시 목록이 아니라 공식 블로그·SNS 건별 공지 방식):
    - `beam` — 2026-10-16 공식 블로그 "Reflection's Beam is freely available on Ollama for a limited time" (기간 한정, 종료일 미공지, zero data retention 표기) (출처: https://ollama.com/blog/reflection-beam)
    - `minimax-m3.1-flash` — 2026-10-19 공식 SNS 공지로 Ollama Cloud에서 3일간 무료 (종료 2026-10-22 23:59 UTC = 한국 시간 2026-10-23 08:59). 2026-10-23 저녁 확인: 모델 상세 페이지 Cost 패널에서 'free until Oct 22, 2026 11:59 PM UTC' 무료 배지 사라짐, 정가(입력 $0.15·캐시 $0.015·출력 $0.60/1M) 표기 — 무료 종료 확정, 유료 전환. 기간 한정 요약표에서 정리 (출처: https://ollama.com/search?c=cloud).
  - Free 플랜 starter 사용량: Free 계정에 starter 모델용 월간 사용량이 포함됨 (공식 블로그 'transparent pricing' 2026-08-31 + 가격 페이지 FAQ 확인) — 단, 어떤 모델이 starter인지는 공개 명단이 없고 크레딧 금액도 미공개 (미확인).

  </details>

- **한도**: Free 플랜 $0 — starter usage credits 포함, 가입일 기준 월별 리셋·이월 불가, 동시 요청 1개 (공식 가격 페이지 FAQ). starter 크레딧의 구체 금액은 미공개.
- **API**: OpenAI 호환 API·Anthropic API·Ollama API 제공 (공식 SNS 공지 명시). 클라우드 모델은 `:cloud` 태그로 호출 (예: `ollama run beam:cloud`).
- **도구 호출**: 지원 (클라우드 모델 페이지의 tools 태그 표기 — beam 포함).
- **제한**: 사용하려면 Ollama 계정 가입 필요. 카드 필요 여부는 가격 페이지에 관련 문구가 없어 미확인. 무료 형태가 ① free 태그 모델(기간 한정) ② 건별 기간 한정 프로모션 ③ starter 월간 사용량(명단 미공개)의 조합이라, 특정 모델의 상시 무료로 단정할 수 있는 것은 없음.
- **출처**: https://ollama.com/search?c=cloud , https://ollama.com/pricing , https://ollama.com/blog/reflection-beam
- **비고**: 2026-10-15 본 목록 제외, 2026-10-21 형님 결정으로 '확인 필요' 후보에서도 완전 제외했으나, 같은 날 형님이 클라우드 모델 페이지가 로그인 없이 열리고 free 태그로 무료 모델을 특정할 수 있음을 직접 확인해 재등록으로 전환. 제외 사유였던 'starter 명단 비공개'는 여전히 유효하므로, 등록 범위를 공개 확인 가능한 free 태그 모델 + 공식 공지 프로모션으로 한정함.

<a id="cline"></a>

## Cline <span class="prio p-no">연동 불가</span>

- **무료 모델**: Cline 계정 사용자에게 제공되는 기간 한정 무료 모델 프로모션 (모델 목록은 로테이션되며, 2026-09-17 기준 deepseek-v4-flash 제외 등 변동). 고정된 무료 모델 ID 목록 없음.
- **한도**: 프로모션별 일일 사용량 제한 — 구체 수치 미확인
- **API**: Cline API 존재 (OpenAI 호환 Chat Completions, `https://api.cline.bot/api/v1` — 공식 API 문서 2026-10-25 직접 확인). 단, 무료 모델의 API 경유 사용은 여전히 미지원 — 공식 무료 모델 문서(Updated 2026-07-29) 명시: "Free model usage is not supported through the Cline API. Free models are only available in the Cline IDE Extension and CLI."
- **도구 호출**: 해당 없음 (API 미제공)
- **제한**: 무료 모델 사용 데이터가 모델 개선에 활용될 수 있음. 무료 할당량 소진 후 ClinePass($9.99/월) 또는 usage-billing 전환.
- **출처**: https://docs.cline.bot/getting-started/free-models
- **비고**: Cline API는 유료 usage-billing 게이트웨이로 존재하나, 무료 모델은 Cline IDE Extension·CLI 안에서만 사용 가능하므로 Hermes 무료 연결 대상에서는 제외 유지. 형님께 "Cline 무료 모델은 Cline 안에서만 쓸 수 있다"고 안내 필요.

<a id="limited-free"></a>

## 기간 한정 무료

- **안내**: 상시 무료가 아닌, 기간·조건이 한정된 무료 제공자 모음. 종료일이 다가오면 아침·저녁 워치에서 만료 여부를 확인합니다.

| 제공자 | 무료 조건 | 종료 예정 | OpenAI 호환 |
|---|---|---|---|
| [ZeroLimitAI](#zerolimitai) | 7일 체험, 일 100회 | 키 발급 후 7일 (종료 시 402) | O |
| [Hetzner Inference API](#hetzner-inference-api) | 실험 단계 무료 | 미정 (사전 이메일 공지) | O |
| [OpenCode Zen](#opencode-zen) 무료 모델 | 기간 한정 (전 모델) | 모델별 상이 | O |
| [Nous Portal](#nous-portal) `ling-3.1-flash` | 2주 무료 체험 | **2026-10-13 (Vercel·Cline·LLMTR 공식 확인)** — **10/14 아침 유료 전환 확인** (Nous Portal·OpenRouter 양쪽, 입력 $0.075/1M·출력 $0.225/1M). OpenCode Zen의 `ling-3.1-flash-free`는 종료일(10/13) 이틀 뒤인 10/15 아침에 목록에서 제거 확인 — 체험 종료 완료. ※ 2026-10-30 아침 Nous Portal에 `inclusionai/ling-3.1-flash:free` 변형이 가격 $0으로 재등재 확인 (유료 변형과 별개 ID) — 같은 날 저녁 재제거 확인 (무료 7종→6종, 당일 재등재→재제거) | O |
| `space-bunny-alpha` ([Nous Portal](#nous-portal)·[OpenRouter](#openrouter)) | 기간 한정 무료 등재 | 만료(2026-10-05) → 양쪽 카탈로그에서 제거 확인 (2026-10-06) | O |
| laguna `:free` ([OpenRouter](#openrouter)·[Nous Portal](#nous-portal)) | 무료 제공 만료일 2026-10-31 표기 (이후 지속 여부 확인 필요) | 2026-10-31 (laguna-s-2.1·laguna-xs-2.1만 유지 — 10/21 확인, inkling 2종은 만료일 표기 사라짐) | O |
| [OpenRouter](#openrouter) `minimax-m3.1-flash:free` | 기간 한정 무료 (공식 X 10/19 "72시간 무료" 공지) | **2026-10-23 06:00 카탈로그에서 제거 확인 — 무료 종료 확정** (10/22 저녁까지 $0 유지, 10/23 아침 제거) | O |
| [Ollama Cloud](#ollama-cloud) `beam`·`minimax-m3.1-flash` | 기간 한정 무료 (공식 블로그·SNS 건별 공지) | beam: 종료일 미공지 / minimax-m3.1-flash: **2026-10-23 08:59 KST 무료 종료 확정** (10/23 저녁 유료 전환 확인) | O |
| [Cline](#cline) 무료 모델 | 기간 한정 프로모션 | 모델별 상이 | X (API 미제공) |

<a id="zerolimitai"></a>

## ZeroLimitAI <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-04 공식 개발자 페이지 확인):**
  - `auto` — 자동 라우팅: ZeroOptimize™가 매일 재평가한 무료 모델 중 살아 있는 최고 모델로 자동 연결, 장애 시 폴오버
  <details>
  <summary>더보기 — 무료 플랜 안내</summary>

  - 공식 개발자 페이지: [ZeroLimitAI Developers](https://www.zerolimitai.com/developers) — "Free week — $0 for 7 days" (2026-10-04 변경 확인, 기존 "Free — $0 forever"에서 전환). 2026-10-23 확인: 무료 주간 일일 한도가 100회→25회로 축소 ("25 calls/day during the free week", FAQ 'What are the rate limits?' 명시 — 라이브 브라우저 직접 확인).
  - `model: "auto"` 하나로 호출, chat completions·스트리밍·함수 호출(tools) 지원

  </details>

- **한도**: Free week — $0 for 7 days. 일 25회 (2026-10-23 확인 — 기존 일 100회에서 축소), 00:00 UTC 리셋. 체험 종료 후 키는 HTTP 402 upgrade_required — Annual($99/년, 일 2,000회) 필요. Lifetime은 2026-10-26 판매 종료 (기존 구매자는 유지)
- **API**: OpenAI 호환. 엔드포인트 `https://www.zerolimitai.com/api/v1`
- **도구 호출**: 지원 (함수 호출 공식 지원)
- **제한**: 카드 불필요 (체험은 평가용 — 프로덕션은 유료 플랜 필요). 상위 무료 모델 할당량은 전체 사용자와 공유 — 부족 시 무료 요청은 하위 모델로 처리될 수 있음 (공식 FAQ 명시). 임베딩·이미지 입력 미지원
- **출처**: https://www.zerolimitai.com/developers
- **비고**: 2026-10-04 "Free — $0 forever"에서 "Free week — $0 for 7 days"로 변경 확인 → 상시 무료 범위에서 제외, 기간 한정 섹션으로 이동 (2026-10-05 형님 승인).

<a id="hetzner-inference-api"></a>

## Hetzner Inference API <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-06 Hetzner Docs 확인 — 공식 모델 2종):**
  - `Qwen/Qwen3.6-35B-A3B-FP8` — 35B MoE (토큰당 활성 3B), 262K 컨텍스트, 텍스트·이미지 입력, Apache 2.0
  - `Qwen3.8-27B` — 27B Dense (10/06 Docs 신규 확인), 262K 컨텍스트, 텍스트·이미지 입력, Apache 2.0
  <details>
  <summary>더보기 — 무료 조건 안내</summary>

  - 공식 문서 FAQ: "Can I use the Inference API for free? — As long as the Inference API remains in experimental status, it is free of charge. Should this status change, we will notify you in advance via email with detailed information."
  - 3자 자료에서 DeepSeek-V4-Flash-0731·GLM-5.2·Kimi-K2.7-Code 등 추가 모델 언급도 있으나 공식 Docs 기준 미확인

  </details>

- **한도**: API 키당 — 60초당 입력 400만 토큰·출력 10만 토큰 + 60초당 10회 요청 제한 (2026-10-06 공식 Docs FAQ 기준 — 기존의 "24시간당 입력 5억·출력 500만 토큰" 표기는 삭제됨, 입력 300만→400만·출력 6만→10만으로 변경)
- **API**: OpenAI 호환. 엔드포인트 `https://inference.hetzner.com/api/v1`
- **도구 호출**: 미확인 (공식 Docs에 언급 없음)
- **제한**: 카드 불필요 (Hetzner 무료 계정 + API 토큰). 실험 단계 — "as is" 제공, 성능·가용성 보장 없음, SLA 없음, 프로덕션 비권장
- **출처**: https://docs.hetzner.com/general/company-and-policy/experiments/inference/
- **비고**: 2026-07 출시 이후 계속 무료. 종료일이 정해져 있지 않으나 언제든 유료 전환 가능 — 기간 한정으로 분류.

<a id="changelog"></a>

<a id="확인-필요"></a>

## 확인 필요

공식 확인이 안 돼 Tracker에 등록하지 않은 후보 목록. 확인되면 등록, 기준 미달이면 제외.

- **Typhoon (SCB 10X)** — 공식 FAQ "research showcase and free to use", OpenAI 호환 (`https://api.opentyphoon.ai/v1`). 태국어 특화 모델이라 형님 판단 대기 중 (2026-10-15). (출처: https://docs.opentyphoon.ai/en/faq/)
- **Agnes AI** — `agnes-2.5-flash`·`agnes-3.0-flash` 현재 $0 청구 확인 (공식 Docs 가격표, 2026-10-19 아침 직접 확인 — 무료 프로모션 명시). 단 "프로모션" 표기라 종료 시 유료 전환 가능 — 조건부 후보.
- **Kilo Code 게이트웨이** — 익명 시간당 200회/IP 무료로 보이나 `mayTrainOnYourPrompts` 표기 — 데이터 정책 확인 필요.
- **Routeway** — OpenAI 호환 무료 `:free` 9종이나 공식 이용약관상 결제 수단 등록 필수 — 카드 불필요 기준 미달로 제외 권고, 형님 답 대기 중.
- **LLMTR** — 등록 보류 유지.
- **Cloudflare Workers AI** — OpenAI 호환 공식 확인 (`/ai/v1/chat/completions`·`/ai/v1/responses`, 도구 호출 지원 — 2026-10-16 공식 Docs·3자 검증). 무료 10,000 Neurons/day (전 플랜 공통, 일 00:00 UTC 리셋, 카드 불필요 — 2026-10-21 아침 확인에서 표기 유지, 문서 Updated 2026-10-20). 일부 모델(Kimi K2.6/K2.7-code·GLM-5.2 등)은 Workers Paid 플랜 필요로 제외 — 무료 모델 목록은 공식 카탈로그에서 추가 확인 필요 (2026-10-16 신규 후보). (출처: https://developers.cloudflare.com/workers-ai/platform/pricing/, https://developers.cloudflare.com/ai-gateway/usage/rest-api/)
- **UnoRouter** — OpenAI 호환 공식 확인 (`/v1/chat/completions`, "Any OpenAI-compatible client", 모델 페이지에 Tools/Reasoning 태그 — 모델별 상이). 공식 홈페이지 "Free 120, No cost"(2026-10-24 아침 직접 확인 — Free 120 유지, MODELS 255·PROVIDERS 43+·PAID 135, 분 단위 변동 중). 2026-10-29 저녁 확인: 라이브 브라우저 기준 Free 143→140 (MODELS 274→270·PROVIDERS 46+→45+·PAID 131→130, 140+130=270 일치) — 10/28 저녁 143에서 3 감소, 분 단위 변동 지속. 아침 텍스트 추출 기준 Free 124는 라이브 값과 달라 이번 저녁 라이브 값 140으로 기록. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 2026-10-30 아침 확인: 텍스트 추출 기준 Free 126 (MODELS 258·PROVIDERS 42+·PAID 132, 126+132=258 일치)이나 라이브 값과 달라 저녁 라이브 재확인 필요 — 10/29 저녁 라이브 값 140 유지. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 2026-10-30 아침 뒤늦게 도착한 라이브 브라우저 확인 (06:01~06:04 KST): 라이브 기준 Free 140→122 (MODELS 270→254·PROVIDERS 45+→41+·PAID 130→132, 122+132=254 일치) — 10/29 저녁 140에서 18 감소, 분 단위 변동 지속. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 같은 아침 라이브 재확인 (06:13~06:15 KST): 라이브 기준 Free 122→126 (MODELS 254→258·PROVIDERS 41+→42+·PAID 132 유지, 126+132=258 일치) — 10여 분 만에 재반등, 분 단위 변동 지속. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 2026-10-30 저녁 확인: 텍스트 추출 기준 Free 137 (MODELS 269·PROVIDERS 44+·PAID 132, 137+132=269 일치)이나 라이브 값과 달라 저녁 라이브 재확인 필요 — 10/30 아침 라이브 값 126 유지. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 2026-10-26 아침 확인: 라이브 브라우저 기준 Free 127 (MODELS 257·PROVIDERS 42+·PAID 130, 127+130=257 일치) — 10/25 저녁 라이브 148에서 21 감소. 같은 아침 텍스트 추출 기준 Free 128 (MODELS 258·PAID 130) — 라이브 기준 127로 기록, 분 단위 변동 지속. 2026-10-26 저녁 확인: 라이브 브라우저 기준 Free 136 (MODELS 267·PROVIDERS 44+·PAID 131, 136+131=267 일치) — 아침 127에서 9 증가, 분 단위 변동 지속. 2026-10-27 저녁 확인: 라이브 브라우저 기준 Free 140 (MODELS 271·PROVIDERS 48+·PAID 131, 140+131=271 일치) — 10/26 저녁 136에서 4 증가, 분 단위 변동 지속. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 2026-10-28 아침 확인: 라이브 브라우저 기준 Free 140→125 (MODELS 271→255·PROVIDERS 48+→46+·PAID 131→130, 125+130=255 일치) — 저녁 140에서 15 감소, 분 단위 변동 지속. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 2026-10-28 저녁 확인: 라이브 브라우저 기준 Free 125→143 (MODELS 255→274·PROVIDERS 46+ 유지·PAID 130→131, 143+131=274 일치) — 아침 125에서 18 증가, 분 단위 변동 지속. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 2026-10-25 아침 확인: 라이브 브라우저 기준 Free 104 (MODELS 241·PROVIDERS 39+·PAID 137, 104+137=241 일치) — 10/24 저녁 라이브 119에서 15 감소. 같은 아침 텍스트 추출 기준 Free 102 (MODELS 239·PAID 137) — 라이브 기준 104로 기록, 분 단위 변동 지속. 2026-10-25 저녁 확인: 라이브 브라우저 기준 Free 148 (MODELS 274·PROVIDERS 44+·PAID 126, 148+126=274 일치) — 아침 104에서 44 증가, 분 단위 변동 지속. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en). 2026-10-24 저녁 확인에서는 분 단위 변동 확인 — 라이브 브라우저 18:00 기준 Free 119 (MODELS 255·PROVIDERS 43+·PAID 136, 119+136=255 일치), 같은 저녁 텍스트 추출 기준 Free 121 (MODELS 257·PAID 136). 단일 수치로 고정하기보다 119~121 구간 변동으로 기록. 모델별 입·출력 $0.00/1M, 카드 불필요 ("No credit card needed to start"). 무료 한도 수치 공개됨 (2026-10-21 저녁 'Rate Limits & Errors' 공식 문서 라이브 확인): 무료 모델당 사용자당 분당 1요청 (1 RPM per free model per user), 일부 무료 풀은 일일 토큰 예산 (UTC 자정 초기화) + TPM 캡 + 사용자당 병렬 요청 제한, 유료 모델은 UnoRouter 자체 제한 없음. 등록 여부 형님 판단 대기 (2026-10-17 신규 후보). (출처: https://unorouter.com/en, https://unorouter.com/en/docs/platform/errors-and-rate-limits)
- **DreamPrompting** — OpenAI 호환 공식 확인 (`https://dreamprompting.com/api/v1`). 공식 가격 페이지 기준 무료 플랜 (카드·구독 불필요), 한도 IP당 100 RPM + 계정당 24h 롤링 5,000 요청/500,000 토큰. 자체 모델 없이 27개 업스트림 제공자 무료 티어로 라우팅하는 게이트웨이 (공유 할당량 방식). 2026-10-20 저녁: 공식 홈페이지에 라우트 테이블 공개 — 13개 제공자 live 상태 (Groq·Mistral(La Plateforme)·NVIDIA NIM·Cohere·Google AI Studio·OpenRouter·Cloudflare Workers AI·Hugging Face·Codestral·ch.at 등, 무료 티어 우선 라우팅), 14개 추가 제공자 'being enabled'. 런칭일 미공개라 "신규 제공자" 확정은 불가 — 등록 여부 형님 판단 대기 (2026-10-20 신규 후보). (출처: https://dreamprompting.com)
- **Inferbase** — OpenAI 호환 공식 확인 (엔드포인트 `https://api.inferbase.ai/v1`, client-compatibility 문서). 영구 무료 Free 플랜 ("$0 no time limit", "A free plan, not a trial"), 카드 불필요. 한도: 월 5,000 requests (any model/any key) + managed inference 일 100 requests/$0.50 of model usage (초과 시 402), 키당 60 RPM·managed 10 RPM/organization, 요청당 입력 8,192/출력 1,024 토큰 예산. 자체 provider 계정으로 서빙하는 managed inference를 공유 할당량으로 제공하는 게이트웨이 ("Build on every model within daily limits"). 등록 여부 형님 판단 대기 (2026-10-20 신규 후보 — mvalentsev/awesome-free-ai-coding 'New this week'). (출처: https://inferbase.ai/pricing)
- **IteraCompute** — OpenAI 호환 공식 확인 (엔드포인트 `https://api.iteracompute.com/v1/chat/completions`, tool calling·streaming 지원). `qwen/qwen3.8-27b` 무료 (입·캐시 입력·출력 전부 $0/1M), 카드 불필요. 한도: 월 30M tokens (일 할당 없음, 매월 1일 00:00 UTC 리셋, 초과 시 429), TPM 160,000, context 128K (출력 8,192 cap). 자체 GPU 인프라에서 서빙 ("Itera Hosted Online"). 카탈로그 2026-10-19 업데이트. 등록 여부 형님 판단 대기 (2026-10-20 신규 후보 — mvalentsev/awesome-free-ai-coding 'New this week'). ※ 2026-10-22 저녁 확인: `moonshotai/kimi-k3-free`도 카탈로그에 있으나 누적 $10 이상 충전 시에만 $0 — 카드 불필요 기준 미달. (출처: https://iteracompute.com/free/)
- **SimpleLLM** — OpenAI 호환 공식 확인 (`POST /v1/chat/completions`, `https://api.simplellm.eu/v1`). 무료 모델 2종 — `free-Llama-3.1-8B-Instruct`·`free-gemma-4-E4B` (공개 카탈로그 API `https://simplellm.eu/api/models`에서 `is_free`·enabled·available 직접 확인). 계정+API 키 발급 필요, 카드 불필요 (3자 확인). 무료 모델 별 시간/일 요청·토큰 예산 (3자 검증: Free models only / 100 RPH / 1,000 RPD / 50,000 TPM / 500,000 TPD). 독일 Stage One Solutions UG 운영. 2026-10-22 확인: `is_free:true`이나 `status:"planned"`·`enabled:false`인 2종(`Mistral-7B-Instruct-v0.3`, `kode-14b`)이 카탈로그에 신규 등장 — 사용 불가라 본 목록 변경 없음, 관찰 메모로 유지. 등록 여부 형님 판단 대기 (2026-10-20 신규 후보 — mvalentsev/awesome-free-ai-coding 'New this week'). (출처: https://simplellm.eu/docs/models.md, https://simplellm.eu/api/models)
- **AnyRouter** — OpenAI 호환 공식 확인 (엔드포인트 `https://anyrouter.dev/api/v1/chat/completions`, `anyrouter/free` 자동 라우팅 + BYOK 지원). 상시 무료 Free plan $0 (체험 아님·일일 캡 없음 — 무료 모델 2400 req/min per key), 카드 불필요 (공식 FAQ "no card required"). 271모델·17개 제공자 게이트웨이. 유료 모델 호출 시 402 반환 (월 크레딧 없음). 등록 여부 형님 판단 대기 (2026-10-21 신규 후보). (출처: https://anyrouter.dev/blog/free-llm-api-for-students, https://anyrouter.dev/blog/anyrouter-pricing-free-vs-go)
- **NovAI** — OpenAI 호환 공식 확인 (엔드포인트 `https://aiapi-pro.com/v1`, 홍콩 게이트웨이). 공식 무료 페이지 "Free Chinese AI API — 5 models, 10 calls/day, no credit card": 챗 3종(`glm-4.7-flash`·`glm-4.6v-flash`·`glm-4.1v-thinking-flash`) + 이미지 `cogview-3-flash` + 비디오 `cogvideox-flash` (비디오는 일 5회 별도 제한). 한도: 무료 모델 호출 일 10회·분당 5회 (00:00 UTC+8 리셋), 카드·보증금·휴대폰 번호 불필요 (공식 FAQ 명시). 이메일 계정+API 키 필요, 18세 이상. 2026-10-24 아침 무료 모델 표기 명확화 (기존 "채팅 3종 + 이미지·비디오 2종" 미상세 → 5종 명칭 확정) — 등록 여부 형님 판단 대기 유지 (2026-10-23 신규 후보 — mvalentsev/awesome-free-ai-coding 2026-10-22 커밋에서 신규 등재 확인). (출처: https://aiapi-pro.com/free/index.html)

## 변경 이력

- 2026-10-30: OpenCode Zen — 저녁 워치(18:00 `/v1/models` API 직접 확인, 3회 확인 동일): 무료 8종→7종 — `jev-1.13-free`가 카탈로그에서 제거됨 (유료 변형도 카탈로그에 없음 — 완전 제거). `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종 중 `jev-1.13-free` 제외, `flint-40b-free` 편입 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-30: Nous Portal — 저녁 워치(18:00 공식 API 가격 $0 기준, 직접 확인, 재확인 동일): 무료 7종→6종 — 아침에 재등재됐던 `inclusionai/ling-3.1-flash:free`가 카탈로그에서 다시 제거됨 (유료 변형 `inclusionai/ling-3.1-flash`는 입력 $0.075/1M·출력 $0.225/1M 유지, 별개 ID — 당일 재등재→재제거). laguna 2종 expiration_date 2026-10-31 유지 (내일 만료). 대표 3종 전부 잔류 — 대표 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-30: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 재확인, 2회 동일 스냅샷, last_check 2026-10-30T09:01:58Z): tier-free 29종 유지. 아침 major_outage였던 `kimi-k2.7-code`가 operational로 복귀 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`). `rnj-1`은 operational→partial_outage로 전환 (아침 정상), `gemma3-270m:free`·`unmoderated-gpt`는 major_outage 유지. 대표 3종(`gpt-oss-20b`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-30: BazaarLink — 저녁 워치(18:00, 카탈로그 스냅샷 2026-10-30 07:39 UTC, 페이지 직접 확인): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-30 08 UTC 기준): `qwen/qwen3.7-flash` 96%→100%(23/23)로 상승, `deepseek/deepseek-v4-flash-0731free` 91%→96%(22/23)로 상승, 나머지 4종 100% 유지. 대표 2종 중 `qwen/qwen3.7-flash`는 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-30: 저녁 워치 — 위 4건 외 변동 없음: OpenRouter(`:free` 16종 유지, laguna 2종 만료일 2026-10-31·`dots-3-note-preview:free` 2026-12-31 유지 — 공개 API 직접 확인)·OrcaRouter($0 `-free` 7종 유지, orcacyber-minimax 포함 — pricing API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 텍스트 추출 확인, '2 models' 표기)·Groq(한도 동일 — gpt-oss-120b/20b·qwen3.8-27b 30 RPM / 1K RPD / 8K TPM / 200K TPD, safeguard 3 RPM — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, 가격표 Updated 2026-10-21 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인, 페이지 Updated 2026-10-30)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지, 문서 Updated 2026-07-29 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지 — 텍스트 추출 기준 20종 노출, 총수 변경 단정 불가, 라이브 재확인 필요)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보). NVIDIA NIM은 이번 저녁 텍스트 추출본이 2026-10-20 스냅샷(10일 전)이라 재확인으로 쓰지 못했고, AnyAPI는 텍스트 추출만으로 Free 뱃지·모델명 매핑이 안 돼 이번 저녁 라이브 재확인을 못 했으며, UnoRouter는 텍스트 추출 기준 Free 137로 노출됐으나 라이브 값과 달라 저녁 라이브 재확인 필요 — 이상 4곳은 2026-10-30 아침 확인 상태를 그대로 유지 (NVIDIA 45종·AnyAPI Free 5종·Ollama 클라우드 21종·UnoRouter 라이브 126). 확인 필요 후보 중 Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI는 이번 저녁에 개별 재확인하지 않았고 새로 확인된 변경 사항 없음. 신규 상시 무료 제공자 없음 — 웹 검색에서 새로 등장한 상시 무료 제공자는 확인되지 않았음 (3자 정리글에서 언급된 SambaNova·Cohere는 체험 크레딧 성격이라 상시 무료 범위 외).

- 2026-10-30: UnoRouter — 아침 워치 라이브 재확인 (06:13~06:15 KST): 라이브 기준 Free 122→126 (MODELS 254→258·PROVIDERS 41+→42+·PAID 132 유지, 126+132=258 일치) — 같은 아침 06:01~06:04 확인(122)에서 10여 분 만에 재반등, 분 단위 변동 지속. 나머지 5개 사이트(NVIDIA·Token Harbor·AnyAPI·BazaarLink·Ollama)는 재확인 값과 이전 확인 값이 동일 — 변경 없음. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-30: 뒤늦게 도착한 라이브 브라우저 확인 결과 반영 (06:01~06:04 KST, 아침 워치 마감 후 도착): NVIDIA NIM — Free Endpoint 필터 44종→45종 (1종 증가, 증가 모델 특정 불가 — 3자 자료의 `mistralai/mistral-large-4-1t-a52b` 무료 엔드포인트 추가 단서와 일치), 대표 4종 유지. AnyAPI — Free 티어 5종 유지 라이브 확정 (Qwen3.8 27B·Ling 3.0 Flash Sante·Ling 3.0 Flash Fin·Qwen2.5 Coder 32B·Gemma 3n 4B, 각 카드 Free 배지). Ollama Cloud — 클라우드 21종 유지 라이브 확정 (전수 스크롤 카운트, free 태그 `beam` 1종 유지). UnoRouter — 라이브 기준 Free 140→122 (MODELS 270→254·PROVIDERS 45+→41+·PAID 130→132, 122+132=254 일치), 분 단위 변동 지속 — 등록 여부 형님 판단 대기 유지. Token Harbor(Free 2종)·BazaarLink(무료 6종·동일 프로브 수치)는 라이브 결과와 아침 텍스트 추출 확인이 일치 — 변경 없음. 아침 워치 요약에 적었던 'NVIDIA·AnyAPI·UnoRouter 라이브 미확인' 3곳 중 AnyAPI·UnoRouter는 이번 라이브 결과로 해소, NVIDIA는 45종 증가로 갱신 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview, https://anyapi.ai/ai-models, https://ollama.com/search?c=cloud, https://unorouter.com/en).

- 2026-10-30: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인 + 재확인, 2회 동일 스냅샷): tier-free 29종 유지. `kimi-k2.7-code`가 major_outage로 전환 (2회 연속 확정) — 대표에서 제외, `gpt-oss-20b` 편입. `gemma3-270m:free`·`glm-4.7-flash`·`rnj-1`이 정상 복귀 — 현재 정상 6종 (`gpt-oss-20b`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`·`gemma3-270m:free`). `unmoderated-gpt`는 major_outage. 대표 3종(`gpt-oss-20b`·`mistral-large-4`·`llama-instant`)은 모두 정상. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-30: Nous Portal — 아침 워치(06:00 공식 API 가격 $0 기준, 직접 확인): 무료 6종→7종 — `inclusionai/ling-3.1-flash:free`가 카탈로그에 재등재됨 (가격 $0 확인 — 유료 변형 `inclusionai/ling-3.1-flash`는 입력 $0.075/1M·출력 $0.225/1M 유지, 별개 ID). laguna 2종 expiration_date 2026-10-31 유지 (내일 만료). 대표 3종 전부 잔류 — 대표 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-30: OrcaRouter — 아침 워치(06:00 pricing API 직접 확인): $0 `-free` 7종 유지이나 구성 변경 — `orca/orcacyber-glm-5.3-flash-free` 제거, `orca/orcacyber-minimax-m3.1-flash-free` 신규 등재 (model_price 0·is_free_tier true 확인, 단 locked·Security Research 티어 접근 제한 — 대표 편입 없음). 기존 6종 전부 잔류 — 대표 변경 없음 (출처: https://www.orcarouter.ai/api/pricing).

- 2026-10-30: BazaarLink — 아침 워치(06:00, 카탈로그 스냅샷 2026-10-29 17:46 UTC, 페이지 텍스트 추출 확인): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-29 20 UTC 기준): `deepseek/deepseek-v4-flash-0731free` 87%→91%(21/23)로 상승, `stealth/glyph-cluster` 100%(23/23) 유지, `qwen/qwen3.7-flash` 96%(22/23)·`reflection/beam` 96%(22/23) 유지, 나머지 2종 100% 유지. 대표 2종 중 `qwen/qwen3.7-flash`는 96% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-30: 아침 워치 — 위 4건 외 변동 없음: OpenRouter(`:free` 16종 유지, laguna 2종 만료일 2026-10-31·`dots-3-note-preview:free` 2026-12-31 유지 — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 텍스트 추출 확인, '2 models' 표기)·Groq(한도 동일 — gpt-oss-120b/20b·qwen3.8-27b 30 RPM / 1K RPD / 8K TPM / 200K TPD, safeguard 3 RPM — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, 가격표 Updated 2026-10-21 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지, 문서 Updated 2026-07-29 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지 — 텍스트 추출 기준 클라우드 20종 노출, gpt-oss 미노출은 기존 텍스트 추출 한계로 총수 변경 단정 불가, 저녁 라이브 재확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보). NVIDIA NIM은 이번 아침 텍스트 추출본이 2026-10-20 스냅샷(10일 전)이라 재확인으로 쓰지 못했고, AnyAPI는 텍스트 추출만으로 Free 뱃지·모델명 매핑이 안 돼 이번 아침 라이브 재확인을 못 했으며, UnoRouter는 텍스트 추출 기준 Free 126으로 노출됐으나 라이브 값과 달라 저녁 라이브 재확인 필요 — 이상 3곳은 2026-10-29 저녁 확인 상태를 그대로 유지. 확인 필요 후보 중 Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI는 이번 아침에 개별 재확인하지 않았고 새로 확인된 변경 사항 없음. 신규 상시 무료 제공자 없음 — 웹 검색에서 새로 등장한 상시 무료 제공자는 확인되지 않았음 (3자 자료에서 NVIDIA NIM 무료 엔드포인트에 `mistralai/mistral-large-4-1t-a52b` 추가 단서 포착 — 공식 페이지 라이브 확인 전이라 기준선 미반영, 저녁 워치에서 확인).

- 2026-10-29: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 재확인, 2회 동일 스냅샷, last_check 2026-10-29T09:01:09Z): tier-free 29종 유지. 아침 정상 5종→저녁 정상 4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). `rnj-1`이 operational→major_outage로 전환. `glm-4.7-flash`·`unmoderated-gpt`는 degraded, `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-29: BazaarLink — 저녁 워치(18:00, 카탈로그 스냅샷 2026-10-29 02:43 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-29 08 UTC 기준): `qwen/qwen3.7-flash` 100%→96%(22/23)로 하락, `reflection/beam` 100%→96%(22/23)로 하락, `deepseek/deepseek-v4-flash-0731free` 91%→87%(20/23)로 하락, 나머지 3종 100% 유지. 대표 2종 중 `qwen/qwen3.7-flash`는 96% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-29: 확인 필요 — UnoRouter 무료 표기 라이브 기준 143→140으로 3 감소 (MODELS 274→270·PROVIDERS 46+→45+·PAID 131→130, 140+130=270 일치, 라이브 브라우저 직접 확인). 아침 텍스트 추출 기준 Free 124는 라이브 값과 달라 저녁 라이브 값 140으로 기록. 분 단위 변동 지속 — 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-29: 저녁 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 16종 유지, laguna 2종 만료일 2026-10-31·`dots-3-note-preview:free` 2026-12-31 유지 — 공개 API 직접 확인)·OrcaRouter($0 `-free` 7종 유지, orcacyber 포함 — pricing API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 6종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(Free Endpoint 필터 44종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — gpt-oss-120b/20b·qwen3.8-27b 30 RPM / 1K RPD / 8K TPM / 200K TPD, safeguard 3 RPM — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, 가격표 Updated 2026-10-21 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지, 문서 Updated 2026-07-29 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 클라우드 21종 — 라이브 브라우저 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보). 확인 필요 후보 중 Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI는 이번 저녁에 개별 재확인하지 않았고 새로 확인된 변경 사항 없음. 신규 상시 무료 제공자 없음 — 웹 검색에서 새로 등장한 상시 무료 제공자는 확인되지 않았음 (Aion Labs는 3자 검증 목록에만 있고 자체 모델 전용·일일 크레딧 금액 미공개라 범위가 모호해 등록 보류, 형님 판단 대기).

- 2026-10-29: Nous Portal — 아침 워치(06:00 공식 API 가격 $0 기준, 직접 확인): 무료 7종→6종 — `meituan/longcat-2.0:free`가 카탈로그에서 제거됨 (유료 변형 `meituan/longcat-2.0`만 잔류 — 가격 $0 아님). 잔류 6종: `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`upstage/solar-mini4:free`·`stepfun/step-3.7-flash:free`·`reflection/beam-1.0-501b-a23b:free`·`ornith/ornith-1.5-122b:free`. laguna 2종 expiration_date 2026-10-31 유지 (2일 남음). 대표 3종 전부 잔류 — 대표 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-29: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인, last_check 2026-10-28T20:54:09Z): tier-free 29종 유지. 저녁 최종 정상 3종→아침 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). `rnj-1`이 major_outage→operational, `gpt-oss-20b`가 degraded→operational로 복귀. `glm-4.7-flash`·`unmoderated-gpt`는 degraded, `gemma3-270m:free`는 major_outage 유지. 대표 3종은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-29: BazaarLink — 아침 워치(06:00, 카탈로그 스냅샷 2026-10-28 18:33 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-28 20 UTC 기준): `stealth/glyph-cluster` 87%→100%(23/23)로 상승, `deepseek/deepseek-v4-flash-0731free` 96%→91%(21/23)로 하락, 나머지 4종 100% 유지. 대표 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-29: 아침 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 16종 유지, laguna 2종 만료일 2026-10-31·`dots-3-note-preview:free` 2026-12-31 유지 — 공개 API 직접 확인)·OrcaRouter($0 `-free` 7종 유지, orcacyber 포함 — pricing API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 텍스트 추출 기준 클라우드 20종 — 모델 검색 페이지 직접 확인)·Groq(한도 동일 — gpt-oss-120b/20b·qwen3.8-27b 30 RPM / 1K RPD / 8K TPM / 200K TPD, safeguard 3 RPM — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, 가격표 Updated 2026-10-21 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지, 문서 Updated 2026-07-29 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보). NVIDIA NIM은 이번 아침 텍스트 추출본이 2026-10-20 스냅샷(8일 전)이라 오늘 재확인으로 쓰지 않았고, AnyAPI는 텍스트 추출만으로 Free 뱃지 확인이 안 돼 이번 아침 라이브 재확인을 못 했으며, UnoRouter는 텍스트 추출 기준 Free 124로 노출됐으나 라이브 브라우저 기준과 달라 저녁 워치에서 라이브 재확인 필요 — 이상 3곳은 2026-10-28 저녁 확인 상태를 그대로 유지. 확인 필요 후보 중 Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI는 이번 아침에 개별 재확인하지 않았고 새로 확인된 변경 사항 없음. 신규 상시 무료 제공자 없음 — 웹 검색에서 새로 등장한 상시 무료 제공자는 확인되지 않았음 (AnonRouter는 3자 소개글만 있고 공식 무료 조건 미확인이라 후보 등록 보류, ReadyServer는 VPS 전제라 범위 외).

- 2026-10-28: NVIDIA NIM — 저녁 워치(18:00 라이브 브라우저 직접 확인): Free Endpoint 필터 45종→44종 (1종 감소, 제거 모델 특정 불가). 메인 'Free inference' 대표 무료 4종 유지 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview).

- 2026-10-28: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 재확인, 2회 연속 동일 스냅샷, last_check 2026-10-28T09:02:09Z): tier-free 29종 유지. 아침 정상 7종→저녁 최종 정상 3종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). 1차(08:58:09Z)에서는 정상 5종이었으나 수 분 만에 뒤집힘. `rnj-1`은 major_outage, `gpt-oss-20b`·`glm-4.7-flash`·`unmoderated-gpt`는 degraded, `gemma3-270m:free`는 major_outage 유지. 대표 3종은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-28: BazaarLink — 저녁 워치(18:00, 카탈로그 스냅샷 2026-10-28 08:10 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(샘플 23개, 2026-10-28 08 UTC 기준): `stealth/glyph-cluster` 75%→87%(20/23)로 상승, `deepseek/deepseek-v4-flash-0731free` 92%→96%(22/23)로 소폭 상승, 나머지 4종 100% 유지. 대표 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-28: Ollama Cloud — 저녁 워치(18:00 라이브 브라우저 직접 확인): 클라우드 모델 20종→21종 (전수 스크롤 카운트에 `gpt-oss` 포함 — 아침 누락 vs 신규 등재 구분 불가, 텍스트 추출에서는 20종만 노출). free 태그 `beam` 1종 유지, `minimax-m3.1-flash` 유료 표기 유지 (출처: https://ollama.com/search?c=cloud).

- 2026-10-28: 확인 필요 — UnoRouter 무료 표기 라이브 기준 125→143으로 18 증가 (MODELS 255→274·PROVIDERS 46+ 유지·PAID 130→131, 143+131=274 일치, 라이브 브라우저 직접 확인). 분 단위 변동 지속 — 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-28: 저녁 워치 — 위 5건 외 변동 없음: OpenRouter(`:free` 16종 유지, laguna 2종 만료일 2026-10-31·`dots-3-note-preview:free` 2026-12-31 유지 — 공개 API 직접 확인)·OrcaRouter($0 `-free` 7종 유지, orcacyber 포함 — pricing API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 7종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — gpt-oss-120b/20b·qwen3.8-27b 30 RPM / 1K RPD / 8K TPM / 200K TPD, safeguard 3 RPM — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, 가격표 Updated 2026-10-21 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지, 문서 Updated 2026-07-29 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보). 확인 필요 후보 중 Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI는 이번 저녁에 개별 재확인하지 않았고 새로 확인된 변경 사항 없음. 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 최신 커밋(2026-10-27T14:27Z)은 감사·재검증 성격으로 신규 제공자 추가 없음.

- 2026-10-28: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 17종→16종 — `nvidia/nemotron-3-super-120b-a12b:free`(기존 대표 #1)가 카탈로그에서 제거됨 (`:free` 없는 동명 모델만 잔류, 무새 직접 대조 재확인). 대표 변경: `dots-studio/dots-3-note-preview:free` #1 승격, `cohere/north-mini-code:free` #2 승격, `nvidia/nemotron-3-ultra-550b-a55b:free` #3 신규 편입. laguna 2종 만료일 표기 2026-10-31 유지 (3일 남음 — 항목 단위 재확인은 브라우저 뷰 한계로 불가) (출처: https://openrouter.ai/api/v1/models).

- 2026-10-28: OrcaRouter — 아침 워치(06:00 pricing API 직접 확인): $0 `-free` 6종→7종 — `orca/orcacyber-glm-5.3-flash-free` 신규 등재 (model_price 0·is_free_tier true 확인, 단 locked·Security Research 티어 접근 제한 — 대표 편입 없음). 기존 6종 전부 잔류 — 대표 변경 없음 (출처: https://www.orcarouter.ai/api/pricing).

- 2026-10-28: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인 + 재확인, 1차 last_check 2026-10-27T20:55:50Z, 2차 2026-10-27T21:17:50Z — 2회 연속 tier-free 29종 동일): tier-free 29종 유지. `rnj-1`이 major_outage→operational, `glm-4.7-flash`가 partial_outage→operational로 복귀 — 현재 정상 7종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`·`rnj-1`·`glm-4.7-flash`). `gpt-oss-20b`는 1차 degraded→2차 operational로 뒤집힘 (최종 정상). `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-28: BazaarLink — 아침 워치(06:00, 카탈로그 스냅샷 2026-10-27 17:46 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(샘플 24개, 2026-10-27 20 UTC 기준): `stealth/glyph-cluster` 78%→75%(18/24)로 하락, `deepseek/deepseek-v4-flash-0731free` 96%→92%(22/24)로 소폭 하락, 나머지 4종 100% 유지. 대표 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-28: Ollama Cloud — 아침 워치(06:00 라이브 브라우저 직접 확인): 클라우드 모델 21종→20종 (free 태그 `beam` 1종 유지, 제거된 1종 특정 불가). `minimax-m3.1-flash` 유료 표기 유지 (출처: https://ollama.com/search?c=cloud).

- 2026-10-28: 확인 필요 — UnoRouter 무료 표기 라이브 기준 140→125로 15 감소 (MODELS 271→255·PROVIDERS 48+→46+·PAID 131→130, 125+130=255 일치, 라이브 브라우저 직접 확인). 분 단위 변동 지속 — 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-28: 아침 워치 — 위 6건 외 변동 없음: OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 7종 유지 — 공식 API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(Free Endpoint 필터 45종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — Free Plan Limits 탭에서 gpt-oss-120b/20b·qwen3.8-27b 30 RPM / 1K RPD / 8K TPM / 200K TPD, safeguard 3 RPM 확인 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, Other Pricing 섹션 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 2026-10-27 커밋 2건은 감사·재검증 성격으로 신규 제공자 추가 없음.

- 2026-10-27: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 재확인, 2회 연속 동일, last_check 2026-10-27T08:57:41Z → 08:59:41Z): tier-free 29종 유지. `rnj-1`이 operational→major_outage, `glm-4.7-flash`가 operational→partial_outage로 전환 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`). `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-27: BazaarLink — 저녁 워치(18:00, 카탈로그 스냅샷 2026-10-27 05:19 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(2026-10-27 08 UTC, 샘플 23개): `stealth/glyph-cluster` 83%→78%(18/23)로 하락, `deepseek/deepseek-v4-flash-0731free` 100%→96%(22/23)로 소폭 하락, 나머지 4종 100% 유지. 대표 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-27: ZeroLimitAI — 저녁 워치(18:00 개발자 페이지 직접 확인): Free week($0 for 7 days·일 25회) 유지. 단, 유료 플랜 변경 — Lifetime 판매가 2026-10-26 종료 (기존 구매자 유지), Annual은 $99/년·일 2,000회 (기존 기준선 표기 $49/년·Lifetime $99 일회성을 정정). 무료 체험 조건 자체는 변동 없음 (출처: https://www.zerolimitai.com/developers).

- 2026-10-27: 확인 필요 — UnoRouter 무료 표기 라이브 기준 136→140으로 4 증가 (MODELS 267→271·PROVIDERS 44+→48+·PAID 131 유지, 140+131=271 일치, 라이브 브라우저 직접 확인). 분 단위 변동 지속 — 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-27: 저녁 워치 — 위 4건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31 — 4일 남음, `dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 7종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 가격 $0 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(Free Endpoint 필터 45종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — gpt-oss-120b/20b·qwen3.8-27b 30 RPM / 1K RPD / 8K TPM / 200K TPD, safeguard 3 RPM — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·Cline(무료 모델 API 경유 미지원 문구 유지, 문서 Updated 2026-07-29 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 클라우드 21종, minimax-m3.1-flash 유료 표기 유지 — 클라우드 모델 검색 페이지 라이브 브라우저 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 2026-10-27 08:49 KST 커밋(chore: expire model promotions)은 vast-10m-flash 프로모션 만료 정리로, 신규 제공자 추가 없음.

- 2026-10-27: Nous Portal — 아침 워치(06:00 공식 API 가격 $0 기준, 직접 확인, 재확인 동일): 무료 8종→7종 — `meituan/longcat-2.5-preview:free`가 카탈로그에서 제거됨 (유료 변형 `meituan/longcat-2.5-preview`도 없음 — 완전 제거). 잔류 7종: `poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`upstage/solar-mini4:free`·`meituan/longcat-2.0:free`·`stepfun/step-3.7-flash:free`·`reflection/beam-1.0-501b-a23b:free`·`ornith/ornith-1.5-122b:free`. laguna 2종 expiration_date 2026-10-31 유지 (4일 남음). 대표 3종은 전부 잔류 — 대표 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-27: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인 + 재확인, 2회 연속 동일, last_check 2026-10-26T20:56:21Z): tier-free 29종 유지. `rnj-1`이 major_outage→operational, `glm-4.7-flash`가 partial_outage→operational로 복귀 — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`). `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 degraded 유지. 대표 3종은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-27: BazaarLink — 아침 워치(06:00, 카탈로그 스냅샷 2026-10-26 18:56 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(2026-10-26 20 UTC, 샘플 24개): `stealth/glyph-cluster` 78%→83%(20/24)로 소폭 상승, 나머지 5종 100% 유지. 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-27: 아침 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31 — 4일 남음, `dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(Free Endpoint 필터 45종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지, 문서 Updated 2026-07-29 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, minimax-m3.1-flash 유료 표기 유지 — 클라우드 모델 검색 페이지 직접 확인). 신규 상시 무료 제공자 없음 — 웹 검색에서 집계 사이트에 언급된 AnonRouter·Onomeo·SambaNova·Cohere trial 등은 상시 무료·카드 불필요·OpenAI 호환 범위를 공식 페이지로 검증하지 못해 등록하지 않음.

- 2026-10-26: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 재확인, 2회 연속 동일, last_check 2026-10-26T09:00:02Z): tier-free 29종 유지. `rnj-1`이 operational→major_outage로 전환 — 현재 정상 4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). `glm-4.7-flash`는 degraded→partial_outage, `gemma3-270m:free`는 major_outage→degraded, `unmoderated-gpt`는 degraded 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-26: BazaarLink — 저녁 워치(18:00, 카탈로그 스냅샷 2026-10-26 04:05 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(2026-10-26 08 UTC, 샘플 23개): `stealth/glyph-cluster` 87%→78%(18/23)로 하락, 나머지 5종 100% 유지. 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-26: 확인 필요 — UnoRouter 무료 표기 라이브 기준 127→136으로 9 증가 (MODELS 257→267·PROVIDERS 42+→44+·PAID 130→131, 136+131=267 일치, 라이브 브라우저 직접 확인). 분 단위 변동 지속 — 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-26: 저녁 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31 — 5일 남음, `dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 8종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 가격 $0 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(Free Endpoint 필터 45종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, Free Plan Limits 탭에서 30 RPM / 1K RPD / 8K TPM / 200K TPD 확인 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 HTML 직접 추출 확인; 라이브 브라우저 변경 보고는 접힘 'Other Pricing' 섹션 누락 오인으로 확인됨)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지, 문서 Updated 2026-07-29 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 클라우드 21종, minimax-m3.1-flash 유료 표기 유지 — 클라우드 모델 검색 페이지 라이브 브라우저 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 2026-10-26 커밋은 검증 날짜 갱신뿐으로 신규 제공자 추가 없음.

- 2026-10-26: AnyAPI — 아침 워치 라이브 브라우저 확인 결과 뒤늦게 도착해 정정: Free 티어 4종→5종 — `Qwen2.5 Coder 32B Instruct (free)`가 목록에 복귀 (2026-10-22 제거 후 복귀). 5종 전부 Free 배지, 만료일 표시 없음. 대표 3종(Qwen3.8 27B·Ling 3.0 Flash Sante·Ling 3.0 Flash Fin)은 전부 잔류 — 대표 변경 없음. 워치 초기 보고에서는 라이브 결과 미반환으로 텍스트 추출(Free 3종 노출, Gemma 3n 텍스트 미노출)만으로 '변경 없음'으로 잘못 기록했으나, 라이브 확인 결과로 정정 (출처: https://anyapi.ai/ai-models).

- 2026-10-26: 확인 필요 — UnoRouter 무료 표기 라이브 기준 148→127로 21 감소 (MODELS 274→257·PROVIDERS 44+→42+·PAID 126→130, 127+130=257 일치, 라이브 브라우저 직접 확인). 같은 아침 텍스트 추출 기준 Free 128 (MODELS 258·PAID 130) — 라이브 기준 127로 기록, 분 단위 변동 지속. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-26: BazaarLink — 아침 워치(06:00, 카탈로그 스냅샷 2026-10-25 17:46 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(2026-10-25 20 UTC, 샘플 23개): `deepseek/deepseek-v4-flash-0731free` 96%→100%로 상승, `stealth/glyph-cluster` 83%→87%로 소폭 상승, 나머지 4종 100% 유지. 대표 2종은 모두 100% — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-26: 아침 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31 — 5일 남음, `dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 8종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 가격 $0 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 무료 카테고리 페이지 직접 확인)·NVIDIA NIM(Free Endpoint 필터 45종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(무료 모델 API 경유 미지원 문구 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 클라우드 21종 — 클라우드 모델 검색 페이지 라이브 브라우저 직접 확인)·Api.Airforce(tier-free 29종 유지, 정상 5종(`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`llama-instant`·`gpt-oss-20b`) 유지 — 공개 API 2회 연속 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 2026-10-25 저녁 이후 새 커밋 없음. ※ AnyAPI·UnoRouter 라이브 결과는 워치 마감 뒤 늦게 도착해 별도 항목으로 기록 (AnyAPI Free 5종 복귀, UnoRouter 라이브 Free 127). ※ BazaarLink 프로브 수치는 라이브 브라우저 보고(샘플 24개·glyph 88%)와 텍스트 추출 2회(샘플 23개·glyph 87%)가 달라, 2회 일치한 텍스트 추출 값을 기록하고 차이는 1개 샘플 수준이라 대표·목록 결론에는 영향 없음.

- 2026-10-25: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 재확인, 2회 연속 동일, last_check 2026-10-25T09:03:47Z): tier-free 29종 유지. `kimi-k2.7-code`가 major_outage→operational, `gpt-oss-20b`가 major_outage→operational로 복귀. 반면 `glm-4.7-flash`는 operational→degraded로 전환. `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 비정상 유지 (1차 degraded↔2차 partial_outage 변동) — 현재 정상 5종 (`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`llama-instant`·`gpt-oss-20b`). 대표에서 `glm-4.7-flash` 제외(degraded 확정), `kimi-k2.7-code` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-25: 확인 필요 — UnoRouter 무료 표기 라이브 기준 104→148로 44 증가 (MODELS 241→274·PROVIDERS 39+→44+·PAID 137→126, 148+126=274 일치, 라이브 브라우저 직접 확인). 분 단위 변동 지속 — 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-25: Cline — 저녁 워치 공식 문서 직접 확인: Cline API(OpenAI 호환 Chat Completions, `https://api.cline.bot/api/v1`) 문서가 존재하나, 무료 모델의 API 경유 사용은 여전히 미지원 (공식 무료 모델 문서 Updated 2026-07-29 명시: "Free model usage is not supported through the Cline API. Free models are only available in the Cline IDE Extension and CLI."). 기존 'API 미지원' 문구를 'API 존재하나 무료 모델 API 경유 불가'로 정정 — 연동 불가 분류 유지 (출처: https://docs.cline.bot/api/overview, https://docs.cline.bot/getting-started/free-models).

- 2026-10-25: 저녁 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31 — 6일 남음, `dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 8종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 가격 $0 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 4종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(Free Endpoint 필터 45종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 텍스트 추출에서 Flash 계열 Free of charge 확인, 라이브 렌더링에서는 개별 모델 행 미노출 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 클라우드 21종 — 클라우드 모델 검색 페이지 라이브 브라우저 직접 확인)·BazaarLink(무료 6종 유지, 카탈로그 스냅샷 2026-10-25 08:48 UTC — 무료 페이지 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 10/25 커밋 1건은 TLS 수정 성격이라 신규 제공자 추가 없음.

- 2026-10-25: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인 + 재확인, 1차 last_check 2026-10-24T20:54:03Z, 2차 20:57:03Z): tier-free 29종 유지. `kimi-k2.7-code`가 operational→major_outage, `gpt-oss-20b`가 degraded→major_outage로 악화. 반면 `glm-4.7-flash`는 degraded→operational로 정상 복귀. `rnj-1`·`llama-instant`·`mistral-large-4`는 operational 유지, `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 비정상 유지 (1차 partial_outage↔2차 degraded 변동) — 현재 정상 4종 (`glm-4.7-flash`·`mistral-large-4`·`rnj-1`·`llama-instant`). 대표에서 `kimi-k2.7-code` 제외(major_outage 확정), `glm-4.7-flash` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-25: BazaarLink — 아침 워치(06:00, 카탈로그 스냅샷 2026-10-24 17:46 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(2026-10-24 20 UTC, 샘플 24개): `deepseek/deepseek-v4-flash-0731free` 92%→96%로 소폭 상승, `stealth/glyph-cluster` 83% 유지, 나머지 4종 100% 유지. 대표 2종 중 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-25: 확인 필요 — UnoRouter 무료 표기 라이브 기준 119→104로 15 감소 (MODELS 255→241·PROVIDERS 43+→39+·PAID 136→137, 104+137=241 일치, 라이브 브라우저 직접 확인). 같은 아침 텍스트 추출 기준 Free 102 (MODELS 239) — 라이브 기준 104로 기록, 분 단위 변동 지속. 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-25: 아침 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31 — 6일 남음, `dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 8종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 가격 $0 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 4종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(Free Endpoint 필터 45종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, 가격표 Updated 2026-10-21 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 클라우드 21종 전수 확인, minimax-m3.1-flash 유료 표기 유지 — 클라우드 모델 검색 페이지 라이브 브라우저 직접 확인)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 10/24 커밋 6건은 유지보수 성격(검색 의미·테스트·Vercel 크레딧 범위·Aion/Beam offer 리뷰 갱신)이라 신규 제공자 추가 없음.

- 2026-10-24: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 재확인, 2회 연속 동일, last_check 2026-10-24T08:59:17Z): tier-free 29종 유지. `gpt-oss-20b`가 operational→degraded, `unmoderated-gpt`가 operational→degraded, `glm-4.7-flash`가 operational→degraded로 전환. 반면 `rnj-1`은 major_outage→operational, `llama-instant`은 partial_outage→operational로 복귀. `gemma3-270m:free`는 major_outage 유지 — 현재 정상 4종 (`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`llama-instant`). 대표에서 `glm-4.7-flash` 제외(degraded 확정), `llama-instant` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-24: BazaarLink — 저녁 워치(18:00, 카탈로그 스냅샷 2026-10-24 02:29 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(2026-10-24 08 UTC, 샘플 24개): `stealth/glyph-cluster` 91%→83%로 하락, `deepseek/deepseek-v4-flash-0731free` 96%→92% 소폭 하락, 나머지 4종 100% 유지. 대표 2종 중 `qwen/qwen3.7-flash`는 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-24: 확인 필요 — UnoRouter 무료 표기 저녁 확인에서 분 단위 변동: 라이브 브라우저 18:00 기준 Free 119 (MODELS 255·PROVIDERS 43+·PAID 136, 119+136=255 일치), 같은 저녁 텍스트 추출 기준 Free 121 (MODELS 257·PAID 136). 아침 Free 120에서 단일 수치로 고정되지 않고 119~121 구간에서 변동 — 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-24: 저녁 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31 — 7일 남음, `dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 8종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 가격 $0 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 4종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(Free Endpoint 필터 45종 유지, 대표 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 접힘 섹션 직접 확인 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 클라우드 21종 — 클라우드 모델 검색 페이지 직접 확인, minimax-m3.1-flash 유료 표기 유지)·SimpleLLM(무료 2종 유지, planned 2종 그대로 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 최신 커밋 2026-10-23T17:35Z 유지, 아침 워치 이후 새 커밋 없음.

- 2026-10-24: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인 + 재확인, 2회 연속 동일): tier-free 29종 유지. `glm-4.7-flash`가 degraded→operational로 정상 복귀. 반면 `rnj-1`은 operational→major_outage, `llama-instant`은 operational→partial_outage로 악화 (둘 다 재확인에서도 유지). `gemma3-270m:free`는 major_outage 유지 — 현재 정상 5종 (`gpt-oss-20b`·`mistral-large-4`·`unmoderated-gpt`·`kimi-k2.7-code`·`glm-4.7-flash`). 대표에서 `llama-instant` 제외(partial_outage 확정), `glm-4.7-flash` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-24: NVIDIA NIM — 아침 워치(06:00 라이브 브라우저 직접 확인): Free Endpoint 필터 43종→45종 (2종 증가). 메인 'Free inference' 대표 무료 4종 유지 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview).

- 2026-10-24: BazaarLink — 아침 워치(06:00, 카탈로그 스냅샷 2026-10-23 17:46 UTC): 무료 6종 유지 — 목록 변동 없음. 24h 프로브(2026-10-23 20 UTC): `stealth/glyph-cluster` 74%→91%로 개선, `reflection/beam` 100% 유지, `deepseek/deepseek-v4-flash-0731free`는 100%→96% 소폭 하락. 대표 2종은 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-24: 확인 필요 — NovAI 무료 모델 표기 명확화 (챗 3종 + 이미지 `cogview-3-flash` + 비디오 `cogvideox-flash`, 비디오는 일 5회 별도 제한). 한도·카드 불필요 조건은 동일 — 등록 여부 형님 판단 대기 유지 (출처: https://aiapi-pro.com/free/index.html).

- 2026-10-24: 아침 워치 — 위 4건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31 — 7일 남음, `dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 8종 유지, laguna 2종 expiration 2026-10-31 유지 — 공식 API 가격 $0 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지, 가격표 Updated 2026-10-22 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지, 3자 철회/신규 주장은 공식 문서에서 미확인 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, 가격표 Updated 2026-10-21 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·Ollama Cloud(free 태그 `beam` 1종 유지, 21종 동일 — 클라우드 모델 검색 페이지 직접 확인)·SimpleLLM(무료 2종 유지 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter(유지 — 확인 필요 후보). UnoRouter는 Free 120 유지 (MODELS 255·PROVIDERS 43+·PAID 135 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 2026-10-23T09:00Z(어제 저녁 워치) 이후 새 커밋 없음.

- 2026-10-23: Ollama Cloud — 저녁 워치(18:00 라이브 브라우저 직접 확인): `minimax-m3.1-flash` 기간 한정 무료 종료 확정 — 모델 상세 페이지 Cost 패널에서 'free until Oct 22, 2026 11:59 PM UTC' 무료 배지가 사라지고 정가(입력 $0.15·캐시 $0.015·출력 $0.60/1M) 표기로 유료 전환. free 태그는 `beam` 1종 유지 (클라우드 모델 21종 전수 확인). 기간 한정 요약표에서 minimax 행 정리 (출처: https://ollama.com/search?c=cloud).

- 2026-10-23: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인, 1차 18:03 / 2차 18:08 KST): tier-free 29종 유지. `glm-4.7-flash`가 operational→degraded로 전환, `rnj-1`은 1차 major_outage→2차 operational로 5분 만에 뒤집힘 (불안정). 반면 `gpt-oss-20b`는 degraded→operational로 복귀, `gemma3-270m:free`는 major_outage→degraded로 개선 — 2차 기준 정상 6종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`·`gpt-oss-20b`). 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-23: NVIDIA NIM — 저녁 워치(18:00 라이브 브라우저 직접 확인): Free Endpoint 필터 42종→43종 (필터 카운트 'Free Endpoint 43', 1종 증가). 메인 'Free inference' 대표 무료 4종(`nvidia/nemotron-3.5-super-vl-120b-a12b`·`deepseek-ai/deepseek-v4.1-flash`·`nvidia/nemotron-3.5-lightning-30b-a3b`·`nvidia/nemotron-3-ultra-550b-a55b`)은 유지 (출처: https://build.nvidia.com/models?filters=nimType%3Anim_type_preview).

- 2026-10-23: BazaarLink — 저녁 워치(18:00 무료 페이지 직접 확인, 스냅샷 2026-10-23 08 UTC, 페이지 HTML 직접 추출): 무료 6종 유지 (동일 ID) — 목록 변동 없음. 24h 프로브(샘플 23개): `reflection/beam` 96%→100%·`stealth/glyph-cluster` 61%→74%로 개선, 대표 2종(`qwen/qwen3.7-flash`·`deepseek/deepseek-v4-flash-0731free`)은 100% 유지 — 대표 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-23: 확인 필요 — UnoRouter 무료 표기 "Free 106"→"Free 120"으로 14 증가 (MODELS 241→254·PROVIDERS 40+→41+·PAID 135→134, 공식 홈페이지 텍스트 추출 직접 확인 — 분 단위 변동 중). 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-23: 저녁 워치 — 위 5건 외 변동 없음: OpenRouter(`:free` 17종 유지, 전원 prompt/output $0, 만료일 표기 유지 (laguna 2종 2026-10-31·`dots-3-note-preview:free` 2026-12-31) — 공개 API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·OpenCode Zen(무료 8종 유지, `big-pickle` 카탈로그 잔류 — `/v1/models` API 직접 확인)·Nous Portal(무료 8종 유지 — 공식 API 가격 $0 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지, 유료 인상 스케줄은 유료에만 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션, 가격표 Updated 2026-10-21 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days'·일 25회 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·SimpleLLM(무료 2종 유지 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting·AnyRouter·NovAI(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding 2026-10-22 이후 커밋은 1건(`3973cd53` chore: expire model promotions 2026-10-22 — LLMTR 만료 beam-1.0 프로모 제거)만으로 신규 제공자 추가 없음.

- 2026-10-23: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 18종→17종 — `minimax/minimax-m3.1-flash:free`가 카탈로그에서 제거됨 (공식 X 10/19 "72시간 무료" 프로모션 종료 확정). 기존 17종 전부 잔류, prompt/output $0 재확인. 만료일 표기 유지 (`dots-3-note-preview:free` 2026-12-31·laguna 2종 2026-10-31). 대표 3종 전부 잔류 — 대표 변경 없음. 기간 한정 요약표의 minimax 행은 만료 확정으로 정리 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-23: OpenCode Zen — 아침 워치(06:00 `/v1/models` API 직접 확인): 무료 9종→8종 — `minimax-m3.1-flash-free`가 카탈로그에서 제거됨 (MiniMax M3.1 Flash 기간 한정 무료 종료 — OpenRouter `:free`도 같은 날 제거). 기존 8종 전부 잔류. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종 전부 잔류 — 대표 변경 없음. Zen 무료 티어는 Hermes 외부 사용 불가라 형님 연결에는 영향 없음 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-23: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인, last_check 2026-10-22T20:53:32Z + 재확인 20:58:33Z — 2회 연속 동일): tier-free 29종 유지. `gpt-oss-20b`가 operational→degraded로 전환 — 현재 정상 6종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`·`rnj-1`·`unmoderated-gpt`). `gemma3-270m:free`는 major_outage 유지. 대표 3종(`kimi-k2.7-code`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-23: ZeroLimitAI — 아침 워치(라이브 브라우저 직접 확인): 무료 주간 일일 한도가 100회→25회로 축소 ("25 calls/day during the free week" — 개발자 페이지 FAQ 'What are the rate limits?' 명시). "Free week — $0 for 7 days" 표기는 유지. 상시 무료가 아닌 기간 한정 제공자라 우선순위 영향은 제한적 (출처: https://www.zerolimitai.com/developers).

- 2026-10-23: 확인 필요 — 신규 후보 NovAI 추가 (공식 확인, 형님 판단 대기): 홍콩 OpenAI 호환 게이트웨이 (`https://aiapi-pro.com/v1`). 공식 무료 페이지 "Free Chinese AI API — 5 models, 10 calls/day, no credit card" — 무료 채팅 모델 3종(`glm-4.7-flash`·`glm-4.6v-flash`·`glm-4.1v-thinking-flash`) + 이미지·비디오 모델 2종. 한도: 무료 모델 호출 일 10회·분당 5회 (00:00 UTC+8 리셋), 카드·보증금·휴대폰 번호 불필요 (공식 FAQ 명시). 이메일 계정+API 키 필요, 18세 이상. mvalentsev/awesome-free-ai-coding 2026-10-22 커밋에서 신규 등재 확인 후 공식 사이트 직접 검증 (출처: https://aiapi-pro.com/free/index.html).

- 2026-10-23: 확인 필요 — UnoRouter 무료 표기 "Free 113"→"Free 106"으로 7 감소 (MODELS 248→241·PROVIDERS 42+→40+·PAID 135 유지, 공식 홈페이지 라이브 브라우저 직접 확인 — 분 단위 변동 중). 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-23: 아침 워치 — 위 6건 외 변동 없음: LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지 — 공식 API 가격 $0 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·NVIDIA NIM(대표 무료 라인업 4종 유지, Free Endpoint 필터 42종 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 Free Tier 유지, 가격표 Updated 2026-10-22 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류, '27+' 공식 표기 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 가격표 HTML 직접 추출 확인; 라이브 브라우저에서는 접힘 섹션이라 누락으로 오인될 수 있음)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·BazaarLink(무료 6종 유지, 24h 프로브 갱신 — 무료 페이지 직접 확인)·Ollama Cloud(free 태그 `beam` 유지 — 클라우드 모델 검색 페이지 직접 확인; `minimax-m3.1-flash` 기간 한정 프로모션은 2026-10-23 08:59 KST 종료 예정 — 현재 06:00 기준 만료 전)·SimpleLLM(무료 2종 유지 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting(유지 — 확인 필요 후보). 신규 상시 무료 제공자 없음 (NovAI는 확인 필요 후보로 등록).

- 2026-10-22: OpenCode Zen — 저녁 워치(18:00 `/v1/models` API 직접 확인): 무료 10종→9종 — `longcat-2.5-preview-free`가 카탈로그에서 제거됨. 기존 9종 전부 잔류. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`)은 전부 잔류 — 대표 변경 없음. Zen 무료 티어는 Hermes 외부 사용 불가라 형님 연결에는 영향 없음 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-22: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인, last_check 2026-10-22T09:16:57Z, 재확인 09:20:06Z — 2회 연속 동일): tier-free 29종 유지. `glm-4.7-flash`가 major_outage→operational로 정상 복귀, `unmoderated-gpt`는 partial_outage→operational로 복귀, `gemma3-270m:free`는 major_outage→degraded로 개선 — 현재 정상 7종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`·`unmoderated-gpt`). 대표 3종은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-22: 기간 한정 무료 — OpenRouter `minimax/minimax-m3.1-flash:free` 행 추가: 공식 X 10/19 "72시간 무료" 공지 역산 기준 2026-10-22 21:00 KST경 종료 예정 (±몇 시간 오차 가능). 10/22 저녁 워치에서 prompt/output $0·expiration_date 표기 없음 확인 — 아직 무료 유지 중. 만료 여부는 내일 아침 워치에서 확인 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-22: Ollama Cloud — 저녁 워치(18:00 라이브 브라우저 직접 확인): free 태그는 `beam` 1개 유지, 클라우드 모델 21개 동일 — 목록 변동 없음. `minimax-m3.1-flash` 상세 페이지 Cost 패널에 "free until Oct 22, 2026 11:59 PM UTC"(= 2026-10-23 08:59 KST) 배지 표시 확인 — 프로모션 종료 시점이 공식 페이지에서 확인됨 (아침엔 목록 카드 정가 표기만, 상세 배지는 미확인). 만료(10/23 08:59 KST) 여부는 내일 아침 워치에서 확인 (출처: https://ollama.com/search?c=cloud).

- 2026-10-22: 확인 필요 — UnoRouter 무료 표기 "Free 110"→"Free 113"으로 3 증가 확인 (MODELS 245→248·PROVIDERS 39+→42+·PAID 135 유지, 공식 홈페이지 텍스트 추출 직접 확인 — 분 단위 변동 중). 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-22: 저녁 워치 — 위 5건 외 변동 없음: OpenRouter(`:free` 18종 유지, 전원 prompt/output $0, 만료일 표기 유지 — 공개 API 직접 확인)·LLM7.io(turbo 5종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 4종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·NVIDIA NIM(대표 무료 라인업 4종 유지·'kimi' 언급 없음, Free Endpoint 필터 42종 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 가격표 직접 확인)·AIHubMix(25종 유지, 대표 3종 잔류 — '27+' 공식 표기는 10/17부터 동일 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인; 유료 모델 Cached Input Storage 열 "Limited-time Free" 표기 유지, 무료 3종에는 없음)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·BazaarLink(무료 6종 유지, 24h 프로브 갱신 — 무료 페이지 직접 확인)·SimpleLLM(무료 2종 유지 — 공개 카탈로그 API 직접 확인, 확인 필요 후보)·Inferbase·IteraCompute·DreamPrompting(유지 — 확인 필요 후보; IteraCompute의 kimi-k3-free는 누적 $10+ 충전 시에만 $0라 카드 불필요 기준 미달). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding에 2026-10-22 새 커밋 없음.

- 2026-10-22: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 17종→18종 (prompt/output $0 직접 확인). `recursive/flint-v1.0:free` 신규 등재 — Recursive가 10/21 공개한 40B/2.5B MoE 오픈 웨이트 코딩 모델 (SWE-bench Pro v2 89.7% 자체 보고·Apache 2.0·262K 컨텍스트·도구 호출·추론 지원 — 출처: https://techcrunch.com/2026/10/21/recursive-launches-flint-a-laptop-coding-model-it-says-was-largely-built-by-ai/). 기존 17종 전부 잔류. 만료일 표기 유지 (`dots-3-note-preview:free` 2026-12-31·laguna 2종 2026-10-31). 대표 3종 전부 잔류 — 대표 변경 없음 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-22: OpenCode Zen — 아침 워치(06:00 `/v1/models` API 직접 확인): 무료 9종→10종 — `flint-40b-free` 신규 등재 (Recursive Flint의 Zen ID, 10/21 공개 — 위 TechCrunch 참조). 기존 9종 전부 잔류. `big-pickle`(스텔스) 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종 전부 잔류 — 대표 변경 없음. Zen 무료 티어는 Hermes 외부 사용 불가라 형님 연결에는 영향 없음 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-22: LLM7.io — 아침 워치(06:00 라이브 API 직접 확인): turbo(무료) 7종→5종 — `DeepSeek-V4-Flash-0731`(기존 대표 #1)·`GLM-5.3-Flash`(기존 대표 #2)가 카탈로그에서 완전 삭제됨 (동일 ID의 deepseek/glm-5.3 변형은 전부 `pro` 티어 — 유료 전환). 잔류 5종: `codestral-latest`·`gpt-oss:20b`·`minimax-m2.7`·`mistral-Nemo-Instruct-2407`·`nemotron-3-nano:30b`. 대표 변경: 잔류 유일 기존 대표 `gpt-oss:20b`를 #1으로 승격, `codestral-latest`(코딩 특화)·`minimax-m2.7`(180K·도구 호출·추론)을 #2·#3으로 편입 (대표 선정 기준: 에이전트 적합성 최우선 — 2026-10-14 형님 확립). 라인업이 뒤집히는 중이라 사용 전 재확인 권장 (출처: https://api.llm7.io/v1/models).

- 2026-10-22: AnyAPI — 아침 워치(06:00 라이브 브라우저 직접 확인, Tier 필터 Free): Free 티어 5종→4종 — `Qwen2.5 Coder 32B Instruct (free)`가 목록에서 제거됨 (Free 필터 상태 검색 'No items found.' — 제거 확인). 잔류 4종: Qwen3.8 27B (free), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Google Gemma 3n 4B (free). 대표 3종은 전부 잔류 — 대표 변경 없음 (출처: https://anyapi.ai/ai-models).

- 2026-10-22: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인 + 5분 간격 재확인, 2회 연속 동일): tier-free 29종 유지. `gpt-oss-20b`가 partial_outage→operational로 정상 복귀, `unmoderated-gpt`는 operational→partial_outage로 악화, `glm-4.7-flash`는 degraded→major_outage로 악화. `kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`은 operational 유지 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). 대표 3종은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-22: 아침 워치 — 위 5건 외 변동 없음: Nous Portal(무료 8종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·NVIDIA NIM(무료 라인업 4종 유지, 'kimi' 언급 없음, Free Endpoint 필터 42종 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 Free Tier 유지, 문서 Updated 2026-10-19 UTC — 가격표 직접 확인)·AIHubMix(25종 유지, 대표 3종 잔류 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인; 유료 모델 Cached Input Storage 열의 "Limited-time Free" 표기는 기준선 기록 없어 신규 여부 미확인 — 다음 워치 비교)·Agnes AI($0 프로모션 유지, 클라이언트 오류 없이 정상 로드 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·BazaarLink(무료 6종 유지, `stealth/glyph-cluster` 24h 프로브 52%→63% 개선 — 무료 페이지 직접 확인)·Ollama Cloud(free 태그 `beam` 유지·`minimax-m3.1-flash` 정가 등재 유지 — 클라우드 모델 검색 페이지 직접 확인; 기간 한정 프로모션은 2026-10-23 08:59 KST 종료 예정)·SimpleLLM(무료 2종 유지 — 공개 카탈로그 API 직접 확인, 확인 필요 후보; `planned` 2종은 enabled:false라 사용 불가 — 관찰 메모)·확인 필요 후보 UnoRouter(무료 표기 "Free 111"→"Free 110", MODELS 245·PROVIDERS 39+·PAID 135 — 라이브 브라우저 직접 확인; 등록 여부 형님 판단 대기 유지). 신규 상시 무료 제공자 없음 — awesome-free-ai-coding history에서 2026-10-21 이후 신규 added 이벤트 없음, ElectronHub·AMD Radeon Cloud·xKiro·Reka는 공식 확인 불가라 보류 유지.

- 2026-10-21: 확인 필요 — UnoRouter 무료 한도 수치 공개 확인 (공식 'Rate Limits & Errors' 문서, 2026-10-21 저녁 라이브 브라우저 직접 확인): 무료 모델당 사용자당 분당 1요청 (1 RPM per free model per user), 일부 무료 풀은 일일 토큰 예산 (UTC 자정 초기화) + TPM 캡 + 사용자당 병렬 요청 제한, 유료 모델은 UnoRouter 자체 제한 없음. Free 표기는 라이브 111·텍스트 추출 112로 분 단위 변동 중 (MODELS 246·PROVIDERS 42+·PAID 135) — 등록 여부 형님 판단 대기 유지 (출처: https://unorouter.com/en/docs/platform/errors-and-rate-limits).

- 2026-10-21: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 18:05 재확인, last_check 2026-10-21T09:02:39Z, 2회 연속 동일): tier-free 29종 유지. `gpt-oss-20b`가 operational→partial_outage로 전환, `glm-4.7-flash`는 operational→degraded로 전환. 반면 `kimi-k2.7-code`(major_outage→정상)·`unmoderated-gpt`(partial_outage→정상)는 복귀 — 현재 정상 4종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`). 대표에서 `gpt-oss-20b` 제외, `kimi-k2.7-code` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-21: 확인 필요 — UnoRouter 무료 표기 "Free 109"→"Free 112"로 3 증가 확인 (공식 홈페이지 텍스트 추출 직접 확인 — 같은 저녁 라이브 브라우저에서는 Free 111, 분 단위 변동 중; 자세한 변동 이력과 한도 공개는 위 항목 참조). 무료 한도(RPM/RPD) 수치 당시 미공개 상태였으나 이후 공식 문서 공개 확인 — 형님 판단 대기 유지 (출처: https://unorouter.com/en).

- 2026-10-21: 저녁 워치 — 위 2건 외 변동 없음: OpenRouter(`:free` 17종 유지, 만료일 표기 유지 — 공개 API 직접 확인)·LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenCode Zen(무료 9종 유지 — `/v1/models` API 직접 확인)·Nous Portal(무료 8종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지, `orcarouter/free` 별칭은 pricing 응답에 없어 미확인 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 텍스트 추출 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·Gemini(Flash 계열 Free Tier 유지, 유료 인상 스케줄은 유료에만 — 가격표 직접 확인)·AIHubMix(대표 3종 잔류 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인)·BazaarLink(무료 6종 유지, `stealth/glyph-cluster` 24h 프로브 38%→52% 개선 — 무료 페이지 직접 확인)·Ollama Cloud(free 태그 `beam` 유지·`minimax-m3.1-flash` 정가 등재 유지 — 클라우드 모델 검색 페이지 텍스트 추출 직접 확인; minimax-m3.1-flash 기간 한정 프로모션은 2026-10-23 08:59 KST 종료 예정)·SimpleLLM(무료 2종 유지 — 공개 카탈로그 API 직접 확인, 확인 필요 후보). AnyAPI(Free 5종 유지, `Google Gemma 3n 4B (free)` 포함 — 라이브 브라우저 직접 확인). NVIDIA NIM(무료 라인업 4종 유지·'kimi' 언급 없음, Free Endpoint 필터 42종 — 라이브 브라우저 직접 확인). 신규 상시 무료 제공자 없음 — 3자 카탈로그에서 ElectronHub·AMD Radeon Cloud·xKiro 언급 지속이나 공식 확인 불가라 보류 유지.

- 2026-10-21: Ollama Cloud — 재등록 (형님 결정 전환): 같은 날 '확인 필요'에서도 완전 제외했으나, 형님이 클라우드 모델 페이지(https://ollama.com/search?c=cloud)가 로그인 없이 열리고 모델별 가격·'free' 태그로 무료 여부를 특정할 수 있음을 직접 확인해 재등록으로 전환. 라이브 전수 확인 (2026-10-21 저녁): 클라우드 모델 21개 중 free 태그는 `beam` 1개뿐 (가격표 모델 목록에서도 beam만 누락 — 무료와 정합). 공식 블로그 확인: beam 기간 한정 무료 공지 (2026-10-16, 종료일 미공지), Free 플랜 starter 월간 사용량 (명단·금액 미공개). MiniMax M3.1 Flash 기간 한정 무료(공식 SNS 공지, 2026-10-23 08:59 KST 종료)도 기간 한정 요약표에 병기. 등록 범위는 공개 확인 가능한 free 태그 모델 + 공식 공지 프로모션으로 한정.

- 2026-10-21: Ollama Cloud — '확인 필요' 후보에서도 완전 제외 (형님 최종 결정): 모델 목록은 로그인을 해야만 확인 가능하고, 무료 모델 정보는 가입된 이메일로 일시적으로만 보내주는 방식이라 공개적으로 명확히 확인할 수 없음 — A안 3순위(확인 수단 자체가 없음) 적용. 2026-10-15 본 목록 제외에 이은 최종 정리로, 비공식 프로브 결과를 메모로 남기는 안도 함께 종결. '확인 필요' 후보 13건→12건. (출처: https://ollama.com/pricing)

- 2026-10-21: 무료 모델 확인 링크 전수 점검·정정 (형님 지시 — "명확하게 확인되는 페이지로 등록" 기준 적용): ① OpenRouter — 필터 없는 전체 목록(`https://openrouter.ai/models`)을 가격 $0 필터 적용 주소(`https://openrouter.ai/models?max_price=0`, 직접 열어도 필터 유지·전부 $0 표기 — 라이브 브라우저 확인)로 교체, 무료 전용 컬렉션 링크 병기. ② OpenCode Zen — 모델 목록이 없는 안내 페이지(`https://opencode.ai/zen`)를 공식 문서 'Free models' 섹션(`https://opencode.ai/v2/docs/console/models/#free-models`)으로 교체 (문서 목록과 API 카탈로그가 달라 집계는 API `-free` 기준 유지 — 2026-10-21 08:10 API 재확인 9종 동일). ③ Agnes AI — 홈페이지 주소를 공식 가격표(`https://agnes-ai.com/en/docs/pricing`, 두 모델 'Current price' 전부 $0 / M 확인)로 교체하고 '가격표'임을 명시 (무료 전용 페이지·필터는 없음). ④ Nous Portal — 모델 목록 페이지에 'Free Models' 섹션·FREE 필터가 있으나 필터 상태가 URL에 남지 않음을 명시하고 API 원본 링크 병기.

- 2026-10-21: Nous Portal — 무료 7종→8종: `ornith/ornith-1.5-122b:free` 신규 등재 (2026-10-21 08:10 공식 API 가격 $0 직접 확인, 웹 모델 목록의 FREE 8종과 일치). 대표 3종 변경 없음 (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-21: NVIDIA NIM — '더보기' 무료 모델 확인 링크 정정 (형님 제보): 기존 메인 주소 `https://build.nvidia.com`는 무료 목록으로 바로 가지 않아, 'Free Endpoint' 필터가 적용된 모델 목록 주소 `https://build.nvidia.com/models?filters=nimType%3Anim_type_preview`로 교체 (2026-10-21 라이브 브라우저 직접 확인 — 필터 적용 시 39종 표시·전 카드 'Free Endpoint' 배지, 직접 열어도 필터 유지됨). 메인 페이지 대표 무료 라인업 4종 표기는 별도 항목으로 분리해 유지.

- 2026-10-21: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인): tier-free 29종 유지. `kimi-k2.7-code`가 operational→major_outage로 전환, `unmoderated-gpt`는 operational→partial_outage로 전환. 반면 `glm-4.7-flash`(degraded→정상)·`rnj-1`(major_outage→정상)·`gpt-oss-20b`(degraded→정상)은 복귀, `gemma3-270m:free`는 major_outage→partial_outage로 완화 — 현재 정상 5종 (`gpt-oss-20b`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`·`rnj-1`). 대표 3종(`gpt-oss-20b`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-21: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 17종 유지 (전원 prompt/output $0 재확인). `thinkingmachines/inkling:free`·`inkling-small:free`의 expiration_date 표기가 사라짐 (10/20 기준 4종 모두 2026-10-31이었으나 laguna-s-2.1·laguna-xs-2.1 2종만 2026-10-31 유지) — 기간 한정 요약표 정정 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-21: BazaarLink — 아침 워치(무료 페이지 직접 확인, 스냅샷 2026-10-20 17:45 UTC): 무료 7종→6종 — 스냅샷에서 `stealth/cat-jam`이 목록에 없음. 24h 프로브: `qwen/qwen3.7-flash` 100%(24/24)·`deepseek/deepseek-v4-flash-0731free` 100%(24/24, 91%→회복)·`nvidia/nemotron-3.5-lightning-free` 100%(24/24)·`reflection/beam` 100%(24/24)·`reflection/beam-free` 100%(24/24)·`stealth/glyph-cluster` 38%(9/24). 대표 2종 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-21: 확인 필요 — UnoRouter 무료 표기 "Free 113"→"Free 109"로 4 감소 (MODELS 248→245·PROVIDERS 44+→40+·PAID 135→136, 공식 홈페이지 직접 확인). 무료 한도(RPM/RPD) 수치 여전히 미공개 — 형님 판단 대기 (출처: https://unorouter.com/en).

- 2026-10-21: 확인 필요 — 신규 후보 AnyRouter (공식 확인, 등록 기준 4개 전부 충족): 상시 무료 Free plan $0 (체험 아님·일일 캡 없음, 무료 모델 2400 req/min per key)·카드 불필요 (공식 FAQ "no card required")·OpenAI 호환 (`https://anyrouter.dev/api/v1/chat/completions`, `anyrouter/free` 자동 라우팅 + BYOK)·271모델·17개 제공자 게이트웨이. 유료 모델 호출 시 402 반환 (월 크레딧 없음). 등록 여부 형님 판단 대기 (출처: https://anyrouter.dev/blog/free-llm-api-for-students, https://anyrouter.dev/blog/anyrouter-pricing-free-vs-go).

- 2026-10-21: 아침 워치 — 위 5건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenCode Zen(무료 9종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 7종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지, `orcarouter/free` 별칭은 pricing 응답에 없어 미확인 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지, 'kimi' 언급 없음 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 Free Tier 유지 — 유료 티어 인상 스케줄(2026-12-01 플래그십·2027-01-01 Flash)은 유료에만, 무료 영향 없음 — 가격표 직접 확인)·AIHubMix(25종 유지, 대표 3종 잔류 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 Updated 2026-10-20 — 공식 가격 문서 직접 확인). 신규 상시 무료 제공자 없음 — ReadyServer LLM API(10/20 발표)는 VPS 전제라 범위 외 (출처: https://www.readyserver.sg/press/ready-server-launches-readyserver-llm-api/).

- 2026-10-20: Api.Airforce — 18:25 재확인: `gpt-oss-20b`이 degraded로 전환 — 현재 정상 4종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`). `glm-4.7-flash`도 degraded, `rnj-1`·`gemma3-270m:free`는 major_outage 유지. 대표에서 `gpt-oss-20b` 제외. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-20: 저녁 워치 — 위 4건 외 변동 없음: OpenRouter(`:free` 17종 동일 — 공개 API 직접 확인)·LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 7종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지, `orcarouter/free` 별칭은 pricing 응답에 없어 미확인 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일, "Developer plan의 기본 한도" 표기 유지 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지, 'kimi' 언급 없음 — 라이브 브라우저 직접 확인; lightning 표기가 `nemotron-3.5-lightning-30b-a3b`로 보임 — 실제 ID 변경은 미확인)·Gemini(Flash 계열 Free Tier 유지, 유료 티어 2027-01-01 인상 예고는 유료에만 — 가격표 직접 확인)·AIHubMix(25종 유지, 대표 3종 잔류 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 wiki 가격표 직접 확인, agnes-ai.com은 클라이언트 오류 유지)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 가격 문서 2026-10-20 업데이트 — 공식 가격 문서 직접 확인)·BazaarLink(무료 7종 유지, `qwen/qwen3.7-flash` 24h 프로브 100% (23/23)·`deepseek/deepseek-v4-flash-0731free` 91% (21/23), 나머지 5종 "Insufficient samples" 유지 — 무료 페이지 직접 확인). 신규 상시 무료 제공자 없음 — Inferbase·IteraCompute·SimpleLLM은 확인 필요 후보로 등록, 등록 여부는 형님 판단 대기.

- 2026-10-20: 확인 필요 — UnoRouter 무료 표기 "Free 107"→"Free 113"으로 6 증가 (MODELS 241→248·PROVIDERS 41+→44+·PAID 134→135, 공식 홈페이지 라이브 브라우저 직접 확인). 무료 한도(RPM/RPD) 수치 여전히 미공개 — 형님 판단 대기 (출처: https://unorouter.com/en).

- 2026-10-20: OpenCode Zen — 저녁 워치(18:00 `/v1/models` API 직접 확인): 무료 10종→9종 — `space-bunny-free`가 카탈로그에서 제거됨. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free`)은 전부 잔류 — 대표 변경 없음 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-20: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인): tier-free 29종 유지. `glm-4.7-flash`가 degraded로 전환 (06:25 정상), `gemma3-270m:free`·`rnj-1`은 major_outage 유지 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`). 대표 3종(`gpt-oss-20b`·`mistral-large-4`·`llama-instant`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-20: 확인 필요 — 신규 후보 3건 추가 (모두 공식 확인, 형님 판단 대기): Inferbase (영구 무료 Free $0·카드 불필요·OpenAI 호환, 월 5,000 requests + 일 100 managed requests/$0.50 — https://inferbase.ai/pricing), IteraCompute (`qwen/qwen3.8-27b` 무료·카드 불필요·OpenAI 호환, 월 30M tokens·TPM 160K — https://iteracompute.com/free/), SimpleLLM (무료 모델 2종·카드 불필요·OpenAI 호환, 독일 Stage One Solutions UG — https://simplellm.eu/docs/models.md). DreamPrompting은 공식 홈페이지 라우트 테이블 공개 확인 (13개 제공자 live + 14개 예정) — 형님 판단 대기 유지.

- 2026-10-20: Api.Airforce — 06:25 재확인: `glm-4.7-flash` 정상 확인 (06:00의 major_outage는 일시적 뒤집힘) — 현재 정상 7종 (`glm-4.7-flash`·`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`). 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-20: Nous Portal — 아침 워치(06:00 공식 API 라이브 확인): 무료 8종→7종 — `stepfun/step-5-preview:free`가 카탈로그에서 제거됨 (유료 변형 `step-5-preview`만 잔류). 잔류 7종: `meituan/longcat-2.0:free`·`meituan/longcat-2.5-preview:free`·`poolside/laguna-s-2.1:free`·`poolside/laguna-xs-2.1:free`·`reflection/beam-1.0-501b-a23b:free`·`stepfun/step-3.7-flash:free`·`upstage/solar-mini4:free`. 대표에서 `step-5-preview:free` 제외, `step-3.7-flash:free` 편입. `stealth/missingno`는 카탈로그에 없음 (10/17 제거 유지) (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-20: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 19종→17종 (prompt/output $0 직접 확인). `minimax/minimax-m3.1-flash:free` 신규 등재. `google/lyria-3-clip-preview`·`google/lyria-3-pro-preview`(오디오 계열 — 곡당 과금이라 실질 무료 아님)는 집계 제외, `openrouter/free` 자동 라우팅 별칭도 모델 집계에서 제외. 기존 16종 전부 잔류 — 대표 3종(`nvidia/nemotron-3-super-120b-a12b:free`·`dots-studio/dots-3-note-preview:free`·`cohere/north-mini-code:free`) 변경 없음. ※ `laguna-s-2.1`·`laguna-xs-2.1`·`inkling`·`inkling-small` :free 4종은 expiration_date 2026-10-31 — 만료 전후 유료 전환·제거 여부 확인 필요 (기간 한정 요약표에 행 추가), `dots-3-note-preview:free`는 2026-12-31 만료 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-20: OpenCode Zen — 아침 워치(06:00 `/v1/models` API 직접 확인): 무료 9종→10종 — `minimax-m3.1-flash-free` 신규 등재 (기존 9종 잔류 — 대표 변경 없음). `big-pickle`(스텔스)이 카탈로그에 재등장 (10/15 제거 후 복귀, `-free` 접미사 없음 — 무료 집계 제외) (출처: https://opencode.ai/zen/v1/models).

- 2026-10-20: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인, last_check 2026-10-19T20:57:20Z): tier-free 29종 유지. `glm-4.7-flash`가 operational→major_outage로 전환. `gpt-oss-20b`·`llama-instant`·`mistral-large-4`는 operational 확인. `kimi-k2.7-code`·`unmoderated-gpt`·`gemma3-270m:free`·`rnj-1`은 JSON 잘림으로 상태 미확인 (카탈로그 존재는 확인). 대표에서 `kimi-k2.7-code` 제외, `llama-instant` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-20: BazaarLink — 아침 워치(무료 페이지 직접 확인, 스냅샷 2026-10-19 17:44 UTC): 무료 2종→7종 — `stealth/glyph-cluster`·`stealth/cat-jam`·`reflection/beam`·`nvidia/nemotron-3.5-lightning-free`·`reflection/beam-free` 신규 등재 (5종 모두 24h 프로브 "Insufficient samples" — 실측 전 사용 주의). `qwen/qwen3.7-flash` 24h 프로브 100% (24/24), `deepseek/deepseek-v4-flash-0731free` 91%→92% (22/24). 대표 2종 변경 없음 (출처: https://bazaarlink.ai/free).

- 2026-10-20: Groq — 아침 워치(공식 한도 문서 직접 확인): 문서에서 "free" 문구가 사라지고 "Developer plan의 기본 한도" 표기로 변경 — gpt-oss-120b/20b·qwen3.8-27b = 30 RPM/1K RPD/8K TPM/200K TPD, gpt-oss-safeguard-20b = 3 RPM/1K RPD/2K TPM/200K TPD — 수치 동일. 실제 무료 정책 폐지인지는 텍스트만으로 확정 불가 — 관찰 유지 (출처: https://console.groq.com/docs/rate-limits).

- 2026-10-20: 확인 필요 — DreamPrompting 신규 후보: 공식 가격 페이지 직접 확인 — 무료 플랜 (카드·구독 불필요), OpenAI 호환 `https://dreamprompting.com/api/v1`, 한도 IP당 100 RPM + 계정당 24h 롤링 5,000 요청/500,000 토큰. 자체 모델 없이 27개 업스트림 제공자 무료 티어로 라우팅하는 게이트웨이 (공유 할당량 방식). 런칭일 미공개라 "지난 24시간 내 등장" 확정 아님 — 등록 여부 형님 판단 대기 (출처: https://dreamprompting.com).

- 2026-10-20: 확인 필요 — UnoRouter 무료 표기 "Free 120"→"Free 107"로 13 감소 (MODELS 253→241·PROVIDERS 44+→41+·PAID 133→134, 공식 홈페이지 라이브 브라우저 직접 확인). 무료 한도(RPM/RPD) 수치 여전히 미공개 — 형님 판단 대기 (출처: https://unorouter.com/en).

- 2026-10-20: 아침 워치 — 위 8건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OrcaRouter($0 `-free` 6종 유지, `orcarouter/free` 별칭은 pricing 응답에 없어 미확인 — 라이브 API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·NVIDIA NIM(무료 4종 유지, 'kimi' 언급 없음 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 Free Tier 유지, 유료 티어 2027-01-01 인상 예고는 유료에만 — 가격표 직접 확인)·AIHubMix(25종 유지, 대표 3종 잔류 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 2026-10-19 업데이트 — 공식 가격 문서 직접 확인). 신규 상시 무료 제공자 없음 — DreamPrompting은 확인 필요 후보로 등록, 등록 여부는 형님 판단 대기.

- 2026-10-19: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인, last_check 2026-10-19T08:59:33Z): tier-free 29종 유지. `rnj-1`·`glm-4.7-flash`·`gemma3-270m:free`가 major_outage로 전환, `llama-instant`이 정상 복귀 — 당시 정상 5종. 18:04 재확인(last_check 2026-10-19T09:04:33Z)에서 `glm-4.7-flash`가 5분 만에 major_outage→operational로 복귀 — 최종 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`·`unmoderated-gpt`), `gemma3-270m:free`·`rnj-1`은 major_outage 유지. 대표에서 `glm-4.7-flash` 제외, `kimi-k2.7-code` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-19: 확인 필요 — UnoRouter 무료 모델 표기 "Free 113"→"Free 120"으로 7 증가 (공식 홈페이지 라이브 브라우저 직접 확인 — MODELS 253·PROVIDERS 44+·PAID 133 함께 표기). 무료 한도(RPM/RPD) 수치 여전히 미공개 — 형님 판단 대기 (출처: https://unorouter.com/en).

- 2026-10-19: BazaarLink — 저녁 워치(무료 페이지 직접 확인): 무료 2종 유지. `deepseek/deepseek-v4-flash-0731free` 24h 프로브 79%→91%(21/23) 회복, `qwen/qwen3.7-flash` 100% 유지 (출처: https://bazaarlink.ai/free).

- 2026-10-19: 저녁 워치 — 위 3건 외 변동 없음: OpenRouter($0 모델 19종 유지, 대표 3종 잔류 — 공개 API 직접 확인)·LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenCode Zen(무료 9종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, 구성 동일 — 라이브 API 직접 확인)·OrcaRouter(무료 7종 유지, pricing API 기준 6개 `-free` ID $0 + `orcarouter/free` 별칭 — 라이브 API 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지, 'kimi' 언급 없음 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 무료 등급 유지 — 가격표 직접 확인)·AIHubMix(25종 유지, 대표 3종 잔류 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션 — 공식 가격표 직접 확인)·Agnes AI($0 프로모션 유지 — 3자 10/19 검증, 공식 홈페이지 텍스트 추출 실패)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지, 문서 2026-10-15 업데이트 — 공식 가격 문서 직접 확인). 신규 상시 무료 제공자 없음.

- 2026-10-19: Api.Airforce — 06:20 재확인: `kimi-k2.7-code`·`gemma3-270m:free` 모두 정상 — 현재 정상 7종 (`gemma3-270m:free`·`glm-4.7-flash`·`gpt-oss-20b`·`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`). 06:00의 major_outage는 일시적 뒤집힘 (출처: https://api.airforce/v1/models).

- 2026-10-19: 아침 워치 — 위 3건 외 변동 없음: LLM7.io(turbo 7종 유지 — 첫 시도 502 후 재시도 성공, 라이브 API 직접 확인)·OpenCode Zen(무료 9종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, 구성 동일 — 라이브 API 직접 확인)·OrcaRouter(무료 7종 유지, `orcarouter/free` 별칭 포함 — 라이브 브라우저 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지, 'kimi' 언급 없음 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 무료 등급 유지, 가격표 2026-10-16 UTC — 가격표 직접 확인)·AIHubMix(25종 유지, 대표 3종 잔류 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션 — 공식 가격표 직접 확인)·BazaarLink(무료 2종 유지, `deepseek/deepseek-v4-flash-0731free` 24h 프로브 83%→79% 소폭 하락 — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인)·Cloudflare Workers AI(무료 10,000 Neurons/day 표기 유지 — 공식 가격 문서 직접 확인). 신규 상시 무료 제공자 없음 — ElectronHub·AMD Radeon Cloud·Reka는 3자 언급만으로 공식 확인 불가라 보류.

- 2026-10-19: 확인 필요 — UnoRouter 무료 모델 표기 "Free 114"→"Free 113"로 1 감소 (공식 홈페이지 직접 확인). 무료 한도(RPM/RPD) 수치 여전히 미공개 — 형님 판단 대기 (출처: https://unorouter.com/en).

- 2026-10-19: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인): tier-free 29종 유지. `kimi-k2.7-code`가 operational→major_outage로 전환 — 현재 정상 7종 (`gemma3-270m:free`·`glm-4.7-flash`·`gpt-oss-20b`·`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`). 06:20 재확인에서 `kimi-k2.7-code`·`gemma3-270m:free` 모두 정상 확인 — 06:00의 major_outage 판정은 일시적 뒤집힘. 대표에 `kimi-k2.7-code` 복귀. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-19: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 16종→19종 (prompt/output $0 직접 확인). 신규 3종: `google/lyria-3-clip-preview`·`google/lyria-3-pro-preview`(오디오 계열 — 채팅 용도 아님)·`openrouter/free`(자동 라우팅 별칭). 기존 16종 전부 잔류 — 대표 3종(`nemotron-3-super-120b-a12b:free`·`dots-3-note-preview:free`·`cohere/north-mini-code:free`) 변경 없음 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-18: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인, last_check 2026-10-18T09:00:09Z + 재확인, 동일): tier-free 29종 유지. `llama-instant`이 operational→degraded로 전환 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`). `glm-4.7-flash`·`gemma3-270m:free`는 major_outage→degraded로 개선. 대표에서 `llama-instant` 제외, `gpt-oss-20b` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-18: 확인 필요 — UnoRouter 무료 모델 표기 "Free 104"→"Free 114"로 증가 (공식 홈페이지 직접 확인). 무료 한도(RPM/RPD) 수치 여전히 미공개 — 형님 판단 대기 (출처: https://unorouter.com/en).

- 2026-10-18: 저녁 워치 — 위 2건 외 변동 없음: OpenRouter(`:free` 16종 유지, 대표 3종 잔류 — 공개 API 직접 확인)·LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenCode Zen(무료 9종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, 구성 동일 — 라이브 API 직접 확인)·OrcaRouter(무료 7종 유지, `orcarouter/free` 별칭 포함 — 라이브 브라우저 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지, 'kimi' 언급 없음 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 무료 등급 유지 — 가격표 직접 확인)·AIHubMix(25종 유지, 대표 3종 잔류 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션 — 공식 가격표 직접 확인)·BazaarLink(무료 2종 유지, `deepseek/deepseek-v4-flash-0731free` 24h 프로브 88%→83% 소폭 하락 — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지 — 3자 10/16 검증)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인). 신규 상시 무료 제공자 없음.

- 2026-10-18: OrcaRouter — 아침 워치(라이브 브라우저 직접 확인): 무료 5종→7종 — `deepseek/deepseek-v4.1-flash-free` 신규 등재 (V4 Flash의 production successor, 1M 컨텍스트·비전·도구 호출 지원), `orcarouter/free` 자동 라우팅 별칭이 목록에 포함. 기존 5종 전부 잔류 — 대표 3종 변경 없음. ※ 텍스트 추출만으로는 3종까지만 보여 false negative였음 — 라이브 브라우저에서 7종 전부 확인 (출처: https://www.orcarouter.ai/models?price=free, https://www.orcarouter.ai/api/pricing).

- 2026-10-18: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인 + 재확인): tier-free 29종 유지. `unmoderated-gpt`가 partial_outage→operational로 복귀 (재확인에서도 유지) — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`unmoderated-gpt`). `glm-4.7-flash`는 operational→major_outage로 재전환, `gemma3-270m:free`는 major_outage 유지. 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-18: 확인 필요 — UnoRouter 무료 모델 표기 "Free 92"→"Free 104"로 증가 (공식 홈페이지 직접 확인). 무료 한도(RPM/RPD) 수치 여전히 미공개 — 형님 판단 대기 (출처: https://unorouter.com/en).

- 2026-10-18: 아침 워치 — 위 3건 외 변동 없음: OpenRouter(`:free` 16종 유지, 대표 3종 잔류 — 라이브 API 직접 확인)·LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenCode Zen(무료 9종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지 — 라이브 API 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·Token Harbor(Free 2종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지, 'kimi' 언급 없음 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 무료 등급 유지 — 가격표 직접 확인)·AIHubMix(25종 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·BazaarLink(무료 2종 유지, `deepseek-v4-flash-0731free` 24h 프로브 74%→88% 회복 — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지 — 3자 10/15 검증)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인). 신규 상시 무료 제공자 없음 — ElectronHub는 3자 블로그 언급만으로 공식 확인 불가라 보류 (조사 원칙: 확실한 정보만).

- 2026-10-17: Api.Airforce — 18:20 재확인: `glm-4.7-flash`가 partial_outage→정상 복귀 — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`). `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 partial_outage (출처: https://api.airforce/v1/models).

- 2026-10-17: 저녁 워치 — 위 4건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenRouter(`:free` 16종 유지, 대표 3종 잔류 — 라이브 API 직접 확인)·OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — `deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`, 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지, 'kimi' 언급 없음 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 무료 등급 유지, 가격표 2026-10-16 UTC 업데이트 — 가격표 직접 확인)·Z.ai(Flash 3종 Free 유지, "Other Pricing" 섹션 — 공식 가격표 직접 확인)·BazaarLink(무료 2종 유지, `deepseek/deepseek-v4-flash-0731free` 24h 프로브 100%→74% 저하 — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지, 공식 Docs 모델 가격표에서 agnes-2.5/3.0-flash 모두 Current price $0 직접 확인 — 사이트 정상 로드)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인). AIHubMix는 대표 3종 유지이나 본문 '27+ models' 주장과 달리 실제 나열 고유 모델은 25종 확인 — 더보기 표기 정정 (무료 모델 문서 직접 확인).

- 2026-10-17: 확인 필요 — UnoRouter 신규 후보 추가: OpenAI 호환 (`/v1/chat/completions`, "Any OpenAI-compatible client", 모델 페이지 Tools/Reasoning 태그 — 모델별 상이), 공식 홈페이지 "Free 92, No cost"·모델별 입·출력 $0.00/1M, 카드 불필요 ("No credit card needed to start"). 무료 한도(RPM/RPD) 수치 미공개 — 추가 확인 필요, 형님 판단 대기 (출처: https://unorouter.com/en, https://unorouter.com/en/models/liquid/lfm-2.5-2.6b:free).

- 2026-10-17: Nous Portal — 저녁 워치(18:00 공식 API 라이브 확인 + 재확인): 무료 8종 유지이나 구성 변경 — `stealth/missingno`가 카탈로그에서 제거됨 (10/11 등재 후 6일 만에 종료), `reflection/beam-1.0-501b-a23b:free` 신규 등재. 대표 3종 변경: `stepfun/step-5-preview:free`·`poolside/laguna-s-2.1:free`·`reflection/beam-1.0-501b-a23b:free` (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-17: OpenCode Zen — 저녁 워치(18:00 `/v1/models` API 직접 확인 + 재확인): 무료 12종→9종 — `ll-alpha-free`(10/16 저녁 신규 스텔스, 하루 만에 제거)·`muse-spark-1.2-contributor-free`·`muse-spark-1.3-contributor-free`가 카탈로그에서 제거됨. `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종 변경: `deepseek-v4.1-flash-free`·`glm-5.3-flash-free`·`jev-1.13-free` (출처: https://opencode.ai/zen/v1/models).

- 2026-10-17: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인, last_check 2026-10-17T08:58:46Z): tier-free 29종 유지. `gemma3-270m:free`가 정상→major_outage로 전환, `glm-4.7-flash`는 partial_outage, `unmoderated-gpt`는 partial_outage — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-17: Api.Airforce — 06:20 재확인: `glm-4.7-flash`가 정상→degraded로 전환 — 현재 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`gemma3-270m:free`). `unmoderated-gpt`는 partial_outage 유지 (출처: https://api.airforce/v1/models).

- 2026-10-17: AnyAPI — 아침 워치(06:00 라이브 브라우저 직접 확인, Tier 필터 Free): Free 티어 5종 유지 (전일 동일 — Qwen3.8 27B·Ling 3.0 Flash Sante·Ling 3.0 Flash Fin·Qwen2.5 Coder 32B Instruct·Google Gemma 3n 4B, 각 카드 "Free" 배지 확인). 브라우저 handoff가 지연돼 한 번 더 확인 후 반영 — 대표 변경 없음 (출처: https://anyapi.ai/ai-models).

- 2026-10-17: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인, last_check 2026-10-16T20:56Z): tier-free 29종 유지. `rnj-1`이 major_outage→정상 복귀, `gemma3-270m:free`도 major_outage→정상 복귀 — 현재 정상 7종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`·`rnj-1`·`gemma3-270m:free`). `unmoderated-gpt`는 degraded→partial_outage (여전히 비정상). 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`)은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-17: OpenCode Zen — 아침 워치(06:00 `/v1/models` API 직접 확인): 무료 12종 유지이나 구성 변경 — `cat-jam-free`가 카탈로그에서 제거되고 `beam-free`가 신규 등재 (정체 미공개). `big-pickle`(스텔스)은 카탈로그 잔류 (`-free` 접미사 없음 — 무료 집계 제외). 대표 3종(`muse-spark-1.3-contributor-free`·`jev-1.13-free`·`deepseek-v4.1-flash-free`) 전부 잔류 — 대표 변경 없음 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-17: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 15종→16종 — `xingchen-agi/xing4.0-29b-a4b:free` 신규 등재 (China Telecom TeleAI의 29B MoE 오픈 웨이트 모델, 262K 컨텍스트, prompt/output $0 직접 확인). 대표 3종 전부 잔류 — 대표 변경 없음 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-17: 아침 워치 — 위 3건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, `stealth/missingno` 포함 — 라이브 API 직접 확인)·OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·Token Harbor(Free 2종 유지 — 텍스트 추출 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지 — 라이브 브라우저 직접 확인)·Gemini(Flash 계열 API 무료 티어 유지 — 가격표 직접 확인)·AIHubMix(27+ 무료 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·BazaarLink(무료 2종 유지 — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지 — 3자 10/12 검증)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인). AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인). 신규 상시 무료 제공자 없음.

- 2026-10-16: Api.Airforce — 18:20 재확인: `gemma3-270m:free`가 정상→major_outage로 다시 전환 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`). `rnj-1`은 major_outage 유지, `unmoderated-gpt`는 degraded (출처: https://api.airforce/v1/models).

- 2026-10-16: OpenCode Zen — 저녁 워치(18:00 `/v1/models` API 직접 확인): 무료 11종→12종. `step-5-preview-free`가 카탈로그에서 제거됨 (대표 #1이었음 — 대표에서 제외, `deepseek-v4.1-flash-free`로 교체). `ll-alpha-free`(신규 스텔스 모델 — [공식 설명](https://opencode.ai/v2/docs/console/models/) "LL Alpha Free is a stealth model that's free on OpenCode for a limited time")·`glm-5.3-flash-free` 신규 등재. `big-pickle`(스텔스)이 카탈로그에 재등장 (10/15 아침 제거 후 복귀, `-free` 접미사 없음 — 무료 집계 제외). 대표 3종: `muse-spark-1.3-contributor-free`·`jev-1.13-free`·`deepseek-v4.1-flash-free` (출처: https://opencode.ai/zen/v1/models).

- 2026-10-16: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인, last_check 18:02 KST): tier-free 29종 유지. `rnj-1`이 정상→major_outage로 전환, `gemma3-270m:free`가 major_outage→정상 복귀 — 정상 6종 유지 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`glm-4.7-flash`·`gemma3-270m:free`). `unmoderated-gpt`는 major_outage→partial_outage로 개선. 대표 3종 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-16: 저녁 워치 — 위 2건 외 직접 확인분 변동 없음: Token Harbor(Free 2종 유지 — `deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`, 라이브 브라우저 직접 확인)·NVIDIA NIM(무료 4종 유지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenRouter(`:free` 15종 유지, 대표 3종 잔류 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, `stealth/missingno` $0 확인 — 라이브 API 직접 확인)·OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·Gemini(API 무료 티어 유지 — 가격표 직접 확인)·AIHubMix(27+ 무료 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·BazaarLink(무료 2종 유지 — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 가격표 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인). 신규 상시 무료 제공자 없음.

- 2026-10-16: Token Harbor — 아침 워치(06:00 라이브 브라우저 직접 확인): `claude-haiku-5.5:free` 무료 만료 확인 (종료일 2026-10-15 22:00 KST 경과) — Free 카테고리에서 제외, Value(유료 $0.10/$0.50)로 전환. 무료 3종→2종 (`deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free` 잔류). 대표에서 `claude-haiku-5.5:free` 제외 — 기간 한정 프로모 종료 (출처: https://tokenharbor.ai/models?category=free).

- 2026-10-16: NVIDIA NIM — 아침 워치(build.nvidia.com 텍스트 추출 + 라이브 브라우저 재확인): 무료 라인업 4종 유지이나 구성 교체 — `moonshotai/kimi-k3`이 `nvidia/nemotron-3.5-super-vl-120b-a12b`(멀티모달 VL MoE)로 교체됨 (페이지 전체에 'kimi' 언급 없음). 대표 모델에서 `kimi-k3` 제외, `nemotron-3.5-super-vl-120b-a12b` 편입 (출처: https://build.nvidia.com).

- 2026-10-16: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 14종→15종 (프롬프트/출력 전부 $0). 대표 3종(`nemotron-3-super-120b-a12b:free`·`dots-3-note-preview:free`·`cohere/north-mini-code:free`) 전부 잔류 — 대표 변경 없음. 10/14 06:00 명단이 기준선에 개별 기록되지 않아 신규 1종 특정 불가 — 15종 전체 명단을 더보기 섹션에 기록 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-16: OpenCode Zen — 아침 워치(06:00 `/v1/models` API 직접 확인): 무료 10종→11종, `nemotron-3.5-super-vl-free` 신규 등재 (기존 10종 잔류). 대표 3종 변경 없음 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-16: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인, 2회 연속 동일): tier-free 29종 유지. `rnj-1`(major_outage→정상)·`glm-4.7-flash`(partial_outage→정상) 복귀 — 정상 6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`·`glm-4.7-flash`). `unmoderated-gpt`는 정상→major_outage로 전환, `gemma3-270m:free`는 major_outage 유지. 대표 3종(`llama-instant`·`mistral-large-4`·`kimi-k2.7-code`) 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-16: 확인 필요 — Cloudflare Workers AI 신규 후보 추가: OpenAI 호환 공식 확인 (`/ai/v1/chat/completions`·`/ai/v1/responses`, 도구 호출 지원), 무료 10,000 Neurons/day (전 플랜 공통, 일 00:00 UTC 리셋, 카드 불필요). 단 일부 모델(Kimi K2.6/K2.7-code·GLM-5.2 등)은 Workers Paid 플랜 필요 — 무료 모델 목록은 공식 카탈로그에서 추가 확인 필요, 형님 판단 대기 (출처: https://developers.cloudflare.com/workers-ai/platform/pricing/, https://developers.cloudflare.com/ai-gateway/usage/rest-api/).

- 2026-10-16: 아침 워치 — 위 6건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, `stealth/missingno` 포함 — API 가격 표기 포맷만 "0"→"0.0000000000"으로 변경, $0 동일 — 라이브 API 직접 확인)·OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·Gemini(API 무료 티어 유지 — 가격표 직접 확인)·AIHubMix(27+ 무료 유지 — 무료 모델 문서 직접 확인)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인, "Other Pricing" 섹션·페이지 업데이트 2026-10-10)·BazaarLink(무료 2종 유지, 24h 프로브 100% — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 모델 가격표에서 agnes-2.5/3.0-flash 모두 Current price $0 직접 확인, 페이지 업데이트 2026-10-13; agnes-ai.com은 클라이언트 오류 유지)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인). 신규 상시 무료 제공자 없음 — ReadyServer LLM API(10/14 발표)는 VPS 번들·사설망 전용이라 범위 외.

- 2026-10-15: OpenCode Zen — 저녁 워치(18:00 `/v1/models` API 직접 확인 + 재확인): 무료 9종→10종, `deepseek-v4.1-flash-free` 신규 등재 (기존 9종 잔류 — 재확인에서도 10종 유지). 대표 3종 변경 없음 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-15: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인 + 재확인): tier-free 29종 유지. `rnj-1`이 major_outage로 재전환 (06:20 정상 복귀 후) — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`unmoderated-gpt`, 재확인에서 `unmoderated-gpt`가 degraded→정상 복귀). `glm-4.7-flash`는 degraded→partial_outage로 악화, `gemma3-270m:free`는 major_outage 유지. 대표 3종은 모두 정상 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-15: Z.ai — 공식 가격표 구조 변경 관찰 (18:00 라이브 브라우저 직접 확인): 무료 3종(`glm-4.7-flash`·`glm-4.5-flash`·`glm-4.6v-flash`)이 본문 요금 테이블에서 "Other Pricing"(레거시) 접힘 섹션으로 이동. 3종 모두 입력·캐시·출력 전부 Free 유지, "Limited-time Free" 라벨 없음 — 무료 상태 변화 없음. 향후 변경 전조일 수 있어 관찰 유지 (출처: https://docs.z.ai/guides/overview/pricing).

- 2026-10-15: 저녁 워치 — 위 3건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenRouter(`:free` 14종 유지, 대표 3종 잔류 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, `stealth/missingno` 포함 — 라이브 API 직접 확인)·OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·Token Harbor(무료 3종 유지 — 라이브 브라우저 직접 확인; `claude-haiku-5.5:free`는 오늘 22:00 KST 무료 만료 예정, 확인 시점 기준 약 4시간 남음)·AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지 — 라이브 브라우저 직접 확인)·Gemini(API 무료 티어 유지 — 가격표 직접 확인, 페이지 업데이트 2026-10-14 UTC)·AIHubMix(27+ 무료 유지 — 무료 모델 문서 직접 확인)·BazaarLink(무료 2종 유지 — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 모델 가격표에서 agnes-2.5/3.0-flash 모두 Current price $0 직접 확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — for 7 days' 유지 — 개발자 페이지 직접 확인)·Cline(API 미지원 유지 — 문서 직접 확인). 신규 상시 무료 제공자 없음 — ReadyServer LLM API(10/14 발표)는 VPS 번들·사설망 전용이라 범위 외.

- 2026-10-15: Ollama Cloud 제외 (형님 결정) — starter 무료 모델 목록이 공개 정보로 확인 불가. '확인 필요' 섹션 신설 (Ollama Cloud·Typhoon·Agnes AI·Kilo Code·Routeway·LLMTR). (출처: https://ollama.com/pricing)

- 2026-10-15: Api.Airforce — 06:20 재확인: `rnj-1`이 major_outage→정상 복귀 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). `glm-4.7-flash`는 degraded, `gemma3-270m:free`는 major_outage 유지 (출처: https://api.airforce/v1/models).

- 2026-10-15: OpenCode Zen — 아침 워치(06:00 `/v1/models` API 직접 확인): 무료 11종→9종. `ling-3.1-flash-free`가 체험 종료일(10/13) 이틀 만에 목록에서 제거됨 (Nous Portal·OpenRouter는 10/14 아침에 이미 유료 전환 — Zen만 이틀 유예). `big-pickle`(스텔스 모델)도 목록에서 제거됨 — 스텔스 관련 정보에서 Big Pickle 링크 정리. 대표에서 `big-pickle` 제외, `jev-1.13-free` 편입. 기간 한정 요약표의 ling-3.1-flash 행 정정 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-15: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인, last_check 10-14 20:55 UTC): tier-free 29종 유지. `rnj-1`이 정상→major_outage로 전환 — 현재 정상 4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). `glm-4.7-flash`는 major_outage→degraded로 개선, `gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 partial_outage. 대표에서 `rnj-1` 제외, `kimi-k2.7-code` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-15: 아침 워치 — 위 2건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenRouter(`:free` 14종 유지, 대표 3종 잔류 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, `stealth/missingno` 포함 — 라이브 API 직접 확인)·OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·Token Harbor(무료 3종 유지 — 라이브 브라우저 직접 확인; `claude-haiku-5.5:free`는 오늘 22:00 KST에 무료 만료 예정)·AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지 — 라이브 브라우저 직접 확인)·Gemini(API 무료 티어 유지 — 가격표 직접 확인)·AIHubMix(무료 모델 문서 유지 — `coding-glm-5.1-free`·`gpt-5.5-free`·`xiaomi-mimo-v2.5-free` 그대로)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인, 페이지 업데이트 2026-10-10)·BazaarLink(무료 2종 유지 — 무료 페이지 직접 확인)·Agnes AI($0 프로모션 유지 — 공식 Docs 모델 가격표에서 agnes-2.5/3.0-flash 모두 Current price $0 직접 확인, 페이지 업데이트 2026-10-13; agnes-ai.com은 클라이언트 오류 유지)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Ollama Cloud(Free 플랜 구조 유지 — 가격 페이지 직접 확인)·Cline(API 미지원 유지). 신규 상시 무료 제공자 없음 — Typhoon(SCB 10X: 공식 FAQ "research showcase and free to use", OpenAI 호환 `https://api.opentyphoon.ai/v1`, `typhoon-v2.5-30b-a3b-instruct` 등 — 태국어 특화 모델이라 형님 판단 대기, 출처: https://docs.opentyphoon.ai/en/faq/ · https://docs.opentyphoon.ai/en/api-reference/).

- 2026-10-14: Api.Airforce — 저녁 워치(18:00 공개 API 라이브 확인): tier-free 29종 유지. `gemma3-270m:free`가 정상→major_outage로 전환, `gpt-oss-20b`가 degraded→정상 복귀 — 현재 정상 5종 (`llama-instant`·`mistral-large-4`·`rnj-1`·`kimi-k2.7-code`·`gpt-oss-20b`). `glm-4.7-flash`는 major_outage 유지, `unmoderated-gpt`는 partial_outage. 대표 3종은 모두 정상 유지 — 대표 변경 없음. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-14: OpenCode Zen — 저녁 워치(18:00 `/v1/models` API 직접 확인): 무료 11종 유지 (전일 동일). `ling-3.1-flash-free`는 체험 종료일(10/13) 경과 이틀째에도 목록 유지 — 제거 미발생 (Nous Portal·OpenRouter에서는 10/14 아침 유료 전환 확인, Zen만 유예 중 — 다음 워치 재확인). `cat-jam-free` 등 신규 등재 유지 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-14: 저녁 워치 — 위 2건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenRouter(`:free` 14종 유지, 대표 3종 잔류 — 라이브 API 직접 확인)·Nous Portal(무료 8종 유지, `stealth/missingno` 포함 — 라이브 API 직접 확인)·OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·Token Harbor(무료 3종 유지 — 라이브 브라우저 직접 확인; `claude-haiku-5.5:free`는 10/15 13:00까지 무료, 만료일은 내일)·AnyAPI(Free 5종 유지 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM('Free inference' 4종 유지 — 라이브 브라우저 직접 확인)·Gemini(API 무료 티어 유지 — 가격표 직접 확인)·AIHubMix(무료 모델 문서 유지 — `coding-glm-5.1-free`·`gpt-5.5-free`·`xiaomi-mimo-v2.5-free` 그대로)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인, 페이지 업데이트 2026-10-10)·BazaarLink(무료 2종 유지 — 무료 페이지 직접 확인)·Agnes AI(공식 사이트 클라이언트 오류로 직접 확인 불가 — 3자 10/05 검증 기준 $0 프로모션 유지이나 공식 미확인)·Hetzner(실험 무료 2종·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Ollama Cloud(Free 플랜 구조 유지 — 가격 페이지 직접 확인)·Cline(API 미지원 유지). 신규 상시 무료 제공자 없음.

- 2026-10-14: Api.Airforce — 06:15 재확인: `gemma3-270m:free`가 major_outage→정상 복귀 — 현재 정상 5종 (`gemma3-270m:free`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). `gpt-oss-20b`는 degraded, `glm-4.7-flash`는 major_outage 유지 (출처: https://api.airforce/v1/models).

- 2026-10-14: Nous Portal — 아침 워치(06:00 공식 API 라이브 확인): `inclusionai/ling-3.1-flash`가 2주 체험 종료 후 유료 전환 (입력 $0.075/1M, 출력 $0.225/1M) — 무료 목록에서 제거. `inclusionai/ling-3.0-flash-sante:free`·`inclusionai/ling-3.0-flash-fin:free`도 카탈로그에서 완전 삭제됨. 무료 11종→8종. 대표 3순위에서 `sante:free` 제외, `stepfun/step-5-preview:free` 편입. 기간 한정 요약표 정정 (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-14: OpenRouter — 아침 워치(06:00 공개 API 라이브 확인): `:free` 19종→14종. `apodex/apodex-1.1-mini:free`가 카탈로그에서 완전 삭제됨 (삭제 확인). 나머지 4종도 카탈로그에서 삭제됐으나 10/13 저녁 등재 시 명단이 기준선에 개별 기록되지 않아 대조 불가 — 잔류 14종은 기존 추적 모델 전부 유지. 대표 3종(`nemotron-3-super-120b-a12b:free`·`dots-3-note-preview:free`·`cohere/north-mini-code:free`) 전부 잔류. `inclusionai/ling-3.1-flash`는 유료 전환 (출처: https://openrouter.ai/api/v1/models).

- 2026-10-14: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인, last_check 05:56 KST): tier-free 29종 유지. `gpt-oss-20b`가 degraded로 전환, `rnj-1`이 major_outage에서 정상 복귀 — 현재 정상 4종 (`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`·`rnj-1`). `glm-4.7-flash`·`gemma3-270m:free`는 major_outage 유지, `unmoderated-gpt`는 partial_outage. 대표에서 `gpt-oss-20b` 제외, `rnj-1` 편입. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-14: LLM7.io — 아침 워치(06:00 라이브 API 직접 확인): turbo(무료) 7종 유지이나 구성 변경 — `gemma4:31b`이 turbo→pro 티어로 유료 전환, `minimax-m2.7`은 10/10 카탈로그 제거 후 turbo로 복귀. 대표 3종(`DeepSeek-V4-Flash-0731`·`GLM-5.3-Flash`·`gpt-oss:20b`)은 전부 turbo 유지 (출처: https://api.llm7.io/v1/models).

- 2026-10-14: OpenCode Zen — 아침 워치(06:00 `/v1/models` API 직접 확인): 무료 11종 유지 (전일 동일). `ling-3.1-flash-free`는 체험 종료일(10/13) 경과 후 10/14 아침에도 목록 유지 — 제거 미발생 (Nous Portal·OpenRouter에서는 10/14 아침 유료 전환 확인, Zen만 유예 중 — 다음 워치 재확인). `cat-jam-free` 등 신규 등재 유지 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-14: 아침 워치 — 위 5건 외 변동 없음: OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·Token Harbor(무료 3종 유지, `claude-haiku-5.5:free`는 "Free until 10/15/2026, 1:00:00 PM" 표기 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지 — 'Free inference' 섹션 브라우저 직접 확인; `nemotron-3.5-lightning-30b-a55b` 표기는 옆 카드(`nemotron-3-ultra-550b-a55b`)와의 혼동으로 판단 — 3자 자료(NVIDIA API ID·HF 가중치·OpenRouter canonical slug) 모두 `a3b` 확인)·Gemini(API 무료 티어 유지 — 가격표 직접 확인)·AIHubMix(무료 모델 문서 유지 — `coding-glm-5.1-free`·`gpt-5.5-free`·`xiaomi-mimo-v2.5-free` 그대로)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인, 페이지 업데이트 2026-10-10)·BazaarLink(무료 2종 유지 — 브라우저 직접 확인)·Agnes AI($0 프로모션 유지 — Docs 모델 페이지에서 agnes-2.5/3.0-flash 모두 Current price $0 직접 확인, /pricing은 404)·Hetzner(실험 무료 2종 유지·한도 동일 — 공식 Docs 확인)·ZeroLimitAI('Free week — $0 for 7 days' 유지 — 개발자 페이지 직접 확인)·Ollama Cloud(Free 플랜 구조 유지 — 가격 페이지 직접 확인)·Cline(API 미지원 유지). 신규 상시 무료 제공자 없음 — OVHcloud AI Endpoints 익명 티어(가입·키·카드 불필요, OpenAI 호환, 모델당 분 2회, 3자 10/08 검증 — `gpt-oss-120b`·`qwen3.6`·`qwen3.8-27b`·`qwen3-coder`)는 신규 후보로 형님 판단 대기 (출처: https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/ovh-ai-endpoints.md).

- 2026-10-13: Api.Airforce — 18:12 재확인: `gemma3-270m:free`·`glm-4.7-flash`·`rnj-1` major_outage, `unmoderated-gpt` partial_outage 전환 — 현재 정상 4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). `mistral-large-4` 신규는 tier-free 29종 기준 유지. 대표 모델에서 `glm-4.7-flash` 제외, `mistral-large-4` 편입 (출처: https://api.airforce/v1/models).

- 2026-10-13: OpenCode Zen — 저녁 워치(18:00 `/v1/models` API 직접 확인): 무료 10종→11종, `cat-jam-free` 신규 등재 (owned_by: opencode — 정체 미공개, 관련 정보 확인 시 링크 추가). `ling-3.1-flash-free`는 체험 종료일(10/13) 당일 저녁에도 목록 유지 — 제거 미발생 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-13: Api.Airforce — 저녁 워치(18:00/18:06 공개 API 확인 + 18:08 직접 재확인): tier-free 28종→29종 (`mistral-large-4` 신규). 정상 6종 (`gemma3-270m:free`·`glm-4.7-flash`·`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`mistral-large-4`). `unmoderated-gpt`는 partial_outage, `rnj-1`은 major_outage로 전환 — 대표에서 `unmoderated-gpt` 제외, `glm-4.7-flash` 편입. 수 분 간격 뒤집힘 지속 (출처: https://api.airforce/v1/models).

- 2026-10-13: OpenRouter — 저녁 워치(18:00 공개 API 직접 확인): `:free` 15종→19종 (prompt/output $0 전원 개별 재조회 확정). 대표 3종 잔류 확인. `inclusionai/ling-3.1-flash`도 $0 유지 (체험 종료일 10/13 당일) (출처: https://openrouter.ai/api/v1/models).

- 2026-10-13: Nous Portal — 저녁 워치(18:00 공식 API 직접 확인): 무료 11종 유지 (전일 동일). `inclusionai/ling-3.1-flash` $0 유지 — 체험 종료일(10/13) 당일 제거 미발생 (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-13: Api.Airforce — 06:15 재확인: `gemma3-270m:free`가 degraded, `rnj-1`이 major_outage로 전환 — 현재 정상 4종 (`gpt-oss-20b`·`glm-4.7-flash`·`llama-instant`·`unmoderated-gpt`). `kimi-k2.7-code`도 major_outage 유지 (출처: https://api.airforce/v1/models).

- 2026-10-13: Api.Airforce — 아침 워치(06:00 공개 API 라이브 확인): `kimi-k2.7-code`가 major_outage로 전환, `gpt-oss-20b`·`gemma3-270m:free`·`glm-4.7-flash` 정상 복귀 — 정상 4종→6종 (`gpt-oss-20b`·`gemma3-270m:free`·`glm-4.7-flash`·`rnj-1`·`llama-instant`·`unmoderated-gpt`). 대표 모델에서 `kimi-k2.7-code` 제외, `unmoderated-gpt` 편입. 분 단위 뒤집힘 지속 (출처: https://api.airforce/v1/models).

- 2026-10-13: OpenCode Zen — 아침 워치(06:00 `/v1/models` API 직접 확인): 무료 13종→10종 — `mimo-v2.5-free`·`ling-3.0-flash-fin-free`·`nemotron-3-ultra-free`·`exo-free` 제거, `muse-spark-1.2-contributor-free` 신규. `ling-3.1-flash-free`는 체험 종료일(10/13) 당일에도 목록 유지 — 제거 여부 저녁 워치에서 재확인. 대표 모델에서 `nemotron-3-ultra-free` 제외, `step-5-preview-free` 편입. 구 Docs URL(`opencode.ai/docs/zen/`) 404 — Zen 페이지는 https://opencode.ai/zen 으로 이전, 정적 Free 목록 없음 (출처: https://opencode.ai/zen/v1/models).

- 2026-10-13: Nous Portal — 아침 워치(06:00 공식 API 라이브 확인): 무료 11종 유지 (전일 동일). `ling-3.1-flash`는 체험 종료일(10/13) 당일에도 API상 $0 유지 — 제거 여부 저녁 워치에서 재확인. `stealth/missingno` 관련 [실사용 영상](https://www.youtube.com/watch?v=LWlW-TXBLsk) 링크 추가 (Hermes Cloud 사용법·토큰 효율 실측, 10/12 게시) (출처: https://inference-api.nousresearch.com/v1/models).

- 2026-10-13: 아침 워치 — 위 3건 외 변동 없음: LLM7.io(turbo 7종 유지 — 라이브 API 직접 확인)·OpenRouter(`:free` 15종 유지 — 라이브 API 직접 확인)·OrcaRouter(무료 5종 유지 — pricing API 직접 확인)·Token Harbor(무료 3종 유지, `claude-haiku-5.5:free`는 10/15 13:00 UTC까지 — 라이브 브라우저 직접 확인)·AnyAPI(Free 5종 유지, Gemma 3n 4B (free) 포함 — 라이브 브라우저 직접 확인)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지 — 'Free inference' 섹션 직접 확인)·Gemini(API 무료 티어 유지 — 가격표 직접 확인)·AIHubMix(무료 모델 문서 유지)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인, GLM-4.5-Flash 종료 루머는 공식 근거 없음)·BazaarLink(무료 2종 유지)·Hetzner(실험 무료 2종 유지 — 공식 Docs 확인)·ZeroLimitAI('Free week' 유지)·Ollama Cloud·Cline(API 미지원 유지). Agnes AI는 공식 페이지 클라이언트 오류로 직접 확인 불가 — 3자 자료(10/05) 기준 $0 프로모션 유지이나 공식 미확인. 신규 상시 무료 제공자 없음.

- 2026-10-12: Api.Airforce — 18:25 재확인: `gpt-oss-20b`이 degraded로 전환 — 현재 정상 4종 (`kimi-k2.7-code`·`llama-instant`·`unmoderated-gpt`·`rnj-1`). `glm-4.7-flash`·`gemma3-270m:free`는 major_outage 유지 (출처: https://api.airforce/v1/models).

- 2026-10-12: AnyAPI — 저녁 워치(18:03 라이브 브라우저 직접 확인): Google Gemma 3n 4B (free)가 Free 티어로 복귀 — Free 4종→5종. 10/11 아침에도 복귀→제거를 반복한 불안정 라인업 (출처: https://anyapi.ai/ai-models).

- 2026-10-12: Api.Airforce — 저녁 워치(18:00~18:12 라이브 확인): `unmoderated-gpt`가 degraded→정상 복귀, `rnj-1` 정상 유지, `glm-4.7-flash`가 major_outage로 전환 — 현재 정상 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`unmoderated-gpt`·`rnj-1`). `gemma3-270m:free`는 major_outage 유지. 분 단위 뒤집힘 지속 (출처: https://api.airforce/v1/models).

- 2026-10-12: Ling-3.1-flash — 무료 체험 종료일 2026-10-13로 공식 확인 (Vercel AI Gateway "free to use through October 13, 2026", Cline 10/3 발표, LLMTR 조건). 기간 한정 요약표·Nous·OpenCode Zen 표기를 확정일로 정정 (출처: https://vercel.com/changelog/ling-3-1-flash-is-now-available-on-ai-gateway).

- 2026-10-12: 저녁 워치 — 위 3건 외 변동 없음: LLM7.io(turbo 7종 유지)·OpenRouter(`:free` 15종 유지)·Nous Portal(무료 11종 유지, `stealth/missingno` 포함 — 정체 관련 새 정보 없음)·OrcaRouter(무료 5종 유지)·Token Harbor(무료 3종 유지, `claude-haiku-5.5:free`는 10/15 13:00 UTC까지)·OpenCode Zen(무료 13종 유지, `ling-3.1-flash-free` 아직 Free)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지 — 'Free inference' 섹션 직접 확인)·Gemini(API 무료 티어 유지 — 가격표 직접 확인)·AIHubMix(무료 모델 문서 유지)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인, GLM-4.5-Flash 종료 루머는 공식 근거 없음)·BazaarLink(무료 2종 유지)·Hetzner(실험 무료 2종 유지 — 공식 Docs 확인)·ZeroLimitAI('Free week' 유지)·Ollama Cloud·Cline(API 미지원 유지). Agnes AI는 공식 페이지 로드 실패(클라이언트 오류)로 직접 확인 불가 — 3자 자료(10/05) 기준 $0 프로모션 유지이나 공식 미확인. 신규 상시 무료 제공자 없음.

- 2026-10-12: Api.Airforce — 06:00엔 정상 6종이었으나 06:10 재확인에서 `rnj-1`이 partial_outage로 전환 — 현재 정상 5종 (출처: https://api.airforce/v1/models).

- 2026-10-12: 아침 워치 — Api.Airforce 외 변동 없음: LLM7.io(turbo 7종 유지)·OpenRouter(`:free` 15종 유지)·Nous Portal(무료 11종 유지, `ling-3.1-flash` 체험 유효 — 종료 예상 ~10/13~14)·OrcaRouter(무료 5종 유지)·Token Harbor(무료 3종 유지, claude-haiku-5.5:free 10/15 13:00 UTC까지)·OpenCode Zen(무료 13종 유지)·AnyAPI(Free 4종 유지)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지 — 'Free inference' 섹션 직접 확인)·Gemini(API 무료 티어 유지)·AIHubMix(무료 모델 문서 유지)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·BazaarLink(무료 2종 유지)·Agnes AI($0 프로모션 유지 — 3자 10/05 확인)·Hetzner(실험 무료 2종 유지 — 공식 Docs 확인)·ZeroLimitAI('Free week' 유지)·Ollama Cloud·Cline(API 미지원 유지). 신규 상시 무료 제공자 없음.
- 2026-10-12: Api.Airforce — 아침 워치(06:00 라이브 확인): `glm-4.7-flash`가 다시 major_outage로 전환, `gemma3-270m:free`가 정상 복귀였으나 5분 간격 재확인에서 다시 뒤집힘 — 최종 어제 저녁 상태(정상 6종: `gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`rnj-1`·`unmoderated-gpt`·`glm-4.7-flash`, `gemma3-270m:free`는 major_outage) 유지. 대표 모델 3종은 모두 정상. 분 단위 뒤집힘 지속 — 사용 전 재확인 필수 (출처: https://api.airforce/v1/models).

- 2026-10-11: Nous Portal — `stealth/missingno`(MissingNo) 신규 무료 등재 확인 (18:00 라이브 API): 스텔스 추론 모델, 262K 컨텍스트·도구 호출·구조화 출력 지원, 추론 상시 활성화(깊이 조절 가능), 입·출력 $0. 무료 10종→11종, 대표 모델 1순위에 편입. 정체 미공개 — 10/11 신규 등재라 외부 정보 없음 (스텔스 모델 표기 규칙상 정보 확보 시 링크 추가) (출처: https://inference-api.nousresearch.com/v1/models).
- 2026-10-11: Api.Airforce — 저녁 워치(18:00 라이브 확인): `glm-4.7-flash`가 다시 정상 복귀, 정상 호출 가능 무료 모델 5종→6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`rnj-1`·`unmoderated-gpt`·`glm-4.7-flash`). `gemma3-270m:free`는 major_outage 유지. 하루 종일 버틴 안정 3종(`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`)은 그대로 대표 모델 유지 (출처: https://api.airforce/v1/models).
- 2026-10-11: 저녁 워치 — 위 2건 외 변동 없음: LLM7.io(turbo 7종 유지)·OpenRouter(`:free` 15종 유지)·OrcaRouter(무료 5종 유지)·Token Harbor(무료 3종 유지, claude-haiku-5.5:free 10/15 13:00 UTC까지)·OpenCode Zen(무료 13종 유지 — Docs 'The free models' 섹션 직접 확인)·AnyAPI(Free 4종 유지)·Groq(한도 동일 — 한도 문서 직접 확인)·NVIDIA NIM(무료 4종 유지 — build.nvidia.com 'Free inference' 섹션 직접 확인)·Gemini(API 무료 티어 유지 — 10/10 3자 확인)·AIHubMix(무료 모델 문서 유지)·Z.ai(Flash 3종 Free 유지 — 공식 가격표 직접 확인)·BazaarLink(무료 2종 유지)·Agnes AI($0 프로모션 유지 — 3자 최신 확인)·Hetzner(실험 무료 2종 유지 — 공식 Docs 확인)·ZeroLimitAI('Free week' 유지). 신규 상시 무료 제공자 없음.

- 2026-10-11: Mistral 제외 (형님 결정) — 가격 페이지 개편 이후 Free 플랜의 "월 $10 API 크레딧" 문구가 7회 연속 확인되지 않음. 웹 검색상 하루 25회 요청 같은 비공식 정보만 있고 사용량 기준이 모호해 추적 대상에서 제외. 향후 공식 무료 API 티어 확인 시 재등록 검토 (출처: https://mistral.ai/pricing).

- 2026-10-11: AnyAPI — 06:00에 Google Gemma 3n 4B (free)의 Free 복귀가 확인됐으나 06:15 재확인에서는 Free 목록에 없음 (Free 4종 유지). 카탈로그가 분 단위로 뒤집히는 중 — 다음 워치에서 재확인 (출처: https://anyapi.ai/ai-models).
- 2026-10-11: Api.Airforce — `glm-4.7-flash`가 다시 major_outage로 전환, 정상 호출 가능 무료 모델 6종→5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`rnj-1`·`unmoderated-gpt`). `gemma3-270m:free`는 major_outage 유지. 안정 3종(`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`)은 그대로 정상 (출처: https://api.airforce/v1/models).
- 2026-10-11: 아침 워치 — 위 2건 외 변동 없음: LLM7.io(turbo 7종 유지)·OpenRouter(`:free` 15종 유지)·Nous Portal(무료 10종 유지, `ling-3.1-flash` 체험 유효 — 종료 예상 ~10/13~14)·OrcaRouter(무료 5종 유지)·Token Harbor(무료 3종 유지, claude-haiku-5.5:free 10/15 13:00 UTC까지)·OpenCode Zen(무료 13종 유지)·Groq(한도 동일)·NVIDIA NIM(무료 4종 유지)·Gemini(API 무료 티어 유지)·Mistral(Free 월 $10 크레딧 문구 7회 연속 없음 — 형님 판단 대기 유지)·AIHubMix(27+ 무료 유지)·Z.ai(Flash 3종 Free 유지 — 3자 매체의 'GLM-4.5-Flash retirement' 주장은 공식 가격표에서 확인 불가)·BazaarLink(무료 2종 유지)·Agnes AI($0 프로모션 유지)·Hetzner(실험 무료 2종 유지)·ZeroLimitAI('Free week' 유지)·Ollama Cloud·Cline(API 미지원 유지). 신규 상시 무료 제공자 없음.

- 2026-10-10: Api.Airforce — 저녁 워치(18:00 라이브 확인): `glm-4.7-flash`가 major_outage에서 정상 복귀, 정상 호출 가능 무료 모델 5종→6종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`rnj-1`·`unmoderated-gpt`·`glm-4.7-flash`). 하루 종일 정상 유지 중인 안정 3종(`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`)은 그대로 대표 모델 유지. `gemma3-270m:free`는 major_outage 유지 (출처: https://api.airforce/v1/models).

- 2026-10-10: LLM7.io — turbo(무료) 티어 10종→7종: `minimax-m2.7`이 카탈로그에서 제거되고, `glm-5.2`·`minimax-m3`이 turbo→pro 티어 강등 (유료 전환). 2회 라이브 확인에서 변동 없음 — 안정된 것으로 보임. 대표 모델 2순위에서 `minimax-m2.7` 제외하고 `GLM-5.3-Flash`(멀티모달 플래시)로 교체 (출처: https://api.llm7.io/v1/models).
- 2026-10-10: Api.Airforce — `gemma3-270m:free`가 다시 major_outage로 전환, 정상 호출 가능 무료 모델 6종→5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`rnj-1`·`unmoderated-gpt`). `glm-4.7-flash`는 major_outage 지속. 대표 모델 3종은 모두 정상 유지. 사용 전 재확인 권장 (출처: https://api.airforce/v1/models).
- 2026-10-10: Mistral — Free 플랜의 "월 $10 API 크레딧" 문구 5회 연속(10/08 저녁·10/09 아침·저녁·10/10 아침·저녁) 없음. Pro엔 "$25.5/mo in API credits"·다른 등급엔 "$15/mo in API credits" 표기가 있으나 Free 플랜 카드에만 없음. 실제 제거인지 페이지 개편인지는 여전히 미확인 — 형님 판단 대기 (출처: https://mistral.ai/pricing).

- 2026-10-09: Api.Airforce — 상태 뒤집힘 지속 (18:00 라이브 확인): `glm-4.7-flash`가 다시 major_outage로 전환, `unmoderated-gpt`(major_outage→정상)·`rnj-1` 정상 복귀. ※ 18:15 재확인에서 `gemma3-270m:free`도 정상 복귀 — 현재 정상 6종. 정상 호출 가능 무료 모델 4종→5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`rnj-1`·`unmoderated-gpt`). `gemma3-270m:free` degraded 지속. 대표 모델 3순위에 `llama-instant` 복귀. 사용 전 재확인 권장 (출처: https://api.airforce/v1/models).
- 2026-10-09: OpenCode Zen — Free 목록 교체: `fledge-alpha-free` 제거, `step-5-preview-free` 신규 등재 (가격표 Free 행 입·출력·캐시 읽기 모두 Free, "free on OpenCode for a limited time", zero-retention). 무료 13종 유지. Zen 무료 티어는 Hermes 외부 사용 불가 유지라 연결에는 영향 없음 (출처: https://opencode.ai/docs/zen/).
- 2026-10-09: Mistral — Free 플랜의 "월 $10 API 크레딧" 문구 3회 연속(10/08 저녁·10/09 아침·저녁) 없음. 실제 제거인지 페이지 개편인지는 여전히 미확인 — 형님 판단 대기 (출처: https://mistral.ai/pricing).

- 2026-10-09: Token Harbor — Free 카테고리에 3종 다시 등재 확인 (06:10 라이브 브라우저 직접 확인): `claude-haiku-5.5:free` ("FREE LIMITED TIME", 10/15까지 무료 후 표준 요금 전환), `deepseek-v4.1-flash:free` (FREE), `mimo-v2.6-flash:free` (FREE). 10/08 저녁 18:11엔 "Nothing in this tier yet"이었으나 아침에 복귀 — Free 목록 등재가 불안정, 사용 전 재확인 필수 (출처: https://tokenharbor.ai/models?category=free).
- 2026-10-09: Api.Airforce — 상태 뒤집힘 지속: 06:01엔 정상 2종(`gpt-oss-20b`·`kimi-k2.7-code`)이었으나 07:10 재확인에서 `llama-instant`(degraded→정상)·`glm-4.7-flash`(major_outage→정상) 복귀 — 현재 정상 4종. `unmoderated-gpt` major_outage, `gemma3-270m:free` degraded 지속 (출처: https://api.airforce/v1/models).
- 2026-10-09: Nous Portal — 무료 9종→10종. `stepfun/step-5-preview:free` 신규 등재 (공식 API 가격 $0 기준). Nous 무료 라인업은 일 단위로 뒤집히는 로테이션 패턴이 반복되므로 보조·폴백용으로만 권장 (출처: https://inference-api.nousresearch.com/v1/models).
- 2026-10-09: OpenRouter — `:free` 16종→15종. 당시 대표 #1이던 `inclusionai/ling-3.0-flash-sante:free`가 무료에서 제거됨. 대표 모델 1순위를 `nvidia/nemotron-3-super-120b-a12b:free`로 승격, 3순위에 `cohere/north-mini-code:free` 편입. 잔류 15종 전부 pricing prompt/output "0" 확인 (출처: https://openrouter.ai/api/v1/models).
- 2026-10-09: LLM7.io — `deepseek-v4-pro`가 turbo→pro 티어로 강등 (무료→유료), turbo 11종→10종. 대표 모델에서 `deepseek-v4-pro`를 제외하고 `minimax-m2.7`(180K 컨텍스트·도구 호출·추론 지원)을 2순위로 편입 (출처: https://api.llm7.io/v1/models).
- 2026-10-09: NVIDIA NIM — 무료 라인업에서 `deepseek-ai/deepseek-v4-pro-0813`이 `deepseek-ai/deepseek-v4.1-flash`로 교체됨 (무료 4종 유지: kimi-k3·deepseek-v4.1-flash·nemotron-3.5-lightning-30b-a3b·nemotron-3-ultra-550b-a55b). 대표 모델도 교체 반영 (출처: https://build.nvidia.com).

- 2026-10-08: Token Harbor — 저녁 워치(18:00)의 `claude-haiku-5.5:free` 무료 등재를 18:11 브라우저 직접 확인에서 정정: Free 카테고리가 완전히 비어 있음 ("Nothing in this tier yet"), 3종 모두 Value(유료)로 표기. 무료 라인업이 분 단위로 뒤집히는 중 — 다음 워치에서 재확인 (출처: https://tokenharbor.ai/models?category=free).

- 2026-10-08: Token Harbor — `claude-haiku-5.5:free` (Claude Haiku 5.5) 신규 등재 → 무료 2종→3종. "Limited time" 뱃지, freeUntil 2026-10-15T13:00:00+00:00 (약 7일 기간 한정 프로모). 종료 후 목록 제거 여부를 다음 워치에서 추적 (출처: https://tokenharbor.ai/models?category=free — freeRows JSON 직접 파싱).
- 2026-10-08: Mistral — 가격 페이지가 Vibe(Pro $14.99/월·Team $24.99/사용자/월) 중심으로 개편되어 Free 플랜의 "월 $10 API 크레딧" 문구가 사라짐 (직접 확인). Free 플랜 자체는 FAQ에 유지. 실제 제거인지 페이지 개편인지는 미확인 — 다음 아침 워치에서 추가 확인 예정, 형님께 판단 질문 (출처: https://mistral.ai/pricing).
- 2026-10-08: Api.Airforce — 상태 뒤집힘 지속 (18:03 확인): 아침 정상이던 `rnj-1`이 major_outage로 전환, `unmoderated-gpt`는 partial_outage→operational로 복귀. 4분 간격 재확인에서 `glm-4.7-flash`가 17:59 정상→18:03 major_outage로 뒤집힘. 현재 정상 4종 (`gpt-oss-20b`·`llama-instant`·`kimi-k2.7-code`·`unmoderated-gpt`), 하루 종일 정상은 3종 (`gpt-oss-20b`·`llama-instant`·`kimi-k2.7-code`). 대표 모델에서 `rnj-1` 제외, 사용 전 재확인 권장 (출처: https://api.airforce/v1/models).
- 2026-10-08: 저녁 워치 — 위 3건 외 변동 없음: LLM7.io(turbo 11종 유지)·OpenRouter(`:free` 16종 유지)·Nous Portal(무료 9종 유지, laguna 2종 만료일 2026-10-31 표기 유지)·OrcaRouter(무료 5종 유지)·OpenCode Zen(무료 13종 유지)·AnyAPI(Free 4종 유지)·Groq(한도 동일)·Gemini(API 무료 티어 유지)·NVIDIA NIM(무료 4종 유지)·AIHubMix·Z.ai(Flash 3종 Free 유지)·Agnes AI($0 유지)·BazaarLink(무료 2종 유지)·Hetzner(모델 2종·실험 무료 유지)·ZeroLimitAI('Free week' 유지)·Ollama Cloud·Cline(API 미지원 유지). 신규 상시 무료 제공자 없음.
- 2026-10-08: OpenCode Zen — `exo-free`(Exo Free) 신규 등재 → 무료 12종→13종 (입·출력 모두 Free, 상세 스펙 미공개). Hermes 등 외부 하네스에서 Zen 무료 티어 사용 불가는 여전 (출처: https://opencode.ai/docs/zen/).
- 2026-10-08: Api.Airforce — `glm-4.7-flash`가 major_outage에서 정상 복귀, `gemma3-270m:free`는 degraded→major_outage로 악화, `unmoderated-gpt`는 partial_outage 유지. 정상 호출 가능 무료 모델 4종→5종 (`gpt-oss-20b`·`llama-instant`·`kimi-k2.7-code`·`rnj-1`·`glm-4.7-flash`), 3.5분 간격 재확인에서 뒤집힘 없음 (출처: https://api.airforce/v1/models).
- 2026-10-08: 아침 워치 — 위 2건 외 변동 없음: LLM7.io(turbo 11종 유지)·OpenRouter(`:free` 16종 유지)·Nous Portal(무료 9종 유지 — 단 laguna 2종의 API상 만료일 2026-10-31 표기, 추적 필요)·OrcaRouter(무료 5종 유지)·Groq(한도 동일)·NVIDIA NIM(무료 4종)·Gemini(API 무료 티어 유지)·Mistral(Free 월 $10 크레딧 유지)·AnyAPI(Free 4종 유지)·Token Harbor(무료 2종 유지)·BazaarLink(무료 2종 유지)·AIHubMix·Z.ai(Flash 3종 Free 유지)·Agnes AI($0 유지)·Hetzner(모델 2종·실험 무료 유지)·ZeroLimitAI('Free week' 유지)·Ollama Cloud·Cline(API 미지원 유지). 신규 상시 무료 제공자 없음.

- 2026-10-07: Api.Airforce — 저녁 워치(18:00)에서 정상 6종 반영했으나 분 단위로 재전환: `unmoderated-gpt`(정상→partial_outage)·`gemma3-270m:free`(정상→degraded)·`glm-4.7-flash` major_outage 지속. 현재 정상 4종 (`gpt-oss-20b`·`llama-instant`·`kimi-k2.7-code`·`rnj-1`) (출처: https://api.airforce/v1/models).

- 2026-10-07: Api.Airforce — 무료 모델 상태 뒤집힘 지속 (18:00 확인): `unmoderated-gpt`(partial_outage→정상)·`gemma3-270m:free`(degraded→정상) 복귀, `glm-4.7-flash`(정상→major_outage) 재전환. 정상 호출 가능 무료 모델 5종→6종 (`gpt-oss-20b`·`llama-instant`·`unmoderated-gpt`·`gemma3-270m:free`·`kimi-k2.7-code`·`rnj-1`). 사용 전 재확인 권장 (출처: https://api.airforce/v1/models).
- 2026-10-07: 저녁 워치 — Api.Airforce 외 변동 없음: LLM7.io(turbo 11종 유지)·OpenRouter(`:free` 16종 유지)·Nous Portal(무료 9종 유지)·OrcaRouter(무료 5종 유지)·AnyAPI(Free 4종 유지)·Token Harbor(무료 2종, 3자 추적 10-05 검증 유지)·BazaarLink(무료 2종·24h 프로브 100%)·OpenCode Zen(무료 12종)·Groq(한도 동일)·NVIDIA NIM·Gemini(API 무료 티어 유지 — 10/09 변경은 Gemini 앱 한정, API 영향 없음)·Mistral(Free 월 $10 크레딧 유지)·AIHubMix·Agnes AI($0 유지, 3자 추적 10-07 갱신 기준)·Hetzner(모델 2종·실험 단계 무료 유지)·ZeroLimitAI('Free week' 유지). 신규 상시 무료 제공자 없음.
- 2026-10-07: Z.ai 신규 등록 (형님 승인) — GLM Flash 3종 영구 무료 (공식 가격표: `glm-4.7-flash`·`glm-4.5-flash`·`glm-4.6v-flash`, 입력·캐시·출력 전부 Free). OpenAI 호환 (`https://api.z.ai/api/paas/v4`), 카드·휴대폰 불필요 (3자 검증). 한도는 공식 수치 미공개 — concurrency 기반. 우선순위 중간 (출처: https://docs.z.ai/guides/overview/pricing).

<details>
<summary>변경 이력 펼쳐보기</summary>

- 2026-10-07: LLM7.io — turbo(무료) 티어 7종→11종으로 확대: `deepseek-v4-pro`·`gemma4:31b`·`glm-5.2`·`minimax-m3` 신규 추가 (06:00 확인). 확인 직전 분 단위로 9→10→11종으로 변동 후 11종으로 안정 — 라인업 로테이션 중이라 사용 전 재확인 권장 (출처: https://api.llm7.io/v1/models).
- 2026-10-07: Api.Airforce — 카탈로그 API 502 Bad Gateway 장애 발생 (05:57 KST경, 약 1시간) 후 복구. 정상 호출 가능 무료 모델 4종→6종: `gemma3-270m:free`(major_outage→정상 복귀)·`glm-4.7-flash`(partial_outage→정상 복귀), `gpt-oss-20b`·`rnj-1`·`kimi-k2.7-code`·`llama-instant` 정상 유지. `unmoderated-gpt`는 partial_outage 유지. ※ 06:25 재확인에서 `gemma3-270m:free`가 다시 degraded로 전환 — 현재 정상 5종 (`gemma3-270m:free` 제외). 상태가 시간 단위로 뒤집히는 중이라 사용 전 재확인이 안전 (출처: https://api.airforce/v1/models).
- 2026-10-07: 아침 워치 변동 없음 — OpenRouter(`:free` 16종 유지)·Nous Portal(무료 9종 유지)·Groq(한도 동일)·NVIDIA NIM(무료 4종)·OrcaRouter(무료 5종)·Token Harbor(무료 2종)·OpenCode Zen(무료 12종)·AnyAPI(Free 4종)·BazaarLink(무료 2종)·Gemini(API 무료 티어 유지, 10/09 앱 Flash-Lite 제한은 API에 영향 없음 재확인)·Mistral(Free 월 $10 크레딧 유지)·Ollama Cloud·Agnes AI($0 프로모션 유지)·AIHubMix·Hetzner(모델 2종·한도 유지)·ZeroLimitAI('Free week' 유지). 신규 상시 무료 제공자 없음.
- 2026-10-06: Groq — `openai/gpt-oss-safeguard-20b` 한도 추가 하향: RPM 5→3 (10/05 30→5에 이은 재하향). RPD 1K·TPM 2K·TPD 200K 유지, 나머지 무료 모델(gpt-oss-120b/20b·qwen3.8-27b) 한도 변동 없음 (출처: https://console.groq.com/docs/rate-limits).
- 2026-10-06: Api.Airforce — 상태 뒤집힘 지속 (18:00 확인): `rnj-1` major_outage→정상 복귀, `unmoderated-gpt` 정상→partial_outage, `glm-4.7-flash` major_outage→partial_outage, `gemma3-270m:free`는 major_outage 유지. 정상 호출 가능 무료 모델은 여전히 4종이나 구성 변경 (`gpt-oss-20b`·`llama-instant`·`kimi-k2.7-code`·`rnj-1`), 대표 모델에서 `unmoderated-gpt`→`rnj-1`로 교체. 사용 전 재확인 권장 (출처: https://api.airforce/v1/models).
- 2026-10-06: 저녁 워치 변동 없음 — OpenRouter(`:free` 16종 유지)·Nous Portal(무료 9종 유지)·AnyAPI(Free 4종 유지)·LLM7.io(turbo 7종 유지)·OrcaRouter(무료 5종 유지)·Token Harbor(무료 2종 유지)·BazaarLink(무료 2종 유지)·OpenCode Zen(무료 12종 유지)·Gemini(API 무료 티어 유지)·NVIDIA NIM(무료 4종 유지)·Mistral(Free 월 $10 크레딧 유지)·Hetzner(아침 반영 유지). 신규 상시 무료 제공자 없음.
- 2026-10-06: 신규 후보 Routeway 발견 (보류 — 형님 판단 대기): OpenAI 호환 게이트웨이, `:free` 9종 라이브 확인 (`deepseek-v4-flash:free`·`minimax-m2.7:free`·`muse-glimmer-30b:free`·gemma-4-26b-a4b-it 5종 persona variant), 5 RPM/200 RPD (3자 검증 2026-09-28 기준). 단, 카드 요구 관련 자료가 상충 — FAQ는 결제 단계 없음 vs 이용약관은 결제 수단 요구 명시 (봇 차단으로 직접 확인 불가) → Tracker 범위(카드 불필요 상시 무료) 충족 여부가 불확정이라 반영 보류 (출처: https://api.routeway.ai/v1/models, https://mvalentsev.github.io/awesome-free-ai-coding/providers/routeway/).
- 2026-10-06: OpenRouter — `qwen/qwen3.8-27b:free`가 유료 전용으로 전환 확인 (유료 `qwen/qwen3.8-27b`만 잔류, 입력 $0.425/1M), 대표 모델에서 `nemotron-3-super-120b-a12b:free`로 교체. `:free` 16종 (10/03 17종에서 축소). `stealth/space-bunny-alpha`는 만료일 2026-10-05 경과 후 카탈로그에서 완전 제거 확인 (출처: https://openrouter.ai/api/v1/models).
- 2026-10-06: Nous Portal — `stealth/space-bunny-alpha` 카탈로그에서 완전 제거 확인 (만료일 2026-10-05 경과) — 기간 한정 요약표에서 정리. `upstage/solar-mini4:free`가 무료로 신규 등재. 무료 9종 유지 (space-bunny-alpha 제외 → solar-mini4 추가). `inclusionai/ling-3.1-flash`는 $0 등재 유지 (2주 체험 ~10/13~14 예상) (출처: https://inference-api.nousresearch.com/v1/models).
- 2026-10-06: AnyAPI — `Qwen3.8 27B (free)`가 Free 티어로 신규 등재 확인 (Free 뱃지 직접 확인), Free 3종→4종. 라인업이 하루 새 뒤집히는 패턴 반복 (출처: https://anyapi.ai/ai-models).
- 2026-10-06: Api.Airforce — `rnj-1` major_outage 재전환, `gpt-oss-20b` degraded→정상 복귀, `glm-4.7-flash` major_outage 지속. 06:00 확인 기준 정상 5종(`gpt-oss-20b`·`llama-instant`·`gemma3-270m:free`·`kimi-k2.7-code`·`unmoderated-gpt`)이었으나 06:15 재확인에서 `gemma3-270m:free`가 다시 major_outage로 전환 — 현재 정상 4종 (`gpt-oss-20b`·`llama-instant`·`kimi-k2.7-code`·`unmoderated-gpt`). 상태가 계속 요동 (출처: https://api.airforce/v1/models).
- 2026-10-06: Hetzner Inference API — 공식 모델 2종으로 확대: `Qwen3.8-27B` (Dense, 262K 컨텍스트, 텍스트·이미지, Apache 2.0) 신규 확인. 한도 변경: 60초당 입력 300만→400만 토큰·출력 6만→10만 토큰 + 60초당 10회 요청 제한 추가, 기존 "24시간당 입력 5억·출력 500만 토큰" 표기 삭제 (출처: https://docs.hetzner.com/general/company-and-policy/experiments/inference/).
- 2026-10-06: Gemini — 10/09부터 Gemini 앱(소비자) 무료 사용자는 Flash-Lite만 제공, Flash·Pro는 구독 필요 (공식 지원 페이지·보도 기준, 10/04 기준선에 이미 반영된 소식을 효력 시점으로 확정). Gemini API(AI Studio) 무료 티어에는 영향 없음 — 무료 텍스트 모델(gemini-3.8-flash·gemini-3.5-flash-lite) 유지 (출처: https://tpsreport.news/news/gemini-free-tier-flash-lite-only-ai-plus-loses-pro, https://www.aifreeapi.com/en/posts/google-gemini-api-free-tier).
- 2026-10-06: 변동 없음 — Groq(한도 동일)·NVIDIA NIM(무료 4종)·OrcaRouter(무료 5종)·LLM7.io(turbo 7종)·Token Harbor(무료 2종)·OpenCode Zen(무료 12종)·BazaarLink(무료 2종)·Mistral(Free 월 $10 크레딧 유지)·Ollama Cloud·Agnes AI($0 프로모션 유지)·AIHubMix·ZeroLimitAI('Free week' 유지). 신규 상시 무료 제공자 없음.

- 2026-10-05: Groq — `openai/gpt-oss-safeguard-20b` 한도 하향 (RPM 30→5, TPM 8K→2K; RPD 1K·TPD 200K 유지). 나머지 무료 모델(gpt-oss-120b/20b·qwen3.8-27b)은 한도·목록 변동 없음 (출처: https://console.groq.com/docs/rate-limits).
- 2026-10-05: Gemini — TTS 모델 2종(`gemini-3.8-flash-tts`·`gemini-3.8-flash-lite-tts`) Free Tier "Free of charge"로 GA 확인 (2026-09-22 changelog, 18:00 가격표 직접 확인 — 기준선 미기록분). 음성 합성 전용이라 Hermes 채팅 연결 대상 아님, 대표 모델 변경 없음 (출처: https://ai.google.dev/gemini-api/docs/pricing, https://ai.google.dev/gemini-api/docs/changelog).
- 2026-10-05: Api.Airforce — 정상 가용 무료 모델 5종 로테이션: `gemma3-270m:free` major_outage→정상 복귀·`rnj-1` 정상 유지, 반면 `kimi-k2.7-code`·`glm-4.7-flash` major_outage 전환 (18:07 확인). 그러나 18:15경 라이브 재확인에서 `gemma3-270m:free`→major_outage로 재장애, `kimi-k2.7-code`→정상 복귀. 현재 정상 5종 `gpt-oss-20b`·`rnj-1`·`unmoderated-gpt`·`kimi-k2.7-code`·`llama-instant`. 상태가 계속 요동 (출처: https://api.airforce/v1/models).
- 2026-10-05: `space-bunny-alpha` — 만료일 2026-10-05 도래. 그러나 18:00 KST 현재 OpenRouter·Nous Portal 양쪽 카탈로그 모두 $0로 여전히 등재 중 (expiration_date=2026-10-05, 언제든 제거 가능) — 실제 제거 확인 시 목록에서 정리 예정 (출처: https://openrouter.ai/api/v1/models, https://inference-api.nousresearch.com/v1/models).
- 2026-10-05: AIHubMix 신규 등록 — 800+ 모델 게이트웨이, 27종 이상 $0 제공 (공식 문서 'No trial expiry'), 카드 불필요, OpenAI 호환 (형님 승인).
- 2026-10-05: '기간 한정 무료' 섹션 신설 — ZeroLimitAI('Free week — $0 for 7 days' 전환으로 상시 무료 범위 제외)를 상시 목록에서 이동, Hetzner Inference API(실험 단계 무료·종료일 미정) 신규 등록. OpenCode Zen·ling-3.1-flash·space-bunny-alpha·Cline은 요약표로 정리 (형님 승인).
- 2026-10-05: Intern-AI Discovery API 제외 확정 — 범용 채팅 API(OpenAI SDK 호환)는 맞으나 공식 무료 쿼터 미게시·휴대폰 번호 연동+화이트리스트 가입 구조라 Tracker 범위 미충족. 공식 무료 티어 게시 시 재검토 (출처: https://internlm.intern-ai.org.cn/api/document).
- 2026-10-05: Token Harbor — `qwen3.8-flash:free` 무료 프로모 종료 확인 (2026-10-04 13:00 UTC 경과, Free 목록에서 제거 → 유료 "value" 티어 $0.15/1M 입력으로 전환, isFree:false). 무료 2종 (`deepseek-v4.1-flash:free`·`mimo-v2.6-flash:free`)으로 축소, 대표 모델에서 제외 (출처: https://tokenharbor.ai/models?category=free).
- 2026-10-05: Api.Airforce — `unmoderated-gpt` major_outage→정상 복귀, `glm-4.7-flash` partial_outage→정상 복귀, `rnj-1`도 major_outage→정상 복귀 (06:15 확인). 그러나 06:30경 라이브 재확인에서 `rnj-1`이 다시 major_outage로 복귀 — 정상 호출 가능 무료 모델 6종→5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`glm-4.7-flash`·`llama-instant`·`unmoderated-gpt`). Airforce 상태는 계속 요동 (출처: https://api.airforce/v1/models).
- 2026-10-05: 변동 없음 — OpenRouter(:free 17종)·LLM7.io(turbo 7종)·Nous Portal(무료 9종)·OrcaRouter(무료 5종)·BazaarLink(무료 2종)·OpenCode Zen(무료 12종)·AnyAPI(Free 3종)·Groq·NVIDIA NIM·Gemini·Mistral·Ollama Cloud. ZeroLimitAI는 여전히 'Free week' 표기 (형님 판단 대기 유지). `space-bunny-alpha`는 OpenRouter·Nous Portal 모두 여전히 $0 등재 (만료일 2026-10-05 — 저녁 워치에서 만료 확인 예정). 신규 상시 무료 제공자 없음.

- 2026-10-04: ZeroLimitAI — 공식 개발자 페이지의 무료 표기가 기준선의 "Free — $0 forever"(10/03)에서 "Free week — $0 for 7 days"(7일 체험 후 유료 플랜 필요, 체험 종료 시 402 upgrade_required)로 변경 확인. 기준선 '영구 무료 티어' 표기와 상충 → Tracker 범위(상시 무료 제공자만 추적) 적용 여부를 형님께 질문 예정, 이번 워치에서는 섹션 미변경 (출처: https://www.zerolimitai.com/developers).
- 2026-10-04: Ling-3.1-flash 무료 성격 확인 — 2026-09-30 출시 2주 무료 체험 (체험 종료 ~10/13~14 예상, 이후 유료 전환·오픈소스 공개 예정 — TechNode 보도). Nous Portal·OpenCode Zen의 무료 등재도 체험 종료와 함께 끝날 가능성, 다음 워치에서 지속 확인 (출처: https://technode.com/2026/09/30/ant-group-launches-ling-3-1-flash-with-560-billion-parameters/).
- 2026-10-04: AnyAPI — Ling 3.0 Flash Fin (free)이 오전 Premium 표기에서 저녁에 Free 티어로 복귀 — Free 2종→3종 (Sante·Fin·Qwen2.5 Coder 32B Instruct). 하루 새 뒤집힌 라인업이라 불안정 (출처: https://anyapi.ai/ai-models).
- 2026-10-04: Api.Airforce — `rnj-1` major_outage→정상 복귀, `unmoderated-gpt`는 partial_outage→major_outage로 악화. 정상 호출 가능 무료 모델 4종→5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`glm-4.7-flash`·`llama-instant`·`rnj-1`) (출처: https://api.airforce/v1/models).
- 2026-10-04: 변동 없음 — OpenRouter(:free 17종)·LLM7.io(turbo 7종)·Nous Portal(무료 9종)·OrcaRouter(무료 5종)·BazaarLink(무료 2종)·OpenCode Zen(무료 12종)·Groq·Gemini·Mistral. Token Harbor `qwen3.8-flash:free`는 여전히 Free 등재 (13:00 UTC=22:00 KST 만료 예정 — 내일 아침 워치에서 만료 확인).

- 2026-10-04: OpenCode Zen — 무료 목록 12종으로 교체: `fledge-alpha-free`(신규 스텔스 모델, 10/01 등장 — 커뮤니티에서 Thinking Machines Inkling 연관 추정)·`ling-3.1-flash-free`(신규) 추가 (출처: https://opencode.ai/docs/zen/, https://www.youtube.com/watch?v=4Zb9my4MI3U).
- 2026-10-04: Api.Airforce — `glm-4.7-flash` 18:00 정상에서 18:06 라이브 확인 기준 partial_outage로 재악화, 정상 호출 가능 무료 모델 5종→4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`rnj-1`). Airforce 상태는 분 단위로 뒤집히는 중 (출처: https://api.airforce/v1/models).
- 2026-10-04: AnyAPI — 무료 티어 4종→2종으로 축소: Ling 3.0 Flash Fin이 Premium 티어로 변경, Gemma 3n 4B는 카탈로그 목록에서 완전 제거 확인 (10/02~10/03 '제거 미확정'에서 제거 확정으로 전환). Free 잔류: Ling 3.0 Flash Sante·Qwen2.5 Coder 32B Instruct (출처: https://anyapi.ai/ai-models).
- 2026-10-04: Api.Airforce — `llama-instant` degraded→정상 복귀, `glm-4.7-flash` major_outage→정상 복귀. 반면 `rnj-1`은 정상→major_outage, `gemma3-270m:free`는 정상→major_outage로 다시 장애. 정상 호출 가능 무료 모델 4종 (`gpt-oss-20b`·`kimi-k2.7-code`·`glm-4.7-flash`·`llama-instant`), 대표 모델에서 `rnj-1`→`llama-instant`로 교체 (출처: https://api.airforce/v1/models).
- 2026-10-04: Nous Portal — 무료 9종: `inclusionai/ling-3.1-flash`가 공식 API에서 input/output $0.00 확인되어 무료 확정 (10/03까지는 $0 표시이나 :free 명칭 없어 미확정). `space-bunny-alpha`는 여전히 무료 등재이나 10/05 만료 예정 유지 (출처: https://inference-api.nousresearch.com/v1/models).
- 2026-10-04: 뉴스 확인 — 10/09 Google AI(소비자) 플랜 개편은 Gemini 앱 구독 변경이며 Gemini API(AI Studio) 무료 티어 변경은 아님 (API 무료 티어 "Free of charge" 유지) → API 무료 티어 후속 영향 여부 모니터링. 신규 상시 무료 제공자 등장 없음. 변동 없음: OpenRouter(:free 17종)·LLM7.io(turbo 7종)·OrcaRouter(무료 5종)·BazaarLink(무료 2종)·Token Harbor(`qwen3.8-flash:free` 아침 현재 무료 유지, 13:00 UTC=22:00 KST 만료 예정은 저녁 워치에서 확인) (출처: https://www.neowin.net/news/just-days-after-gemini-argon-launch-google-updates-ai-plans-to-limit-free-use-significantly/).
- 2026-10-03: 신규 제공자 BazaarLink 추가 — 영구 무료 티어("Free — No Credit Card Required", 카드 불필요), `qwen/qwen3.7-flash`·`deepseek/deepseek-v4-flash-0731free` 2종 (24시간 프로브 100%), 무충전 계정 10 RPM·일 60 가중 단위, OpenAI 호환 (출처: https://bazaarlink.ai/free).
- 2026-10-03: Api.Airforce — `llama-instant` 정상→degraded(저하), `gemma3-270m:free` major_outage→정상 복귀. 정상 호출 가능 무료 모델은 `rnj-1`·`kimi-k2.7-code`·`gpt-oss-20b`·`gemma3-270m:free` 4종 (출처: https://api.airforce/v1/models).
- 2026-10-03: AnyAPI — Gemma 3n 4B 무료 목록 여부 10/03 저녁에도 확인 불가 (카탈로그 페이지 텍스트에 모델명 미노출, Free 뱃지 매핑 불가) — 제거 미확정 유지, 다음 워치 재확인.
- 2026-10-03: 신규 제공자 ZeroLimitAI 추가 — 영구 무료 티어("Free — $0 forever", 카드 불필요), 가입 후 첫 주 일 100회 → 이후 일 50회 영구, OpenAI 호환·도구 호출 지원·`auto` 자동 라우팅 + 장애 시 폴오버 (출처: https://www.zerolimitai.com/developers).
- 2026-10-03: 신규 제공자 Agnes AI 추가 — `agnes-2.5-flash`·`agnes-3.0-flash` 현재 $0 (프로모션, "Promotional end dates are subject to Agnes AI platform announcements" — 종료 시 유료 전환 가능), 카드 불필요 (출처: https://agnes-ai.com).
- 2026-10-03: AnyAPI — Gemma 3n 4B가 무료 목록 텍스트에 미노출 (상세 페이지 존재 → 제거 미확정, 다음 워치 재확인).
- 2026-10-03: Token Harbor — `qwen3.8-flash:free` 무료 기한 2026-10-04 13:00 UTC 종료 예정 (3자 자료 기준), 10/04 저녁 워치에서 만료 확인 필요 (출처: https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/token-harbor.md).
- 2026-10-03: OpenRouter — `:free` 17종 확인. 10/01에 제거됐던 `nemotron-3-super-120b-a12b:free`·`cohere/north-mini-code:free`·`liquid/lfm-2.5-2.6b:free` 복귀 + `apodex/apodex-1.1-mini:free`·`nvidia/nemotron-3.5-lightning:free`·`thinkingmachines/inkling-small:free`·`poolside/laguna-s-2.1:free`·`thinkingmachines/inkling:free`·`poolside/laguna-xs-2.1:free`·`nvidia/nemotron-3.5-content-safety:free`·`nvidia/nemotron-3-ultra-550b-a55b:free`·`nvidia/nemotron-3-nano-omni-30b-a3b-reasoning:free`·`google/gemma-4-26b-a4b-it:free`·`google/gemma-4-31b-it:free` 신규 등재. 대표 3종 유지 (출처: https://openrouter.ai/api/v1/models).
- 2026-10-03: Nous Portal — 무료 라인업 로테이션 복귀: 10/01 저녁에 제거됐던 `stepfun/step-3.7-flash:free`·`poolside/laguna-xs-2.1:free`·`inclusionai/ling-3.0-flash-fin:free`·`meituan/longcat-2.0:free`·`meituan/longcat-2.5-preview:free` 5종의 무료 variant 재등장, 무료 8종. `upstage/solar-pro4:free`는 :free variant가 카탈로그에 없음 (유료 variant만 유지). `space-bunny-alpha` 2026-10-05 만료 예정 유지 (출처: https://inference-api.nousresearch.com/v1/models).
- 2026-10-03: LLM7.io — turbo(무료) 티어에 `nemotron-3-nano:30b` 추가, 총 7종 (출처: https://api.llm7.io/v1/models).
- 2026-10-02: LLM7.io — turbo(무료) 티어에 `DeepSeek-V4-Flash-0731`(400K 컨텍스트·도구 호출·추론 지원)·`gpt-oss:20b`·`minimax-m2.7` 3종 추가, 총 6종. `minimax-m2.7`은 10/01 카탈로그 제거 후 복귀. `deepseek-v4-flash:0731`(소문자)은 별개 ID로 pro 유지 (출처: https://api.llm7.io/v1/models).
- 2026-10-01: Nous Portal 무료 라인업 축소 — 기준선 9종 중 `stepfun/step-3.7-flash:free`·`poolside/laguna-xs-2.1:free`·`inclusionai/ling-3.0-flash-fin:free`·`upstage/solar-pro4:free`·`meituan/longcat-2.0:free`·`meituan/longcat-2.5-preview:free` 6종의 무료 variant 제거 확인 (일부 유료 variant는 유지), `stealth/space-bunny-alpha`는 2026-10-05 만료 예정 표시. `poolside/laguna-s-2.1:free`·`inclusionai/ling-3.0-flash-sante:free` 유지 (출처: https://inference-api.nousresearch.com/v1/models).
- 2026-10-01: OpenRouter — 대표 `:free` 모델 `nemotron-3-super-120b-a12b:free`·`cohere/north-mini-code:free`·`liquid/lfm-2.5-2.6b:free` 카탈로그에서 제거 확인 (전체 텍스트 대조), `ling-3.0-flash-sante:free`·`qwen3.8-27b:free`·`dots-3-note-preview:free` 유지 확인 (출처: https://openrouter.ai/api/v1/models).
- 2026-10-01: Api.Airforce — `unmoderated-gpt`가 partial_outage로 변경 (08:05 정상→18:00 부분 장애), 정상 호출 가능 무료 모델 5종→4종 (출처: https://api.airforce/v1/models).
- 2026-10-01: 신규 제공자 3곳 추가 — AnyAPI (Free $0/월·일 100K 토큰·카드 불필요 공식 명시, 공개 카탈로그 /ai-models에서 Free 티어 필터로 무료 목록 확인 가능), Api.Airforce (Free $0/월·분당 1회·일 1,000회 — 단 `tier:"free"` 28종 중 23종이 major_outage라 정상 호출 가능 무료 모델은 5종), Ollama Cloud (Free $0·starter 크레딧 월 리셋·이월 불가·동시 1요청, 도구 호출 공식 지원 확인 — starter 모델 목록·크레딧 금액은 미공개). LLMTR은 보류 유지 (출처: https://anyapi.ai/pricing, https://api.airforce/pricing, https://ollama.com/cloud).
- 2026-10-01: OrcaRouter 무료 라인업 로테이션 — `tencent/hy4-preview-free`(770B MoE·1M 컨텍스트)·`z-ai/glm-5.3-flash-free`·`orca/orcaverify-text1.0-free` 추가, `deepseek/deepseek-v4-pro-free` 제거(모델 페이지 404). 무료 5종, Hacker 티어 정책 변화 없음 (출처: https://www.orcarouter.ai/models?price=free, 공개 API /api/public/models/{id} 직접 확인).
- 2026-10-01: LLM7.io — Free token 한도 변경(24시간 토큰 100만→10만, 분당 60회·시간 250회, 익명 티어 표기 삭제) + turbo 무료 모델 3종(`GLM-5.3-Flash`·`codestral-latest`·`mistral-Nemo-Instruct-2407`) 확정. `minimax-m2.7` 카탈로그 제거, `deepseek-v4-flash:0731`→pro 티어 (출처: https://docs.llm7.io/limits, https://api.llm7.io/v1/models 라이브 직접 확인).
- 2026-10-01: Token Harbor 무료 라인업 로테이션 — `mimo-v2.6-flash:free`·`qwen3.8-flash:free`로 교체, `deepseek-v4-flash:free` 제거. `deepseek-v4.1-flash:free` 유지 (출처: https://tokenharbor.ai/models?category=free).
- 2026-09-30: GitHub Models 섹션 제거 — 2026-07-30 공식 체인지로그 기준 완전 퇴역 (플레이그라운드·추론 API·BYOK 전부 종료), Hermes 연동 불가 확정 (출처: https://github.blog/changelog/2026-07-30-github-models-is-now-retired/).
- 2026-09-30: Nous Portal 무료 모델 9종으로 갱신 — `meituan/longcat-2.5-preview:free` 추가 (라이브 확인). `step-3.7-flash:free`는 10/01 만료설과 무관하게 무료 등재 유지 (출처: https://portal.nousresearch.com/models).
- 2026-09-30: Gemini — 2026-09-18 공식 공지 기준 2.5 모델(`gemini-2.5-flash`/`gemini-2.5-flash-lite`/`gemini-2.5-pro`) 무료 접근을 기존 실사용자로 제한, 신규 프로젝트/키는 `gemini-3.5-flash-lite`·`gemini-3.8-flash` 사용 권장 (출처: https://ai.google.dev/gemini-api/docs/changelog).
- 2026-09-30: NVIDIA NIM — `llama-3.3-70b-instruct` 전면 무료 라인업 노출 제외 (무료 종료 여부는 공식 미확인), 나머지 4종(kimi-k3·deepseek-v4-pro-0813·nemotron-3-ultra-550b-a55b·nemotron-3.5-lightning-30b-a3b)은 직접 확인으로 확정 (출처: https://build.nvidia.com).
- 2026-09-29: NVIDIA NIM 대표 모델 교체 — 공식 'Free inference' 라인업 4종, 한도에 '분당 최대 40회 + 일 10,000회' 추가 (3자 인용). 비고에 2026-09-07 3자 프로브 주석 추가 (출처: https://build.nvidia.com).
- 2026-09-29: OpenRouter 대표 3종 교체 — DeepSeek R1·Llama 3.3 70B·Qwen3 Coder의 `:free` 버전 유료 전용 전환 확인, `nemotron-3-super-120b-a12b:free`·`cohere/north-mini-code:free`·`ling-3.0-flash-sante:free`로 교체. Thinking Machines Inkling은 일반 API 호출에 403을 반환하므로 Hermes 직접 연결 폴백에서 제외 권장 (출처: https://openrouter.ai/api/v1/models).
- 2026-09-29: OrcaRouter — `deepseek/deepseek-v4-pro-free` 무료 풀 제외 확인 (출처: https://www.orcarouter.ai/api/pricing). `z-ai/glm-5.3-flash-free` 무료 티어 신규 추가 (9/7 무료 티어에서 Qwen3.8-27B 대체). `qwen3.8-27b-free` 딜리스트 확인 (출처: https://runtimewire.com/article/orcarouter-glm-5-3-flash-free-tier).
- 2026-09-29: Token Harbor — 대표 모델 조정: `mimo-v2.5:free` → `mimo-v2.6-flash:free`, `TH-Rudder` Free 플랜 Includes 신규 표시 (출처: https://tokenharbor.ai/pricing). 한도에 분당 60회·시간당 1,800회 제한 확인 (2026-09-28 3자 재검증).
- 2026-09-29: [철회] Token Harbor '미사용분 이월 불가' 정정 — 공식 근거 없음 확인 (해당 문구는 유료 Pass 설명의 것) → 원문 '이월 여부 상충' 유지.

- 2026-09-28: Cerebras·Fireworks AI 섹션 제거 — 일회성 체험 크레딧 제공자는 조사 대상 아님 (Tracker 범위 확정: 상시 무료로 쓸 수 있는 제공자만 추적).

- 2026-09-27: Nous Portal '더보기' 링크를 /models로 정정 — Free Models 섹션·FREE 필터로 무료 8종 직접 확인 (Space Bunny Alpha 포함, 형님 확인 요청 반영).
- 2026-09-27: OpenCode Zen 스텔스 모델(Big Pickle, Space Bunny) 관련 정보 링크 추가 — 벤치마크 측정·지문 분석, Nous Portal 무료 제공 교차 안내.
- 2026-09-27: OpenCode Zen 무료 모델 목록 갱신 — 공식 문서 'The free models' 섹션 기준 10종으로 교체 (space-bunny-free, longcat-2.5-preview-free, mimo-v2.6-flash-free, jev-1.13-free 추가). 대표 모델 ID도 실제 무료 ID(`-free` 접미사)로 정정. 외부 하네스 403 차단은 유지 (출처: https://opencode.ai/docs/zen/).
- 2026-09-27: '더보기' 공식 링크 점검·교체 — Groq→한도 문서, OrcaRouter→무료 필터 페이지, Gemini→가격 페이지, Mistral→가격 페이지(Experiment 문구 정정), LLM7.io→모델 카탈로그 API, Nous Portal→Portal 가격 목록, NVIDIA→'Free inference' 섹션 안내. OpenRouter·OpenCode Zen·Token Harbor는 기존 링크로 무료 목록 확인이 가능해 유지, GitHub Models는 퇴역 확정으로 제거 제안 대기 중이라 제외.
- 2026-09-25: Cerebras — '카드 불필요' 표기 정정: verified payment method 추가 후에만 $5 크레딧 지급(30일 유효), 추가 전 API/Playground 접근 비활성, 공식 문서에 "상시 무료 티어 없음" 명시 — 카드 없는 무료 조합에서 실질 제외 (출처: https://inference-docs.cerebras.ai/support/rate-limits).
- 2026-09-25: Mistral — 한도 표기를 공식 기준으로 정정: Experiment 티어 수치(커뮤니티 보고, 초당 1회/월 10억 토큰) → Free 플랜 월 $10 API 크레딧 (출처: https://mistral.ai/pricing).
- 2026-09-24: OpenCode Zen 무료 티어, 2026-09-17부터 OpenCode 외부 하네스에서 403 차단 확정 (maintainer 확인) — 우선순위 중간→낮음으로 하향, Hermes 무료 연동 불가로 비고 수정 (출처: https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/opencode.md).
- 2026-09-24: Groq 무료 테이블에서 Llama 채팅 모델 제외 확인 — 대표 모델을 gpt-oss-120b/20b, qwen3.8-27b로 교체 (출처: https://console.groq.com/docs/rate-limits).
- 2026-09-24: 신규 제공자 2곳 추가 — Token Harbor (DeepSeek V4.1 Flash 무료 라우트, $0 플랜), Nous Portal (Hermes Agent 제작사의 공식 포털, Free $0 플랜) (출처: https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/token-harbor.md).
- 2026-09-24: 표시 형식 개선 — 성능 비교 설명을 링크 하위 중첩 접기 블록으로 변경, 변경 이력 접기 블록화, 목차·앵커 이동 기능 추가, 제공자 스펙 라벨 굵게 처리.
- 2026-09-24: AA 비교 링크를 대표 무료 3종으로 교체 (DeepSeek V4.1 Flash 적용, models 파라미터 제거).
- 2026-09-24: 성능 비교 섹션에 대표 모델 선정 기준 안내(접기 블록) 추가.
- 2026-09-24: 성능 비교 링크에서 프론티어 모델 파라미터 제거 (무료 모델만), 상단 표 3종 + 하단 차트 4종 구성.
- 2026-09-24: 성능 비교 링크를 상단 표(compare=, 5종) + 하단 차트(models=, 7종) 복합 형태로 개선.
- 2026-09-24: 성능 비교에 파라미터 포함 비교 링크 추가 (추천 무료 4종 + 프론티어 3종), 더보기 뒤 빈 줄 추가로 목록 서식 수정.
- 2026-09-24: 기준선 최초 작성 (11개 제공자).
- 2026-09-24: 파일 형식 개편 — 제공자를 사용 우선순위 순으로 정렬, 각 제공자 대표 모델 3개 + 나머지 '더보기' 접기 구조 적용, Cline을 '연동 불가' 섹션으로 분리.
- 2026-09-24: 페이지 피드백 반영 — 대표 모델 목록화, 더보기 공식 링크화, 우선순위 색상 뱃지, 성능 비교 섹션 추가.

<!-- 작성 규칙: `- YYYY-MM-DD: 변경 내용 (출처: URL)` 형식으로 한 줄 요약. 본문은 항상 최신 상태로 유지하고, 바뀐 사실만 여기에 날짜순으로 추가함. -->

</details>
