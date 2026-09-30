# Free LLM Tracker — 기준선 (2026-10-01)

<p class="notice">
Hermes Agent(OCI 무료 인스턴스)에 연결할 무료 LLM API 제공자 조사 기준선.<br>
모든 수치는 2026-10-01 기준 공식 문서·가격 페이지 또는 3자 검증 자료 기준이며,<br>
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
- [LLM7.io](#llm7)
- [OpenCode Zen](#opencode-zen)
- [Token Harbor](#token-harbor)
- [Nous Portal (Hermes Agent)](#nous-portal)
- [Cline](#cline)
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

- **한도**: 공식 한도 문서의 공개 테이블 기준 — gpt-oss-120b/20b/safeguard-20b, qwen3.8-27b에 30 RPM / 1K RPD / 8K TPM / 200K TPD (2026-09-24 직접 확인). Llama 3.1/3.3 채팅 모델은 2026-08-16 종료 이후 무료 테이블에 없음 (2026-09-17 3자 검증 "free plan에 Llama 없음"). 정확한 무료 티어 수치는 계정 limits 페이지에서 확인 필요.
- **API**: OpenAI 호환. 엔드포인트 `https://api.groq.com/openai/v1`
- **도구 호출**: 지원
- **제한**: 카드 불필요. 학습 활용 안 함 (커뮤니티 보고 기준).
- **출처**: https://console.groq.com/docs/rate-limits
- **비고**: 속도 매우 빠름 (LPU, 300~1000+ tok/s). 완전 무료 조합의 메인 후보.

<a id="nvidia-nim"></a>

## NVIDIA NIM (build.nvidia.com) <span class="prio p-high">높음</span>

- **대표 무료 모델 (사용성 순):**
  - `moonshotai/kimi-k3` — function calling 광고 (2026-09-30 공식 무료 라인업 확인)
  - `deepseek-ai/deepseek-v4-pro-0813` — 고속 플래그십 (2026-09-30 확인)
  - `nvidia/nemotron-3-ultra-550b-a55b` — 초대형 MoE (2026-09-30 확인)
  - `nvidia/nemotron-3.5-lightning-30b-a3b` — 경량 고속 (2026-09-30 확인)
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 무료 추론 모델: [build.nvidia.com](https://build.nvidia.com) — 'Free inference with leading models' 섹션에서 확인 (예고 없이 변경됨, 2026-09-30 기준 4종)
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

- **한도**: Free 플랜 — 월 $10 API 크레딧 (공식 가격 페이지 기준, 2026-09-24 검증). Studio·API·Vibe 공유, 초과 시 다음 결제 주기까지 중단 (PAYG 전환 시 예외). 무료 모드는 가장 낮은 속도 제한 적용 (정확한 수치는 계정 내 표시).
- **API**: OpenAI 호환. 엔드포인트 `https://api.mistral.ai/v1`
- **도구 호출**: 지원
- **제한**: 카드 불필요. 학습 활용 위험 보고 있음.
- **출처**: https://console.mistral.ai (커뮤니티 검증 기준), https://mistral.ai/pricing
- **비고**: 월 $10 크레딧은 에이전트 실사용에 빠듯 (Mistral Large 기준 입력 약 2천만 토큰 수준). 데이터 정책 주의 (기본적으로 학습 활용 가능, Admin 패널 opt-out 필요).

<a id="openrouter"></a>

## OpenRouter (이전 조사) <span class="prio p-mid">중간</span>

- **대표 무료 모델 (사용성 순, 2026-09-29 기준 — 라인업 로테이션됨):**
  - `nvidia/nemotron-3-super-120b-a12b:free` — 초대형 MoE
  - `cohere/north-mini-code:free` — 코드 특화
  - `inclusionai/ling-3.0-flash-sante:free` — 고속·의료 특화 (2026-09-29 무료 신규 등록)
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 전체 무료 모델: [OpenRouter 모델 목록](https://openrouter.ai/models) — 무료 필터 사용 (모델명 끝에 `:free`, 로테이션됨)

  </details>

- **한도**: 분당 20회 / 일 50회 (누적 $10 이상 구매 시 일 1,000회)
- **API**: OpenAI 호환. 엔드포인트 `https://openrouter.ai/api/v1`
- **도구 호출**: 무료 라우트별 상이 (각 라우트의 supported_parameters 확인 필요)
- **제한**: 카드 불필요. 무료 라우트별 데이터 정책 상이 (일부는 학습 활용 경고 있음). upstream 429 빈발 보고.
- **출처**: https://buldrr.com/openrouter-free-api-keys-free-models-simple-guide/
- **비고**: Hermes 공식 문서의 기본값이라 설정 예제가 가장 풍부. 일 50회는 에이전트 실사용에 빠듯. $10 1회 충전 시 한도 20배 상승이 가성비 최고. 구 무료 모델(DeepSeek R1·Llama 3.3 70B·Qwen3 Coder 등)의 `:free` 버전은 2026-09-28 확인 기준 유료 전용으로 전환됨. 2026-09-29 18:00 라이브 스냅샷 기준 `:free` 16종 — `qwen3.8-27b:free`·`liquid/lfm-2.5-2.6b:free` 신규 등록. `inclusionai/ling-3.0-flash-fin:free`는 유료 전환 (input $0.06/1M, output $0.18/1M). Thinking Machines Inkling은 에이전트 하네스에서만 응답하고 일반 API 호출에는 403을 반환하므로 Hermes 직접 연결 폴백에서 제외 권장 (2026-09-28 3자 검증).

<a id="llm7"></a>

## LLM7.io <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순, turbo 티어 — 2026-10-01 라이브 API 직접 확인):**
  - `GLM-5.3-Flash` — turbo 티어 무료 (카탈로그의 소문자 `glm-5.3`은 ID가 다른 별개 pro 모델)
  - `codestral-latest` — turbo 티어 무료
  - `mistral-Nemo-Instruct-2407` — turbo 티어 무료
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 2026-10-01 라이브 API 직접 확인 기준 turbo(무료) 티어는 위 3종. `minimax-m2.7`은 카탈로그에서 제거됨 (대체로 `minimax-m3` pro 행만 존재), `deepseek-v4-flash:0731`은 pro 티어로 이동.
  - 전체 목록: [LLM7.io 모델 카탈로그](https://api.llm7.io/v1/models) — `tier: "turbo"` 행이 무료

  </details>

- **한도**: 무료 토큰(dash.llm7.io 발급) — 초당 1회 / 분당 60회 / 시간당 250회 / 24시간 100,000 토큰 (2026-10-01 공식 한도 문서 기준 — 24시간 토큰 허용량이 기존 100만에서 1/10로 축소됨). 익명(키 없음) 티어 표기는 공식 문서에서 사라짐 (삭제인지 표기 누락인지 미확인).
- **API**: OpenAI 호환. 엔드포인트 `https://api.llm7.io/v1`. 익명 사용 시 api_key에 "unused" 입력.
- **도구 호출**: 미확인
- **제한**: 카드·가입 불필요(익명 가능). 운영자가 upstream을 공개하지 않음. 무료 모델 구성이 변경될 수 있음.
- **출처**: https://docs.llm7.io/limits , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/llm7.md , https://github.com/velo4705/awesome-free-byok-models
- **비고**: Hermes 연결 가능. 가입 없이 바로 쓸 수 있어 테스트용으로 가장 간편. 단, 24시간 10만 토큰은 에이전트 루프 몇 바퀴면 소진이므로 에이전트 실사용 폴백으로는 사실상 부적합 — '가입 없이 짧게 시험' 용도로만 유효.

<a id="opencode-zen"></a>

## OpenCode Zen <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순, OpenCode 내부 전용):**
  - `big-pickle` — 스텔스 모델, 기간 한정 무료
  - `nemotron-3-ultra-free` — 기간 한정 무료
  - `muse-spark-1.3-contributor-free` — 데이터 제공 대가 무료 행
  <details>
  <summary>더보기 — 전체 무료 모델 목록</summary>

  - 무료 모델 목록: [OpenCode Zen 문서](https://opencode.ai/docs/zen/) — 가격표 "Free" 행 기준 (로테이션됨). 2026-09-27 기준 `big-pickle`, `space-bunny-free`, `longcat-2.5-preview-free`, `mimo-v2.6-flash-free`, `mimo-v2.5-free`, `ling-3.0-flash-fin-free`, `nemotron-3-ultra-free`, `nemotron-3.5-lightning-free`, `muse-spark-1.3-contributor-free`, `jev-1.13-free` (전부 기간 한정)
  - 스텔스 모델 관련 정보:
    - Big Pickle: [SWE Atlas 벤치마크 측정](https://github.com/PhillipChaffee/big-pickle-swe-atlas) — 코드베이스 QnA 50.8% 해결률 (정체 미공개, 커뮤니티에서는 GLM-4.6 추정)
    - Space Bunny: [지문 분석](https://github.com/majiayu000/stealthprint/blob/main/docs/case-space-bunny.md) — MiniMax 계열 토크나이저, 1M 컨텍스트 확인. Space Bunny Alpha는 [Nous Portal](https://portal.nousresearch.com/)에서도 무료($0.00/1M) 제공 중

  </details>

- **한도**: 커뮤니티 보고 기준 일 약 100회 요청 (공식 문서에 무료 티어 수치 미기재 → 미확인)
- **API**: OpenAI 호환. 엔드포인트 `https://opencode.ai/zen/v1` — 단, **무료 티어는 OpenCode 외부 하네스에서 사용 불가**
- **도구 호출**: 지원 (3자 검증 기준)
- **제한**: **2026-09-17부터 무료 티어가 OpenCode가 아닌 모든 클라이언트를 403으로 차단** (`FreeTierError: OpenCode's free tier can only be used from within OpenCode`) — 2026-09-18 OpenCode maintainer가 "무료 티어는 다른 하네스에서 사용 불가" 확인. Hermes 등 외부 하네스에서 무료 티어 사용 불가 확정. 무료 모델 데이터가 학습에 활용될 수 있음.
- **출처**: https://opencode.ai/docs/zen/ , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/opencode.md , https://github.com/decolua/9router/issues/4103
- **비고**: Hermes에서 Zen 무료 티어는 쓸 수 없으므로 폴백 후보에서 제외. 유료 Zen 잔액이 있으면 연동 가능.

<a id="token-harbor"></a>

## Token Harbor <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순, 2026-10-01 무료 카탈로그 기준):**
  - `deepseek-v4.1-flash:free` — 무료 라우트 (2026-09-30 Free 플랜 Includes 명시 확인, 대시보드에서 :free 라우트 활성화 필요)
  - `mimo-v2.6-flash:free` — 2026-10-01 Free 목록 확인 (v2.5→v2.6 교체)
  - `qwen3.8-flash:free` — 2026-10-01 무료 신규 등록
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 무료 모델 목록: [Token Harbor 무료 모델](https://tokenharbor.ai/models?category=free) — 로테이션됨 ("Promotional models added over time")
  - `deepseek-v4-flash:free` (구형 V4 Flash)는 2026-09-30 pricing Free 목록에서 제외됨 — 공식 블로그(9/23 업데이트)에서는 여전히 무료로 기술 중이라 완전 단정은 불가, 최근 1주 내 무료 라인업에서 빠진 것으로 보임
  - `TH-Rudder` — 2026-09-30 Free 플랜 Includes 신규 표시 (Token Harbor 자체 채팅 제품, API 제공 여부 미확인)

  </details>

- **한도**: $0/월 플랜 — 4주 롤링 주기로 갱신되는 무료 할당량 (정확한 양 미공개, 이월 여부는 보고가 상충). 분당 60회·시간당 1,800회 제한 (2026-09-28 3자 재검증). 카드 불필요.
- **API**: OpenAI 호환. 엔드포인트 `https://tokenharbor.ai/v1` (Anthropic 호환 `/v1/messages`도 제공)
- **도구 호출**: 미확인
- **제한**: 소규모 게이트웨이 — 중국 본토/홍콩/마카오에서 region_blocked. 무료 요청이 플랫폼에 저장될 수 있음. 할당량·라인업이 예고 없이 바뀔 수 있어 프로토타입/폴백용 권장.
- **출처**: https://tokenharbor.ai/pricing , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/token-harbor.md
- **비고**: DeepSeek V4.1 Flash(공식 API는 상시 무료 티어 없음)를 무료로 쓸 수 있는 몇 안 되는 경로. 성능 비교 링크의 대표 모델이라 테스트 가치가 있음.

<a id="nous-portal"></a>

## Nous Portal (Hermes Agent) <span class="prio p-low">낮음</span>

- **대표 무료 모델 (사용성 순):**
  - `stepfun/step-3.7-flash:free`
  - `poolside/laguna-s-2.1:free`
  - `meituan/longcat-2.0:free` — 1M 컨텍스트
  <details>
  <summary>더보기 — 전체 무료 모델 안내</summary>

  - 2026-09-30 기준 무료 9종 (공식 API 직접 조회): `stepfun/step-3.7-flash:free`, `poolside/laguna-s-2.1:free`, `poolside/laguna-xs-2.1:free`, `inclusionai/ling-3.0-flash-fin:free`, `inclusionai/ling-3.0-flash-sante:free`, `upstage/solar-pro4:free`, `meituan/longcat-2.0:free`, `meituan/longcat-2.5-preview:free` (신규), `stealth/space-bunny-alpha` (변동 가능)
  - 카탈로그: [Nous Portal 모델 목록](https://portal.nousresearch.com/models) — 'Free Models' 섹션 및 FREE 필터로 무료 모델 직접 확인 (로그인 불필요), 공식 API: https://inference-api.nousresearch.com/v1/models

  </details>

- **한도**: Free $0 플랜 — "$0 행 모델만, Standard rate limits" (구체 수치 미공개). 카드 불필요.
- **API**: OpenAI 호환. 엔드포인트 `https://inference-api.nousresearch.com/v1`
- **도구 호출**: 미확인
- **제한**: Privacy Mode를 켜지 않으면 추론 페이로드가 학습·개선에 활용될 수 있음. 2026-09-16에 처음 포착된 신규 항목이라 안정성 검증 중 (3자 추적 기준 provisional).
- **출처**: https://portal.nousresearch.com/models , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/nous-portal.md
- **비고**: Nous Research(Hermes Agent 제작사)의 공식 추론 포털. 형님이 세팅 중인 Hermes Agent와 같은 생태계라 연동 테스트 가치가 높음. `step-3.7-flash:free`는 2026-09-30·10-01 실제 브라우저 라이브 확인에서 만료일·"limited time" 표기 없이 무료 등재 유지 — 2026-10-01 만료설은 공식 근거 없는 소문으로 확인됨.

<a id="cline"></a>

## Cline <span class="prio p-no">연동 불가</span>

- **무료 모델**: Cline 계정 사용자에게 제공되는 기간 한정 무료 모델 프로모션 (모델 목록은 로테이션되며, 2026-09-17 기준 deepseek-v4-flash 제외 등 변동). 고정된 무료 모델 ID 목록 없음.
- **한도**: 프로모션별 일일 사용량 제한 — 구체 수치 미확인
- **API**: **미지원**. 공식 문서 명시: "Free model usage is not supported through the Cline API. Free models are only available in the Cline IDE Extension and CLI."
- **도구 호출**: 해당 없음 (API 미제공)
- **제한**: 무료 모델 사용 데이터가 모델 개선에 활용될 수 있음. 무료 할당량 소진 후 ClinePass($9.99/월) 또는 usage-billing 전환.
- **출처**: https://docs.cline.bot/getting-started/free-models
- **비고**: Cline은 API 제공자가 아니라 VS Code/JetBrains/CLI용 코딩 에이전트 도구임. Hermes Agent에 연결할 수 없으므로 조사 대상에서 제외. 형님께 "Cline 무료 모델은 Cline 안에서만 쓸 수 있다"고 안내 필요.

<a id="changelog"></a>

## 변경 이력

<details>
<summary>변경 이력 펼쳐보기</summary>

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
