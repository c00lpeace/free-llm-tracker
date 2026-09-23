# Free LLM Tracker — 기준선 (2026-09-24)

Hermes Agent(OCI 무료 인스턴스)에 연결할 무료 LLM API 제공자 조사 기준선.
모든 수치는 2026-09-24 기준 공식 문서·가격 페이지 또는 3자 검증 자료 기준이며,
'미확인'은 조사 시점에 확인되지 않은 항목임.

**읽는 법**
- 제공자는 **Hermes에서 쓰기 좋은 순서**로 정렬 (판단 기준: API 제공 여부 → 무료 한도 → 도구 호출 지원 → 안정성).
  API를 제공하지 않는 곳(Cline)은 맨 아래 '연동 불가' 섹션에 분리.
- 각 제공자의 무료 모델은 **사용성 좋은 순으로 대표 3개만 목록으로 표시**하고, 전체 목록은 '더보기'를 눌러 공식 페이지 링크에서 확인 (GitHub 웹에서 펼쳐보기 가능).
- 제공자명 옆의 색상 뱃지는 우선순위 (초록=높음, 노랑=중간, 회색=낮음, 빨강=연동 불가).
- 정기 체크(매일 06:00 / 18:00 KST)는 본문을 항상 최신 상태로 갱신하고,
  변경된 사실은 맨 아래 '변경 이력'에 날짜순으로 한 줄씩 추가함.

## 성능 비교

- [추천 무료 모델 + 프론티어 모델 바로 비교](https://artificialanalysis.ai/models/comparisons?compare=kimi-k2-5,gpt-oss-120b,deepseek-v4-flash-vision,claude-opus-5-5,gemini-3-8-flash&models=gpt-oss-120b,kimi-k2-5,deepseek-v4-flash,gemini-2-5-flash,gpt-5-6-sol,claude-opus-5-5,gemini-3-8-flash): 클릭하면 바로 비교 화면이 열립니다. 상단 표에는 5종(Kimi K2.5, gpt-oss-120b, DeepSeek V4 Flash Vision, Claude Opus 5.5, Gemini 3.8 Flash)이 나란히 표시되고(상단 표는 최대 5개까지 지원), 하단 지능·가격·속도 차트에는 추천 무료 4종 + 프론티어 3종(GPT-5.6 Sol, Claude Opus 5.5, Gemini 3.8 Flash)이 함께 비교됩니다. 프론티어 모델은 버전이 자주 바뀌므로 링크가 오래되면 최신 버전으로 교체가 필요할 수 있음.
- [Artificial Analysis 모델 비교](https://artificialanalysis.ai/models): 모델 선택기로 여러 모델을 지정해 지능(Intelligence Index)·속도·가격을 차트에서 나란히 비교 가능. 모델별 전용 페이지에서는 유사 모델과의 직접 비교도 제공.
- 무료 엔드포인트(`:free`, `-free` 등)는 제공자별 별칭이므로, 비교 시에는 기반 모델명(예: DeepSeek V4, Kimi K2)으로 검색.

## Groq (이전 조사) <span class="prio p-high">높음</span>

- 대표 무료 모델 (사용성 순):
  - `gpt-oss-120b` — 한도 문서에 명시된 무료 모델
  - Llama 3.3 70B 계열
  - Qwen3 계열
<details>
<summary>더보기 — 전체 무료 모델 안내</summary>

- GPT/Claude/Gemini 계열은 없음.
- 전체 무료 모델 목록: [Groq 공식 모델 문서](https://console.groq.com/docs/models) (정확한 목록은 가입 후 계정 limits 페이지에서 확인)

</details>

- 한도: 공식 문서는 Developer plan 기본 한도만 공개 (예: gpt-oss-120b — 분당 30회 / 일 1,000회 / 분당 8K 토큰 / 일 200K 토큰). 무료 티어 정확한 수치는 미확인 (가입 후 계정 limits 페이지에서 확인 필요).
- API: OpenAI 호환. 엔드포인트 `https://api.groq.com/openai/v1`
- 도구 호출: 지원
- 제한: 카드 불필요. 학습 활용 안 함 (커뮤니티 보고 기준).
- 출처: https://console.groq.com/docs/rate-limits
- 비고: 속도 매우 빠름 (LPU, 300~1000+ tok/s). 완전 무료 조합의 메인 후보.

## NVIDIA NIM (build.nvidia.com) <span class="prio p-high">높음</span>

- 대표 무료 모델 (사용성 순):
  - `moonshotai/kimi-k2.5` — function calling 광고
  - `deepseek-ai/deepseek-v4-flash-0731` — 고속 플래그십
  - `meta/llama-3.3-70b-instruct` — 안정적 폴백
<details>
<summary>더보기 — 전체 무료 모델 목록</summary>

- 전체 무료 모델 카탈로그: [build.nvidia.com](https://build.nvidia.com) — 100+ 오픈웨이트 모델 (ID는 카탈로그에서 복사, 예고 없이 변경됨)

</details>

- 한도: 키당 분당 약 40회 요청 (커뮤니티 기준, 모델·트래픽에 따라 상이). 일일 상한은 rate limit 외 별도 없음(보고 기준).
- API: OpenAI 호환. 엔드포인트 `https://integrate.api.nvidia.com/v1`, 인증은 `Bearer nvapi-...` 키.
- 도구 호출: 모델별 상이 (DeepSeek V3/R1, Kimi K2, GLM, GPT-OSS 계열이 function calling 광고하나 품질 편차 있음)
- 제한: 카드 불필요. 단, 가입 시 고유 이메일+전화번호 인증 필요. 공식 약관상 프롬프트/응답을 학습에 사용하지 않음(커뮤니티 보고 기준). 프로덕션 용도 아님(프로토타이핑용).
- 출처: https://github.com/miztertea/nim-proxy/blob/HEAD/knowledge/research/nim-free-tier-40rpm-no-credits.md , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/nvidia-nim.md
- 비고: OpenAI 호환이라 Hermes 연결 가능. 분당 40회는 에이전트 루프에 넉넉한 편. 도구 호출 품질이 모델별로 들쭉날쭉하므로 메인 모델은 DeepSeek/Kimi 계열로 테스트 권장.

## OrcaRouter <span class="prio p-high">높음</span>

- 대표 무료 모델 (사용성 순):
  - `deepseek/deepseek-v4-pro-free` — 최상위 성능
  - `deepseek/deepseek-v4-flash-free` — 고속
  - `tencent/hy3-free`
<details>
<summary>더보기 — 전체 무료 모델 안내</summary>

- 무료 라인업: [OrcaRouter](https://www.orcarouter.ai) — 로테이션됨. `orcarouter/free` 자동 라우팅 별칭도 제공.

</details>

- 한도: 무료 모델은 $0/토큰, 요청 속도(request rate) 기준으로 상한 적용 — 구체적 수치 미확인. 무료 "Hacker" 티어는 200+ 모델 카탈로그 접근 포함.
- API: OpenAI 호환. 엔드포인트 `https://api.orcarouter.ai/v1` (Anthropic·Gemini 호환 엔드포인트도 제공). 키 발급: GitHub 로그인 후 대시보드에서 발급.
- 도구 호출: 지원
- 제한: 카드 등록 불필요(Hacker 티어 무료). 무료 모델 외에는 upstream 제공자 요금 그대로 과금(zero markup). 무료 모델 라인업이 자주 교체됨.
- 출처: https://www.orcarouter.ai/pricing , https://runtimewire.com/article/orcarouter-glm-5-3-flash-free-tier , https://github.com/12britz/awesome-free-models/pull/53
- 비고: 형님이 언급한 "Orcarouter"는 실제 서비스명 "OrcaRouter"임. OpenAI 호환이라 Hermes에 바로 연결 가능. 무료 모델은 rate-limited이므로 메인보다는 폴백/서브용 적합.

## Google AI Studio — Gemini (이전 조사) <span class="prio p-mid">중간</span>

- 대표 무료 모델 (사용성 순):
  - Gemini 2.5 Flash-Lite — 일 1,000~1,500회, 한도 최다
  - Gemini 2.5 Flash
  - Gemma 계열
<details>
<summary>더보기 — 무료 모델 범위 안내</summary>

- Flash 계열만 무료 (Gemini 2.5/3.x Flash, Flash-Lite, Gemma). Pro 모델은 2026년 4월부터 무료 티어 제외 (유료 전용).
- 전체 모델 목록: [Gemini API 모델 문서](https://ai.google.dev/gemini-api/docs/models)

</details>

- 한도: Flash — 분당 10회 / 일 250~1,500회 (프로젝트·리전별 변동 큼). Flash-Lite — 분당 15회 / 일 1,000~1,500회.
- API: OpenAI 호환 엔드포인트 제공 — `https://generativelanguage.googleapis.com/v1beta/openai/`
- 도구 호출: 지원 (function calling, JSON 모드, 구조화 출력)
- 제한: 카드 불필요(Google 계정만). 무료 티어 데이터 학습 활용 가능 (과금 활성화 시 opt-out). 한도가 예고 없이 삭감된 전례 있음 (250→20 RPD 보고).
- 출처: https://help.apiyi.com/en/google-ai-studio-free-quota-limits-solution-en.html
- 비고: 한국어 성능 강점. 단, 한도 변동 리스크가 있어 메인 단독 사용은 주의.

## OpenCode Zen <span class="prio p-mid">중간</span>

- 대표 무료 모델 (사용성 순):
  - `nemotron-3-ultra-free` — 플래그십
  - `mimo-v2.6-flash-free` — 고속
  - `big-pickle`
<details>
<summary>더보기 — 전체 무료 모델 목록</summary>

- 무료 모델 목록: [OpenCode Zen 문서](https://opencode.ai/docs/zen/) — 가격표 "Free" 행 기준 (로테이션됨)

</details>

- 한도: 커뮤니티 보고 기준 일 약 100회 요청 (공식 문서에 무료 티어 수치 미기재 → 미확인)
- API: OpenAI 호환. 엔드포인트 `https://opencode.ai/zen/v1` (chat/completions, responses, messages, systemone 등 모델별 상이)
- 도구 호출: 지원 (3자 검증 기준)
- 제한: 공식 문서는 API 키 발급 시 "billing details 추가" 요구. 커뮤니티 보고는 "카드 불필요·무료 티어 존재" — 상충하므로 주의. 무료 모델 데이터가 학습에 활용될 수 있음(커뮤니티 보고). 2026-09-17 이후 일부 보고에서 "무료 티어는 OpenCode 외부에서 403" 발생 — Hermes 등 외부 하네스 사용 가능 여부는 계정/키 종류에 따라 상이할 수 있음(미확인). 무료 preview 키는 약 7일 만료 보고 있음.
- 출처: https://opencode.ai/docs/zen/ , https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/opencode.md , https://github.com/barestack-labs/quality-free-ai-providers/blob/HEAD/providers/opencode-zen.md
- 비고: Hermes 연동 자체는 base_url 변경만으로 가능하나, 무료 티어의 외부 하네스 차단·키 만료 리스크가 있어 폴백용으로만 권장. 유료 모델은 pay-as-you-go.

## Mistral (이전 조사) <span class="prio p-mid">중간</span>

- 대표 무료 모델 (사용성 순):
  - Mistral Large 계열 — 최상위 성능
  - Codestral — 코드 특화
  - Mistral Small 계열 — 경량·고속
<details>
<summary>더보기 — 전체 무료 모델 안내</summary>

- Experiment 플랜에서는 전 모델 무료.
- 전체 모델 목록: [Mistral 모델 문서](https://docs.mistral.ai/getting-started/models/)

</details>

- 한도: Experiment 티어 — 초당 1회 / 분당 50만 토큰 / 월 10억 토큰
- API: OpenAI 호환. 엔드포인트 `https://api.mistral.ai/v1`
- 도구 호출: 지원
- 제한: 카드 불필요. 학습 활용 위험 보고 있음.
- 출처: https://console.mistral.ai (커뮤니티 검증 기준)
- 비고: 월 10억 토큰은 넉넉하나 초당 1회는 에이전트 루프에 빠듯. 데이터 정책 주의.

## OpenRouter (이전 조사) <span class="prio p-mid">중간</span>

- 대표 무료 모델 (사용성 순, 2026-09 기준 예시 — 라인업 로테이션됨):
  - `deepseek/deepseek-r1:free`
  - `qwen/qwen3-235b-a22b:free`
  - `meta-llama/llama-3.3-70b-instruct:free`
<details>
<summary>더보기 — 전체 무료 모델 안내</summary>

- 전체 무료 모델: [OpenRouter 모델 목록](https://openrouter.ai/models) — 무료 필터 사용 (모델명 끝에 `:free`, 로테이션됨)

</details>

- 한도: 분당 20회 / 일 50회 (누적 $10 이상 구매 시 일 1,000회)
- API: OpenAI 호환. 엔드포인트 `https://openrouter.ai/api/v1`
- 도구 호출: 무료 라우트별 상이 (각 라우트의 supported_parameters 확인 필요)
- 제한: 카드 불필요. 무료 라우트별 데이터 정책 상이 (일부는 학습 활용 경고 있음). upstream 429 빈발 보고.
- 출처: https://buldrr.com/openrouter-free-api-keys-free-models-simple-guide/
- 비고: Hermes 공식 문서의 기본값이라 설정 예제가 가장 풍부. 일 50회는 에이전트 실사용에 빠듯. $10 1회 충전 시 한도 20배 상승이 가성비 최고.

## Cerebras (이전 조사) <span class="prio p-low">낮음</span>

- 대표 무료 모델:
  - `gpt-oss-120b`
  - `qwen-3.8-27b` — 무료 티어 8K 컨텍스트 제한 보고 있음
- 한도: Free Trial 기준 분당 5회 / 일 100만 토큰
- API: OpenAI 호환. 엔드포인트 `https://api.cerebras.ai/v1`
- 도구 호출: 미확인 (모델별 상이 가능)
- 제한: 카드 불필요. 데이터 학습 활용 정책 미확인.
- 출처: https://inference-docs.cerebras.ai/support/rate-limits
- 비고: 속도 매우 빠름 (최대 ~2000 tok/s). 분당 5회는 병렬 작업 시 빨리 소진되므로 폴백용 적합.

## GitHub Models <span class="prio p-low">낮음</span>

- 대표 무료 모델 (사용성 순):
  - `openai/gpt-5`
  - `openai/o3`
  - `deepseek/DeepSeek-R1`
<details>
<summary>더보기 — 전체 무료 모델 목록</summary>

- `openai/gpt-5-mini`, `openai/gpt-4o`, `meta/Llama-3.3-70B-Instruct`, `xai/grok-3`, `mistral-ai/Mistral-Medium-3`, `cohere/Cohere-Command-A` 등 16개 (목록 변동 가능)
- 전체 목록: [GitHub Models 마켓플레이스](https://github.com/marketplace/models)

</details>

- 한도: 무료 티어 기준 분당 약 15회 / 일 150회 / 분당 8K 토큰. 호출당 토큰 제한이 매우 낮음 (입력 약 8K / 출력 약 4K).
- API: OpenAI 호환. 엔드포인트 `https://models.github.ai/inference`, models scope가 있는 GitHub PAT로 인증.
- 도구 호출: 모델별 상이 (미확인 — OpenAI 모델 계열은 일반적으로 지원)
- 제한: 카드 불필요(GitHub 계정만). 한도가 Copilot 구독 등급과 연동됨. 호출당 토큰 제한이 낮아 긴 컨텍스트 에이전트 작업에는 부적합.
- 출처: https://github.com/ishandutta2007/awesome-llm-apis-free , https://freellm.net/providers/github-models
- 비고: Hermes 연결 가능. GPT-5/o3를 무료로 쓸 수 있는 몇 안 되는 곳이나, 8K/4K 토큰 제한 때문에 에이전트 메인보다는 짧은 작업용 폴백으로 적합.

## LLM7.io <span class="prio p-low">낮음</span>

- 대표 무료 모델 (사용성 순):
  - `GLM-5.3-Flash`
  - `minimax-m2.7`
  - `codestral-latest`
<details>
<summary>더보기 — 전체 무료 모델 목록</summary>

- `mistral-Nemo-Instruct-2407` (turbo 티어 — "turbo"는 익명/무료 토큰 사용자가 쓸 수 있는 빠른 모델 그룹)
- 전체 목록: [LLM7.io](https://llm7.io)

</details>

- 한도: 익명(키 없음) — 초당 1회 / 분당 10회 / 시간당 60회 / 24시간 50만 토큰. 무료 토큰(dash.llm7.io 발급) — 분당 40회 / 시간당 100회 / 24시간 100만 토큰.
- API: OpenAI 호환. 엔드포인트 `https://api.llm7.io/v1`. 익명 사용 시 api_key에 "unused" 입력.
- 도구 호출: 미확인
- 제한: 카드·가입 불필요(익명 가능). 운영자가 upstream을 공개하지 않음. 무료 모델 구성이 변경될 수 있음.
- 출처: https://github.com/mvalentsev/awesome-free-ai-coding/blob/HEAD/providers/llm7.md , https://github.com/velo4705/awesome-free-byok-models
- 비고: Hermes 연결 가능. 가입 없이 바로 쓸 수 있어 테스트용으로 가장 간편. 단, 익명 티어의 분당 10회는 에이전트 루프에 빠듯하므로 무료 토큰 발급 권장.

## Cline <span class="prio p-no">연동 불가</span>

- 무료 모델: Cline 계정 사용자에게 제공되는 기간 한정 무료 모델 프로모션 (모델 목록은 로테이션되며, 2026-09-17 기준 deepseek-v4-flash 제외 등 변동). 고정된 무료 모델 ID 목록 없음.
- 한도: 프로모션별 일일 사용량 제한 — 구체 수치 미확인
- API: **미지원**. 공식 문서 명시: "Free model usage is not supported through the Cline API. Free models are only available in the Cline IDE Extension and CLI."
- 도구 호출: 해당 없음 (API 미제공)
- 제한: 무료 모델 사용 데이터가 모델 개선에 활용될 수 있음. 무료 할당량 소진 후 ClinePass($9.99/월) 또는 usage-billing 전환.
- 출처: https://docs.cline.bot/getting-started/free-models
- 비고: Cline은 API 제공자가 아니라 VS Code/JetBrains/CLI용 코딩 에이전트 도구임. Hermes Agent에 연결할 수 없으므로 조사 대상에서 제외. 형님께 "Cline 무료 모델은 Cline 안에서만 쓸 수 있다"고 안내 필요.

## 변경 이력

- 2026-09-24: 성능 비교 링크를 상단 표(compare=, 5종) + 하단 차트(models=, 7종) 복합 형태로 개선.

- 2026-09-24: 성능 비교에 파라미터 포함 비교 링크 추가 (추천 무료 4종 + 프론티어 3종), 더보기 뒤 빈 줄 추가로 목록 서식 수정.

작성 규칙: `- YYYY-MM-DD: 변경 내용 (출처: URL)` 형식으로 한 줄 요약. 본문은 항상 최신 상태로 유지하고, 바뀐 사실만 여기에 날짜순으로 추가함.

- 2026-09-24: 기준선 최초 작성 (11개 제공자).
- 2026-09-24: 파일 형식 개편 — 제공자를 사용 우선순위 순으로 정렬, 각 제공자 대표 모델 3개 + 나머지 '더보기' 접기 구조 적용, Cline을 '연동 불가' 섹션으로 분리.
- 2026-09-24: 페이지 피드백 반영 — 대표 모델 목록화, 더보기 공식 링크화, 우선순위 색상 뱃지, 성능 비교 섹션 추가.
