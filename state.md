# Free LLM Tracker — 기준선 (2026-10-08)

<p class="notice">
Hermes Agent(OCI 무료 인스턴스)에 연결할 무료 LLM API 제공자 조사 기준선.<br>
모든 수치는 2026-10-08 기준 공식 문서·가격 페이지 또는 3자 검증 자료 기준이며,<br>
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
- [Mistral](#mistral)
- [OpenRouter](#openrouter)
- [AIHubMix](#aihubmix)
- [Z.ai](#z-ai)
- [LLM7.io](#llm7)
- [OpenCode Zen](#opencode-zen)
- [Token Harbor](#token-harbor)
- [Nous Portal (Hermes Agent)](#nous-portal)
- [AnyAPI](#anyapi)
- [Api.Airforce](#api-airforce)
- [Ollama Cloud](#ollama-cloud)
- [Agnes AI](#agnes-ai)
- [BazaarLink](#bazaarlink)
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
- **비고**: 속도 매우 빠름 (LPU, 300~1000+ tok/s). 완전 무료 조합의 메인 후보.

<a id="nvidia-nim"></a>

## NVIDIA NIM (build.nvidia.com) <span class="prio p-high">높음</span>

- **대표 무료 모델 (사용성 순):**
  - `moonshotai/kimi-k3` — function calling 광고 (2026-09-30 공식 무료 라인업 확인)
  - `deepseek-ai/deepseek-v4.1-flash` — 고속 플래그십 (2026-10-09 무료 라인업 교체 확인)
  - `nvidia/nemotron-3-ultra-550b-a55b` — 초대형 MoE (2026-09-30 확인)
  - `nvidia/nemotron-3.5-lightning-30b-a3b` — 경량 고속 (2026-09-30 확인)
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 무료 추론 모델: [build.nvidia.com](https://build.nvidia.com) — 'Free inference with leading models' 섹션에서 확인 (예고 없이 변경됨, 2026-10-09 기준 4종: `moonshotai/kimi-k3`, `deepseek-ai/deepseek-v4.1-flash`, `nvidia/nemotron-3.5-lightning-30b-a3b`, `nvidia/nemotron-3-ultra-550b-a55b`). `deepseek-ai/deepseek-v4-pro-0813`은 2026-10-09 확인에서 `deepseek-ai/deepseek-v4.1-flash`로 교체됨.
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

- **대표 무료 모델 (사용성 순, 2026-10-01 기준 — 로테이션됨):**
  - `tencent/hy4-preview-free` — 770B MoE·1M 컨텍스트, 최신 (2026-10-01 공개 API 직접 확인)
  - `deepseek/deepseek-v4-flash-free` — 고속
  - `tencent/hy3-free` — 무료 풀 잔류
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 무료 5종 (2026-10-01 공개 API 직접 확인): `deepseek/deepseek-v4-flash-free`, `tencent/hy3-free`, `tencent/hy4-preview-free`, `z-ai/glm-5.3-flash-free`, `orca/orcaverify-text1.0-free`. `deepseek/deepseek-v4-pro-free`는 무료 풀에서 제외됨 (모델 페이지 404).
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

<a id="mistral"></a>

## Mistral (이전 조사) <span class="prio p-mid">중간</span>

- **대표 무료 모델 (사용성 순):**
  - Mistral Large 계열 — 최상위 성능
  - Codestral — 코드 특화
  - Mistral Small 계열 — 경량·고속
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - Free 플랜(월 $10 API 크레딧)으로 이용 — Studio·API·Vibe 공유.
  - 전체 모델 목록: [Mistral 가격 페이지](https://mistral.ai/pricing)

  </details>

- **한도**: Free 플랜 — 월 $10 API 크레딧 (공식 가격 페이지 기준, 2026-09-24 검증). Studio·API·Vibe 공유, 초과 시 다음 결제 주기까지 중단 (PAYG 전환 시 예외). 무료 모드는 가장 낮은 속도 제한 적용 (정확한 수치는 계정 내 표시). ※ 2026-10-08 18:00 직접 확인: 가격 페이지가 Vibe(Pro $14.99/월·Team $24.99/사용자/월) 중심으로 개편되어 Free 플랜의 "월 $10 API 크레딧" 문구가 사라짐 — 10/09 아침·저녁 재확인에서도 문구 없음 (3회 연속). Free 플랜 자체는 FAQ에 유지. 실제 제거인지 페이지 개편인지는 미확인 (형님 판단 대기).
- **API**: OpenAI 호환. 엔드포인트 `https://api.mistral.ai/v1`
- **도구 호출**: 지원
- **제한**: 카드 불필요. 학습 활용 위험 보고 있음.
- **출처**: https://console.mistral.ai (커뮤니티 검증 기준), https://mistral.ai/pricing
- **비고**: 월 $10 크레딧은 에이전트 실사용에 빠듯 (Mistral Large 기준 입력 약 2천만 토큰 수준). 데이터 정책 주의 (기본적으로 학습 활용 가능, Admin 패널 opt-out 필요).

<a id="openrouter"></a>

## OpenRouter (이전 조사) <span class="prio p-mid">중간</span>

- **대표 무료 모델 (사용성 순, 2026-10-09 06:00 기준 — 로테이션됨):**
  - `nvidia/nemotron-3-super-120b-a12b:free` — 120B 대형 (10/03 복귀 후 무료 잔류 확인)
  - `dots-studio/dots-3-note-preview:free` — 유지 확인 (최신 등록 구간에서 확인)
  - `cohere/north-mini-code:free` — 코딩 계열, 무료 잔류 확인 (10/09)
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 전체 무료 모델: [OpenRouter 모델 목록](https://openrouter.ai/models) — 무료 필터 사용 (모델명 끝에 `:free`, 로테이션됨)

  </details>

- **한도**: 분당 20회 / 일 50회 (누적 $10 이상 구매 시 일 1,000회)
- **API**: OpenAI 호환. 엔드포인트 `https://openrouter.ai/api/v1`
- **도구 호출**: 무료 라우트별 상이 (각 라우트의 supported_parameters 확인 필요)
- **제한**: 카드 불필요. 무료 라우트별 데이터 정책 상이 (일부는 학습 활용 경고 있음). upstream 429 빈발 보고.
- **출처**: https://buldrr.com/openrouter-free-api-keys-free-models-simple-guide/
- **비고**: Hermes 공식 문서의 기본값이라 설정 예제가 가장 풍부. 일 50회는 에이전트 실사용에 빠듯. $10 1회 충전 시 한도 20배 상승이 가성비 최고. 구 무료 모델(DeepSeek R1·Llama 3.3 70B·Qwen3 Coder 등)의 `:free` 버전은 2026-09-28 확인 기준 유료 전용으로 전환됨. 2026-09-29 18:00 라이브 스냅샷 기준 `:free` 16종 — `qwen3.8-27b:free`·`liquid/lfm-2.5-2.6b:free` 신규 등록. `inclusionai/ling-3.0-flash-fin:free`는 유료 전환 (input $0.06/1M, output $0.18/1M). 2026-10-03 06:00 라이브 확인: `:free` 17종 — 10/01에 제거됐던 `nemotron-3-super-120b-a12b:free`·`cohere/north-mini-code:free`·`liquid/lfm-2.5-2.6b:free`가 복귀하고, `apodex/apodex-1.1-mini:free`·`nvidia/nemotron-3.5-lightning:free`·`thinkingmachines/inkling-small:free`·`poolside/laguna-s-2.1:free`·`thinkingmachines/inkling:free`·`poolside/laguna-xs-2.1:free`·`nvidia/nemotron-3.5-content-safety:free`·`nvidia/nemotron-3-ultra-550b-a55b:free`·`nvidia/nemotron-3-nano-omni-30b-a3b-reasoning:free`·`google/gemma-4-26b-a4b-it:free`·`google/gemma-4-31b-it:free`가 신규 등재. `:free` 라인업은 일 단위 로테이션이므로 대표 교체는 유지 확인 기준으로만. `stealth/space-bunny-alpha`는 만료일 2026-10-05 경과 후 카탈로그에서 완전 제거됨 (2026-10-06 06:00 확인, OpenRouter·Nous Portal 양쪽) — 기간 한정 요약표에서 정리. `qwen/qwen3.8-27b:free`는 유료 전용으로 전환 확인 (유료 `qwen/qwen3.8-27b`만 잔류, 입력 $0.425/1M) → 대표 모델에서 `nemotron-3-super-120b-a12b:free`로 교체. 2026-10-06 06:00 라이브 확인: `:free` 16종. Thinking Machines Inkling은 에이전트 하네스에서만 응답하고 일반 API 호출에는 403을 반환하므로 Hermes 직접 연결 폴백에서 제외 권장 (2026-09-28 3자 검증). 2026-10-09 06:00 라이브 확인: `:free` 15종 — `inclusionai/ling-3.0-flash-sante:free`(당시 대표 #1)가 무료에서 제거됨. 잔류 15종 전부 pricing prompt/output "0" 확인.

<a id="aihubmix"></a>

## AIHubMix <span class="prio p-mid">중간</span>

- **대표 무료 모델 (2026-10-05 공식 무료 모델 문서 확인):**
  - `coding-glm-5.1-free` — 오픈소스 최초 SWE-bench Pro 1위 (58.4%), 코딩 특화
  - `gpt-5.5-free` — OpenAI 최신 플래그십 무료 제공
  - `xiaomi-mimo-v2.5-free` — 1M 컨텍스트·에이전트/도구 호출 특화
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 전체 목록: [AIHubMix 무료 모델 문서](https://docs.aihubmix.com/en/blogs/free-ai-models) — 27종 이상 (공식 문서 기준). 무료 ID는 전부 `-free` 접미사
  - 한도 (3자 검증, 2026-09-28): 모델별 일일 캡 — 최신 코딩 모델 5 RPM·일 100회·일 100만 토큰, 그 외 일 500회 수준. 일 리셋, 체험 만료 없음

  </details>

- **한도**: 모델별 일일 캡 (상단 더보기 참조), 일 리셋. 체험 만료 없음 (공식 문서 "No trial expiry")
- **API**: OpenAI 호환. 엔드포인트 `https://aihubmix.com/v1`. Anthropic 형식(`/v1/messages`)도 지원 — Claude Code 직접 연결 가능
- **도구 호출**: 지원 (코딩·에이전트 모델 중심, 모델별 상이)
- **제한**: **카드 불필요**. API 키는 사이트에서 발급
- **출처**: https://docs.aihubmix.com/en/blogs/free-ai-models
- **비고**: 800+ 모델 게이트웨이 중 27종 이상을 플랫폼이 비용 부담하며 $0 제공. 유료 플래그십(GPT-5.5·Gemini 3 등)을 무료로 쓸 수 있는 몇 안 되는 경로 (2026-10-05 형님 승인 등록).

<a id="z-ai"></a>

## Z.ai <span class="prio p-mid">중간</span>

- **대표 무료 모델 (사용성 순, 2026-10-07 공식 가격표 확인 — 3종 모두 영구 Free):**
  - `glm-4.7-flash` — 131K 컨텍스트·도구 호출·추론 지원, 코딩/에이전트에 가장 유망 (컨텍스트·도구 호출은 3자 확인)
  - `glm-4.5-flash` — 경량 텍스트 모델
  - `glm-4.6v-flash` — 비전(텍스트·이미지) 모델
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

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

- **대표 무료 모델 (사용성 순, turbo 티어 — 2026-10-09 06:00 라이브 API 직접 확인, turbo 10종):**
  - `DeepSeek-V4-Flash-0731` — 400K 컨텍스트·도구 호출·추론 지원 (에이전트 용도로 가장 유망)
  - `minimax-m2.7` — 180K 컨텍스트·도구 호출·추론 지원
  - `gpt-oss:20b` — 128K 컨텍스트·도구 호출 지원
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 2026-10-09 06:00 라이브 API 직접 확인 기준 turbo(무료) 티어 10종: `DeepSeek-V4-Flash-0731`, `GLM-5.3-Flash`, `codestral-latest`, `gpt-oss:20b`, `minimax-m2.7` (180K 컨텍스트·도구 호출·추론 지원), `mistral-Nemo-Instruct-2407`, `nemotron-3-nano:30b`, `gemma4:31b`, `glm-5.2`, `minimax-m3`. `deepseek-v4-pro`는 turbo→pro 티어로 강등 (유료 전환). 확인 직전 분 단위로 9→10→11종으로 변동 후 11종으로 안정 — 라인업이 로테이션 중이라 사용 전 재확인이 안전. `minimax-m2.7`은 10/01 카탈로그에서 제거됐다가 10/02 turbo로 복귀한 이력 있음. `deepseek-v4-flash:0731`(소문자·콜론 표기)은 별개 ID로 pro 티어 유지.
  - 전체 목록: [LLM7.io 모델 카탈로그](https://api.llm7.io/v1/models) — `tier: "turbo"` 행이 무료

  </details>

- **한도**: 무료 토큰(dash.llm7.io 발급) — 초당 1회 / 분당 60회 / 시간당 250회 / 24시간 100,000 토큰 (2026-10-01 공식 한도 문서 기준 — 24시간 토큰 허용량이 기존 100만에서 1/10로 축소됨). 익명(키 없음) 티어 표기는 공식 문서에서 사라짐 (삭제인지 표기 누락인지 미확인).
- **API**: OpenAI 호환. 엔드포인트 `https://api.llm7.io/v1`. 익명 사용 시 api_key에 "unused" 입력.
- **도구 호출**: 미확인
- **제한**: 카드·가입 불필요(익명 가능). 운영자가 upstream을 공개하지 않음. 무료 모델 구성이 변경될 수 있음.
- **출처**: https://docs.llm7.io/limits , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/llm7.md , https://github.com/velo4705/awesome-free-byok-models
- **비고**: Hermes 연결 가능. 가입 없이 바로 쓸 수 있어 테스트용으로 가장 간편. 단, 24시간 10만 토큰은 에이전트 루프 몇 바퀴면 소진이므로 에이전트 실사용 폴백으로는 사실상 부적합 — '가입 없이 짧게 시험' 용도로만 유효. 2026-10-07 아침 기준 turbo가 7종→11종으로 확대됐다가 2026-10-09 아침 기준 `deepseek-v4-pro`의 pro 강등으로 10종으로 축소 — 단, 확인 직전 분 단위 로테이션 중이라 사용 전 재확인 권장.

<a id="opencode-zen"></a>

## OpenCode Zen <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순, OpenCode 내부 전용):**
  - `big-pickle` — 스텔스 모델, 기간 한정 무료
  - `nemotron-3-ultra-free` — 기간 한정 무료
  - `muse-spark-1.3-contributor-free` — 데이터 제공 대가 무료 행
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 무료 모델 목록: [OpenCode Zen 문서](https://opencode.ai/docs/zen/) — 가격표 "Free" 행 기준 (로테이션됨). 2026-10-09 기준 13종: `ling-3.1-flash-free` (Ling-3.1-flash 출시 2주 무료 체험, ~10/13~14 종료 예상), `mimo-v2.6-flash-free`, `mimo-v2.5-free`, `ling-3.0-flash-fin-free`, `nemotron-3-ultra-free`, `nemotron-3.5-lightning-free`, `big-pickle`, `space-bunny-free`, `longcat-2.5-preview-free`, `muse-spark-1.3-contributor-free`, `jev-1.13-free`, `exo-free` (10/08 신규 확인, 입·출력 모두 Free, 상세 스펙 미공개), `step-5-preview-free` (10/09 신규 — 가격표 Free 행 입·출력·캐시 읽기 모두 Free, "free on OpenCode for a limited time", zero-retention). `fledge-alpha-free`는 10/09 확인에서 Free 목록에서 제거됨 (전부 기간 한정)
  - 스텔스 모델 관련 정보:
    - Big Pickle: [SWE Atlas 벤치마크 측정](https://github.com/PhillipChaffee/big-pickle-swe-atlas) — 코드베이스 QnA 50.8% 해결률 (정체 미공개, 커뮤니티에서는 GLM-4.6 추정)
    - Space Bunny: [지문 분석](https://github.com/majiayu000/stealthprint/blob/main/docs/case-space-bunny.md) — MiniMax 계열 토크나이저, 1M 컨텍스트 확인. Space Bunny Alpha는 2026-10-05 만료 후 OpenRouter·Nous Portal 양쪽 카탈로그에서 제거 확인 (OpenCode Zen의 `space-bunny-free`와는 별개 ID)
    - Fledge Alpha: [정체 분석 영상](https://www.youtube.com/watch?v=4Zb9my4MI3U) — 2026-10-01 등장, Thinking Machines Inkling 프로젝트와 연결 (PR 추적 기준 '추정'). [OpenCode 데이터 페이지](https://opencode.ai/data/unknown/fledge-alpha). ※ 2026-10-09 확인에서 Zen Free 목록에서 제거됨

  </details>

- **한도**: 커뮤니티 보고 기준 일 약 100회 요청 (공식 문서에 무료 티어 수치 미기재 → 미확인)
- **API**: OpenAI 호환. 엔드포인트 `https://opencode.ai/zen/v1` — 단, **무료 티어는 OpenCode 외부 하네스에서 사용 불가**
- **도구 호출**: 지원 (3자 검증 기준)
- **제한**: **2026-09-17부터 무료 티어가 OpenCode가 아닌 모든 클라이언트를 403으로 차단** (`FreeTierError: OpenCode's free tier can only be used from within OpenCode`) — 2026-09-18 OpenCode maintainer가 "무료 티어는 다른 하네스에서 사용 불가" 확인. Hermes 등 외부 하네스에서 무료 티어 사용 불가 확정. 무료 모델 데이터가 학습에 활용될 수 있음.
- **출처**: https://opencode.ai/docs/zen/ , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/opencode.md , https://github.com/decolua/9router/issues/4103
- **비고**: Hermes에서 Zen 무료 티어는 쓸 수 없으므로 폴백 후보에서 제외. 유료 Zen 잔액이 있으면 연동 가능.

<a id="token-harbor"></a>

## Token Harbor <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-09 06:10 라이브 브라우저 직접 확인 — Free 카테고리 3종):**
  - `claude-haiku-5.5:free` — "FREE LIMITED TIME", 2026-10-15 22:00까지 무료 (기간 한정 프로모)
  - `deepseek-v4.1-flash:free` — FREE (뱃지 없음)
  - `mimo-v2.6-flash:free` — FREE (뱃지 없음)
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 무료 모델 목록: [Token Harbor 무료 모델](https://tokenharbor.ai/models?category=free) — 로테이션됨 ("Promotional models added over time"). 2026-10-09 06:10 라이브 브라우저 직접 확인 기준 Free 카테고리에 3종 등재: `claude-haiku-5.5:free` ("FREE LIMITED TIME", 2026-10-15 22:00까지 무료 후 표준 요금 전환 — 10/08 저녁 18:00 신규 확인 후 18:11엔 목록에서 사라졌다가 10/09 아침에 복귀), `deepseek-v4.1-flash:free` (FREE), `mimo-v2.6-flash:free` (FREE). Value(유료) 탭에는 각 기본 ID(claude-haiku-5.5 $0.10/$0.50, deepseek-v4.1-flash $0.30/$1.20, mimo-v2.6-flash $0.14/$1.28)가 별도 존재. 무료 라인업이 분 단위로 뒤집히는 중 — 사용 전 재확인이 안전.
  - `qwen3.8-flash:free`는 2026-10-04 13:00 UTC 무료 프로모 종료로 Free 목록에서 제거됨 — 현재 유료 "value" 티어 ($0.15/1M 입력, isFree:false)
  - `deepseek-v4-flash:free` (구형 V4 Flash)는 2026-09-30 pricing Free 목록에서 제외됨 — 공식 블로그(9/23 업데이트)에서는 여전히 무료로 기술 중이라 완전 단정은 불가, 최근 1주 내 무료 라인업에서 빠진 것으로 보임
  - `TH-Rudder` — 2026-09-30 Free 플랜 Includes 신규 표시 (Token Harbor 자체 채팅 제품, API 제공 여부 미확인)

  </details>

- **한도**: $0/월 플랜 — 4주 롤링 주기로 갱신되는 무료 할당량 (정확한 양 미공개, 이월 여부는 보고가 상충). 분당 60회·시간당 1,800회 제한 (2026-09-28 3자 재검증). 카드 불필요.
- **API**: OpenAI 호환. 엔드포인트 `https://tokenharbor.ai/v1` (Anthropic 호환 `/v1/messages`도 제공)
- **도구 호출**: 미확인
- **제한**: 소규모 게이트웨이 — 중국 본토/홍콩/마카오에서 region_blocked. 무료 요청이 플랫폼에 저장될 수 있음. 할당량·라인업이 예고 없이 바뀔 수 있어 프로토타입/폴백용 권장.
- **출처**: https://tokenharbor.ai/pricing , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/token-harbor.md
- **비고**: DeepSeek V4.1 Flash(공식 API는 상시 무료 티어 없음)를 무료로 쓸 수 있는 몇 안 되는 경로. 성능 비교 링크의 대표 모델이라 테스트 가치가 있음. `qwen3.8-flash:free` 무료 프로모는 2026-10-04 13:00 UTC에 종료되어 유료(value 티어)로 전환됨 — 10/05 아침 워치에서 만료 확인. `claude-haiku-5.5:free`는 기간 한정 프로모 (10/15 종료): 10/08 저녁 18:00 신규 확인 후 18:11엔 Free 목록에서 사라졌다가 10/09 아침 라이브 브라우저 확인에서 다시 등재됨. 무료 목록 등재가 불안정하므로 사용 전 재확인 필수.

<a id="nous-portal"></a>

## Nous Portal (Hermes Agent) <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순, 2026-10-09 06:00 기준 — 무료 10종):**
  - `poolside/laguna-s-2.1:free`
  - `inclusionai/ling-3.0-flash-sante:free`
  - `upstage/solar-mini4:free` — 신규 무료 등재 (10/06 확인)
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 2026-10-09 06:00 기준 무료 10종 (공식 API 전체 텍스트 대조 — 가격 $0 기준): `inclusionai/ling-3.1-flash`, `inclusionai/ling-3.0-flash-sante:free`, `poolside/laguna-s-2.1:free`, `poolside/laguna-xs-2.1:free`, `upstage/solar-mini4:free`, `stepfun/step-5-preview:free` (신규), `meituan/longcat-2.0:free`, `inclusionai/ling-3.0-flash-fin:free`, `stepfun/step-3.7-flash:free`, `meituan/longcat-2.5-preview:free`. `upstage/solar-pro4:free`는 :free variant가 카탈로그에 없음 (유료 variant `upstage/solar-pro4`만 유지). `stealth/space-bunny-alpha`는 만료일 2026-10-05 경과 후 카탈로그에서 완전 제거 확인 — 기간 한정 요약표에서 정리. ※ `inclusionai/ling-3.1-flash`는 2026-09-30 출시 2주 무료 체험 모델 (체험 종료 ~10/13~14 예상, 이후 유료 전환·오픈소스 공개 예정 — TechNode 보도) — Nous Portal 무료 등재도 체험 종료와 함께 끝날 가능성, 다음 워치에서 지속 확인. `poolside/laguna-s-2.1:free`·`laguna-xs-2.1:free`는 API 응답상 `expiration_date`가 2026-10-31로 표기됨 — 이후 무료 지속 여부는 다음 워치에서 확인 (2026-10-08 라이브 확인).
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

- **대표 무료 모델 (2026-10-06 06:00 공개 카탈로그 확인 — Tier 필터 Free, 4종):**
  - Qwen3.8 27B (free) — 10/06 신규 Free 등재 (Free 뱃지 직접 확인)
  - Ling 3.0 Flash Sante (free) — inclusionAI
  - Ling 3.0 Flash Fin (free) — inclusionAI
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 전체 목록: [AnyAPI AI 모델 카탈로그](https://anyapi.ai/ai-models) — 좌측 Tier 필터에서 Free 선택 (각 무료 모델에 "Free" 배지 표시)
  - 2026-10-06 06:00 확인 기준 Free 티어 4종: Qwen3.8 27B (free) (신규), Ling 3.0 Flash Sante (free), Ling 3.0 Flash Fin (free), Qwen2.5 Coder 32B Instruct (free). Ling 3.0 Flash Fin (free)은 10/04 오전 Premium 티어 표기→저녁 Free 복귀 이력 — 하루 새 뒤집힌 라인업이라 불안정. Gemma 3n 4B는 카탈로그 목록에서 완전 제거 유지

  </details>

- **한도**: Free $0/월 — 일 100,000 ANY Tokens (가격 페이지 "100K / day" 표기)
- **API**: OpenAI 호환 ("Drop-in replacement for OpenAI SDK" — base URL만 교체)
- **도구 호출**: 미확인
- **제한**: **카드 불필요** — 가격 페이지 Free 플랜 카드에 "No credit card required" 명시. 무료 모델의 API 호출용 정확한 모델 ID 형식은 키 발급 후 확인 필요.
- **출처**: https://anyapi.ai/pricing , https://anyapi.ai/ai-models
- **비고**: Hermes 연결 가능(예상). 로그인 없이 무료 모델 목록을 미리 볼 수 있어 검증이 쉬움. 일 10만 토큰은 에이전트 실사용에는 빠듯 — 테스트·가벼운 용도 적합. 무료 티어 모델이 10/06 아침 기준 4종 (Qwen3.8 27B 신규 Free 등재, Free 뱃지 직접 확인).

<a id="api-airforce"></a>

## Api.Airforce <span class="prio p-low">낮음</span>

- **대표 무료 모델 (`tier: "free"` 기준 — 2026-10-09 18:00 공개 API 라이브 확인, 정상 5종):**
  - `gpt-oss-20b` — 무료 티어, 정상 운영
  - `kimi-k2.7-code` — 무료 티어, 정상 운영
  - `llama-instant` — 무료 티어, 정상 운영
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 전체 목록: [Api.Airforce 모델 카탈로그 API](https://api.airforce/v1/models) — `tier: "free"`인 항목이 무료 (2026-10-08 기준 전체 약 637종 중 28종). ※ `access_tiers`는 유료 모델도 전부 `["free"]`라 무료 지표로 사용 불가.
  - 무료 28종: mistral 계열 18종, suno 계열 3종, `gemma3-270m:free`, `glm-4.7-flash`, `rnj-1`, `llama-instant`, `kimi-k2.7-code`, `unmoderated-gpt`, `gpt-oss-20b`
  - 주의: 정상 호출 가능 무료 모델은 5종 (`gpt-oss-20b`·`kimi-k2.7-code`·`llama-instant`·`rnj-1`·`unmoderated-gpt`) — 2026-10-09 18:00 라이브 확인: `glm-4.7-flash`가 다시 major_outage로 전환, `unmoderated-gpt`(major_outage→정상)·`rnj-1` 정상 복귀. `gemma3-270m:free` degraded 지속. 상태가 분 단위로 뒤집히는 중이라 사용 전 재확인이 안전. (10/09 06:01엔 2종이었으나 07:10 재확인에서 `llama-instant`(degraded→정상)·`glm-4.7-flash`(major_outage→정상) 복귀. 2026-10-08 18:03 라이브 확인: 아침 정상이던 `rnj-1`이 major_outage로 전환, `unmoderated-gpt`는 partial_outage→operational로 복귀. 4분 간격 재확인에서 `glm-4.7-flash`가 정상→major_outage로 뒤집힘. `gemma3-270m:free`는 major_outage 유지.)

  </details>

- **한도**: Free $0.00/월 — 분당 1회 / 일 1,000회 ("Access to basic models")
- **API**: OpenAI 호환 (공식 홈페이지에서 Cursor·Cline·OpenCode·Claude Code 등 코딩 에이전트/CLI 연동 광고)
- **도구 호출**: 미확인
- **제한**: 카드 등록 필요 여부는 가격 페이지에 표기 없음 (미확인). 무료 플랜의 실제 호출 가능 여부는 계정으로 테스트 필요.
- **출처**: https://api.airforce/pricing , https://api.airforce/v1/models
- **비고**: 공개 카탈로그의 `tier` 표기와 가격 페이지의 "Free models" 표기가 일치하는지는 실제 키 테스트로 검증 필요. 현재 무료 모델 다수가 장애 상태라 폴백 우선순위는 낮음.

<a id="ollama-cloud"></a>

## Ollama Cloud <span class="prio p-low">낮음</span>

- **대표 무료 모델**: starter 모델 세트 — 공개 목록 미확인 (가격 페이지에 "smaller set of starter models"로만 표기, 구체 모델명·크레딧 금액 미공개)
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - [Ollama Cloud 가격 페이지](https://ollama.com/cloud) — Free 플랜에 "Includes access to starter models" 표기. starter 모델의 구체 목록은 공개 페이지에서 확인 불가 (가입 후 확인 필요).

  </details>

- **한도**: Free $0 — starter usage credits 포함 (금액 미공개), 매월 가입일 기준 리셋, 미사용분 이월 불가, 동시 요청 1개
- **API**: OpenAI 호환 엔드포인트 `https://ollama.com/v1` (3자 검증 기준 — 공식 키는 https://ollama.com/settings/keys 에서 발급)
- **도구 호출**: 지원 (공식 FAQ: 도구 지원 학습된 클라우드 모델은 실제 에이전트 워크플로로 테스트 후 공개)
- **제한**: 카드 요구 여부는 가격 페이지에 표기 없음 (미확인). 프롬프트·응답 데이터는 로깅·학습하지 않음 (공식 FAQ 명시).
- **출처**: https://ollama.com/cloud
- **비고**: 매월 리셋되는 상시 무료라 조사 범위 충족. 단, 크레딧 금액·starter 모델 목록이 비공개라 Hermes 폴백으로는 하위 우선순위. 크레딧 구매 시 전체 모델 잠금 해제.

<a id="agnes-ai"></a>

## Agnes AI <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-02 공식 가격 페이지 확인 — 프로모션 $0):**
  - `agnes-3.0-flash` — 현재 $0 청구 (프로모션, 종료 시 유료 전환 가능)
  - `agnes-2.5-flash` — 현재 $0 청구 (프로모션, 종료 시 유료 전환 가능)
  <details>
  <summary>더보기 — 무료 조건 안내</summary>

  - 공식 FAQ: "Our core AI models are free to use indefinitely". 가격 페이지에서 `agnes-2.5-flash`·`agnes-3.0-flash` 현재 $0 청구 확인.
  - [Agnes AI](https://agnes-ai.com) — 공식 문구 "Promotional end dates are subject to Agnes AI platform announcements"

  </details>

- **한도**: 일일 쿼터 미공개 (3자 프로브 기준 분당 약 20~30 RPM)
- **API**: OpenAI 호환. 엔드포인트 `https://apihub.agnes-ai.com/v1`
- **도구 호출**: 미확인
- **제한**: 카드 불필요. $0은 상시 계약이 아니라 현재 가격 책정 — 종료 시 유료 전환 가능. 2026-09-14 검증 목록 등록, 9/24 프로브 확인 (provisional 상태)
- **출처**: https://agnes-ai.com , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/agnes-ai.md
- **비고**: 프로모션 $0 제공자라 우선순위 낮음. 무료 종료 시 Tracker에서 제거 검토.

<a id="bazaarlink"></a>

## BazaarLink <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-03 공식 무료 페이지 직접 확인):**
  - `qwen/qwen3.7-flash` — 1M 컨텍스트, 텍스트·이미지·비디오 입력 (24시간 프로브 100%)
  - `deepseek/deepseek-v4-flash-0731free` — 약 1M 컨텍스트, 텍스트 전용 (24시간 프로브 100%)
  <details>
  <summary>더보기 — 무료 조건 안내</summary>

  - 공식 페이지: [BazaarLink Free](https://bazaarlink.ai/free) — "Free — No Credit Card Required", 카탈로그 스냅샷(2026-10-03 08:05 UTC) 기준 무료 2종, 매시간 프로브로 실제 응답 확인 공개
  - 무료 모델은 "enabled free models" 표에서만 제공 (로테이션 가능)

  </details>

- **한도**: 무충전 계정 — 10 RPM · 일 60 가중 단위 / 충전 계정 — 20 RPM · 일 120 가중 단위 (무료 모델 간 공유, 00:00 UTC 일일 리셋). 사이트 전체 무료 RPM 상한 15, 계정당 동시 무료 요청 2개
- **API**: OpenAI 호환. 엔드포인트 `https://api.bazaarlink.ai/v1`
- **도구 호출**: 미확인 (공식 무료 페이지에 언급 없음)
- **제한**: 카드 불필요 (이메일 가입 후 60초 만에 무료 키 발급). 긴 입력은 가중 단위 소모가 커짐 (가중 단위: 입력 길이에 따라 소모량이 달라지는 한도 단위)
- **출처**: https://bazaarlink.ai/free
- **비고**: 영구 무료 티어라 조사 범위 충족. 일 한도가 작아(짧은 요청 기준 일 ~60회 수준) 테스트·가벼운 폴백용. 운영사 대만 소재.

<a id="cline"></a>

## Cline <span class="prio p-no">연동 불가</span>

- **무료 모델**: Cline 계정 사용자에게 제공되는 기간 한정 무료 모델 프로모션 (모델 목록은 로테이션되며, 2026-09-17 기준 deepseek-v4-flash 제외 등 변동). 고정된 무료 모델 ID 목록 없음.
- **한도**: 프로모션별 일일 사용량 제한 — 구체 수치 미확인
- **API**: **미지원**. 공식 문서 명시: "Free model usage is not supported through the Cline API. Free models are only available in the Cline IDE Extension and CLI."
- **도구 호출**: 해당 없음 (API 미제공)
- **제한**: 무료 모델 사용 데이터가 모델 개선에 활용될 수 있음. 무료 할당량 소진 후 ClinePass($9.99/월) 또는 usage-billing 전환.
- **출처**: https://docs.cline.bot/getting-started/free-models
- **비고**: Cline은 API 제공자가 아니라 VS Code/JetBrains/CLI용 코딩 에이전트 도구임. Hermes Agent에 연결할 수 없으므로 조사 대상에서 제외. 형님께 "Cline 무료 모델은 Cline 안에서만 쓸 수 있다"고 안내 필요.

<a id="limited-free"></a>

## 기간 한정 무료

- **안내**: 상시 무료가 아닌, 기간·조건이 한정된 무료 제공자 모음. 종료일이 다가오면 아침·저녁 워치에서 만료 여부를 확인합니다.

| 제공자 | 무료 조건 | 종료 예정 | OpenAI 호환 |
|---|---|---|---|
| [ZeroLimitAI](#zerolimitai) | 7일 체험, 일 100회 | 키 발급 후 7일 (종료 시 402) | O |
| [Hetzner Inference API](#hetzner-inference-api) | 실험 단계 무료 | 미정 (사전 이메일 공지) | O |
| [OpenCode Zen](#opencode-zen) 무료 모델 | 기간 한정 (전 모델) | 모델별 상이 | O |
| [Nous Portal](#nous-portal) `ling-3.1-flash` | 2주 무료 체험 | ~10/13~14 예상 | O |
| `space-bunny-alpha` ([Nous Portal](#nous-portal)·[OpenRouter](#openrouter)) | 기간 한정 무료 등재 | 만료(2026-10-05) → 양쪽 카탈로그에서 제거 확인 (2026-10-06) | O |
| [Cline](#cline) 무료 모델 | 기간 한정 프로모션 | 모델별 상이 | X (API 미제공) |

<a id="zerolimitai"></a>

## ZeroLimitAI <span class="prio p-low">낮음</span>

- **대표 무료 모델 (2026-10-04 공식 개발자 페이지 확인):**
  - `auto` — 자동 라우팅: ZeroOptimize™가 매일 재평가한 무료 모델 중 살아 있는 최고 모델로 자동 연결, 장애 시 폴오버
  <details>
  <summary>더보기 — 무료 플랜 안내</summary>

  - 공식 개발자 페이지: [ZeroLimitAI Developers](https://www.zerolimitai.com/developers) — "Free week — $0 for 7 days" (2026-10-04 변경 확인, 기존 "Free — $0 forever"에서 전환)
  - `model: "auto"` 하나로 호출, chat completions·스트리밍·함수 호출(tools) 지원

  </details>

- **한도**: Free week — $0 for 7 days. 일 100회, 00:00 UTC 리셋. 체험 종료 후 키는 HTTP 402 upgrade_required — Annual($49/년, 일 2,000회)·Lifetime($99 일회성, 일 5,000회) 필요
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

## 변경 이력

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
