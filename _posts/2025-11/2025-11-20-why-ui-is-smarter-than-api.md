---
layout: post
title: "ChatGPT/Claude Prompt UI Is Not a Simple UI Layer"
date: 2025-11-20
published: true
categories: [AI]
tags: [AI, Orchestration, RAG, Prompt]
---

*I Built a RAG System in 5 Days. Here's Why It Failed (And What I Learned)*

*5일 만에 RAG 시스템을 직접 구축하며 깨달은 모든 것*

---

![Tutorial RAG vs Real ChatGPT Orchestration](/assets/images/2025-11/2025-11-20-tutorial_vs_real_rag.png)

## *Why ChatGPT/Claude UI feels dramatically smarter than API calls — and why this changed how I think about building AI systems.*

When I spent five days building a RAG system.

On day one, I was confident.
By day three, I was confused.
By day five, I was humbled.

I learned more from this failure than reading tutorials.

Here's what nobody tells you about building AI systems...:

> Upload documents → retrieve → feed into LLM → get nice answers.

I’ve been using ChatGPT Projects and Claude Workspaces intensively for months.
Their reasoning quality, file-aware analysis, and multi-turn consistency feel almost magical.

So I genuinely thought:

> **“If I use their API and build my own RAG system, I should get similar intelligence.”**

But the moment I built it myself, I hit a shock that every real AI architect eventually experiences:

> **My RAG system felt dumb.
> Shallow.
> Inconsistent.
> Easily confused.
> Nothing like ChatGPT or Claude UI.**

At first I wondered:

* Was my architecture wrong?
* Did I choose bad embeddings?
* Is my chunking wrong?
* Should I tune prompts harder?
* Am I missing some magic instruction?

But after days of testing, observing, and using OpenAI/Anthropic prompts side-by-side, I realized a deeper truth:

> **ChatGPT UI ≠ ChatGPT API.
> Claude UI ≠ Claude API.**

The UI is not “just the LLM.”
The UI is an **entire orchestration system** with hidden pipelines, memory, summaries, model routing, multi-pass prompts, and intelligent file processing.

The API is simply the **raw engine**.

My RAG was not dumb —
I simply built **2%** of what ChatGPT has behind the scenes.

And once I understood *why*, everything clicked.

---

## **What’s Actually Happening Behind ChatGPT/Claude UI (The Part I Never Saw)**

Here is what I realized:
When I upload files into ChatGPT Projects or Claude Workspaces, the system runs a **large pipeline** that looks NOTHING like my simple vector DB workflow.

Below is the closest approximation of what’s actually happening under the hood — the stuff nobody sees, but everyone benefits from.

I rewrote this in my own words, based on everything I learned the hard way.

---

## **Step 1 — File Upload = Massive Processing Pipeline**

### **1. File type detection**

```
.py     → parsed into AST (functions, classes, imports)
.md     → hierarchical section parser
.yaml   → schema extraction
.pdf    → text + layout segmentation
```

### **2. Intelligent chunking (not naive fixed-size split)**

* Python → chunk by class/function
* Markdown → chunk by logical section
* Configs → chunk by key/field
* Text → chunk by semantic blocks

Not bitmap splitting.
Not character count splitting.
Not token slicing.

Real structure-aware segmentation.

### **3. Metadata extraction**

```
filename
filetype
import graph
function signatures
docstring summary
referenced files
semantic categories
```

### **4. Embedding creation**

* proprietary embedding models
* optimized for code + prose
* multiple vector indexes:

  * semantic
  * structural
  * dependency-based

In other words:

> **Uploading a file is never just “embedding text.”
> It’s constructing an entire searchable knowledge graph.**

---

## **Step 2 — Query Processing (What Actually Happens When I Ask Something)**

### **1. Intent classification**

My question is classified into categories like:

* “high-level overview”
* “bug diagnosis”
* “security concern”
* “dependency tracing”
* “summarization”
* “rewrite/refactor”

Each intent triggers **different retrieval strategies**.

### **2. Multi-strategy retrieval**

Not just embedding search.

They do:

* semantic retrieval
* keyword fallback
* code graph traversal
* reference resolution
* hybrid reranking

### **3. Reranking & selection**

The system determines:

* which chunks matter
* how deep the explanation should go
* which files must be included
* what order the chunks should appear
* how to balance breadth vs depth

### **4. Context construction**

The UI builds a giant structured prompt containing:

* the selected chunks
* metadata
* file boundaries
* conversation history
* special tags
* internal instructions

This is where my RAG system fails —
because mine simply pasted “top_k chunks” in random order.

---

## **Step 3 — Hidden Prompt Engineering Layer (The Part I Never See)**

This is where the real magic happens.

### **1. System prompt (huge, invisible)**

I never see it, but ChatGPT feeds itself:

```
"You are analyzing a multi-file codebase."
"Always cite sources."
"Maintain file-level consistency."
"Explain dependencies clearly."
"Never hallucinate unknown functions."
...
(1000+ words total)
```

### **2. Metadata injection**

The UI wraps files like:

```
<file name="main.py">
    ...
</file>
```

### **3. Conversation memory**

Older messages aren’t lost — they are:

* compressed
* distilled
* reinserted
* summarized

My API system?
It loses memory instantly unless I manually manage it.

### **4. Final prompt assembly**

The actual prompt going into GPT-4/GPT-o/Gemini/Claude:

* can be **50k–200k tokens**
* extremely structured
* heavily organized
* filled with metadata
* engineered for optimal model behavior

But I only see the **final output**, making everything look “simple.”

---

## **Step 4 — Output Post-Processing**

The UI then:

* inserts citations
* formats code blocks
* detects hallucinations
* applies safety rules
* aligns tone
* ensures quality

And then displays the final answer neatly.

### I only see the top 5% of the entire pipeline.

95% is hidden.

---

## **My Personal Realization: Tutorial RAG Is Just the Doorway**

The more I used my own RAG system, the more I saw the gap:

| ChatGPT/Claude UI      | My RAG                |
| ---------------------- | --------------------- |
| orchestration engine   | simple retrieval      |
| hierarchical chunking  | naive chunking        |
| graph-based reasoning  | semantic-only         |
| memory + summary       | no memory             |
| multi-pass reasoning   | single-pass LLM call  |
| intelligent reranking  | top_k brute force     |
| specialized embeddings | generic embeddings    |
| structured prompt      | sloppy pasted context |

It was humbling.

It forced me to accept:

> **Tutorial RAG is just Chapter 1.
> Real AI system design begins after that.**

The moment you realize this, everything changes.

---

## **So What Should *I* Build Instead?**

This is the conclusion I reached:

### **I shouldn't attempt to copy ChatGPT or Claude’s internal orchestration.**

That would take:

* 50+ engineers
* years of iteration
* proprietary data
* multimodal embeddings
* deeply integrated systems

Instead, what I need is:

### **My own domain-specialized orchestration system**

designed for **my use case**, **my documents**, **my workflows**, and **my domain knowledge**.

A system where:

* I define chunking logic
* I define memory rules
* I define retrieval routing
* I define context construction
* I define evaluation standards
* I design multi-pass reasoning flows
* I enforce my own consistency rules

Something smaller but smarter.
Something achievable.
Something that grows with my research.

This is the path forward.

---

## **Final Reflection — My Breakthrough Understanding**

Building my first RAG system wasn’t just a technical exercise.
It opened my eyes to how **deep** modern AI systems actually are.

I realized:

* ChatGPT Projects and Claude Workspaces feel “smart” because they run dozens of hidden systems.
* API-based RAG feels “weak” because it is literally **only one LLM call**.
* Tutorial RAG is not the solution — it is the *starting point*.
* The true challenge is building **my own orchestration**, not copying theirs.

And in a strange way, this realization gave me real path —
because now I know what the real work is.

Fortunately, I am enjoying this learning!

---

# *ChatGPT/Claude 프로젝트 UI는 단순한 “프롬프트 입력창”이 아니다*

---

## **5일 동안 RAG 시스템을 만들고 그 5일이 내게 준 깨달음**

첫째 날, 자신감에 참.
셋째 날, 혼란스러움.
다섯째 날, 겸손.

튜토리얼보다 실패만 보았다.

처음에는 단순히 이렇게 생각했다:

> 문서 업로드 → 벡터 검색 → LLM에 전달 → 좋은 답변 생성.

그동안 ChatGPT, Claude Projects가 안정적으로 답변할 수 있도록 활용하면서
그들의 **추론 능력**, **파일 감지 능력**, **문맥 유지력**, **다중 턴 일관성**은 거의 신세계처럼 느껴졌다.

그래서 한층 더 나아가서

> **“API로 나만의 RAG 시스템을 만들면, ChatGPT/Claude UI와 훨씬 도움 되는 AI tool을 만들 수 있겠지.”**

하지만 직접 만들어본 순간, 모든 AI 엔지니어가 한 번은 겪는 충격을 맞닥뜨렸다.

> **내 RAG 시스템은 완전 바보라는 것.
> ChatGPT, Claude prompt로 얻어내는 답변과는 비교도 되지 않았다.**

그래서 생각한게

* 구조가 잘못된 건가?
* 임베딩이 문제인가?
* 청킹이 잘못됐나?
* 숨겨진 비밀 설정이 있는 건가?
* 내가 RAG를 완전히 잘못하고 있나?

하지만 API 기반 RAG와 ChatGPT UI를 자세히 비교하면서 알아낸 건:

> **ChatGPT UI ≠ ChatGPT API
> Claude UI ≠ Claude API**

UI는 단순한 LLM 입력창이 아니라는 것.
UI에서 보이는 prompt 뒤로 **파일 처리, 메모리, 요약, 모델 라우팅, 멀티 패스 프롬프트, 구조 기반 청킹 등**으로 이루어진 **완전한 오케스트레이션 시스템**이다.

그리고, API는 단순한 **엔진 그 자체**일 뿐.

결국 RAG 시스템에서 내가 만든 것은 **ChatGPT의 2% 정도**에 불과했던 것이다.

그리고 이 구조를 제대로 이해하자 모든 것이 명확해졌다.

---

# **ChatGPT/Claude UI 뒤에서 실제로 돌아가는 것들**

사실 그동안 사용하면서 파일을 업로드할 때 ChatGPT나 Claude가 어떤 파이프라인을 돌리는지 전혀 몰랐다.

단순하게 만든 만든 벡터 검색 형태의 RAG는 그 시스템과는 **비교도 안 되는 단순한 형태**인데, 뜯어보면 실제로는 다음과 같은 **거대한 파이프라인**이 돌아가고 있다.

---

## **1단계 — 파일 업로드 = 대규모 전처리 파이프라인**

### **① 파일 타입 분석**

```
.py     → AST 분석(함수, 클래스, import 구조)
.md     → 계층적 섹션 파서
.yaml   → 스키마 분석
.pdf    → 텍스트 + 레이아웃 세그멘테이션
```

### **② 지능형 청킹 (단순 분할이 아님)**

* Python → 함수/클래스 단위로
* Markdown → 섹션 단위로
* YAML → 필드 단위로
* 텍스트 → 의미 단락 기준으로

문자 수 기준 분할이 아니다.
토큰 수 기준도 아니다.
**문서 구조 기반 청킹이다.**

### **③ 메타데이터 추출**

```
파일명
타입
의존성 그래프(import graph)
함수 시그니처
docstring 요약
참조된 파일
주제 카테고리
```

### **④ 임베딩 생성**

* 전용 임베딩 모델 (텍스트 + 코드 통합)
* 의미/구조/의존성 기반 다중 벡터 인덱스 생성

즉, 파일 업로드는 단순 “텍스트 임베딩”이 아니다.

> **업로드 = 미니 지식 그래프 구축이다.**

---

## **2단계 — 질문을 입력할 때 실제로 일어나는 일**

### **① 의도 분류**

예: "인증 구조 설명" vs “보안 문제 찾아줘”는 다른 retrieval 전략이 필요하다.

### **② 다중 방식 검색**

다음이 모두 실행됨:

* 의미 기반 검색
* 키워드 기반 보조 검색
* 코드 그래프 탐색
* 참조 파일 추적
* 하이브리드 재랭킹

### **③ 재랭킹**

* 어떤 청크가 중요한가?
* 어느 깊이로 설명해야 하는가?
* 파일 순서를 어떻게 배치할까?
* 대화 흐름과 어떻게 연결할까?

### **④ 문맥 구성**

ChatGPT UI는 거대한 구조화된 프롬프트를 만든다.

* 선택된 청크
* 메타데이터
* 파일 경계
* 대화 기록 요약
* 내부 명령어

내가 만든 RAG는 그냥 “top_k 청크 나열”이었다.

---

## **3단계 — 숨겨진 프롬프트 엔지니어링 레이어**

### **① 내부 시스템 프롬프트 (매우 김)**

보이지 않는 곳에서 ChatGPT는 스스로에게 다음을 말한다:

```
“지금은 다중 파일 코드베이스 분석 모드다.”
“항상 파일명으로 인용하라.”
“종속성 설명을 명확히 하라.”
...
(수천 단어)
```

### **② 파일 메타데이터 주입**

```
<file name="main.py">
    ...
</file>
```

### **③ 대화 요약 + 메모리 관리**

* 이전 대화 요약
* 중요한 사실 추출
* 압축 후 재삽입

내 API 시스템에는 없다.

### **④ 최종 프롬프트 조립**

* 5만~20만 토큰
* 구조화된 giant prompt
* LLM이 가장 잘 이해하도록 최적 구성

우리는 **보여지는 출력만** 본다.

---

## **4단계 — 출력 후처리**

UI는 자동으로:

* 오타/환각 검사
* 코드 포맷팅
* 인용 정리
* 스타일 조정

그리고 깔끔한 답변이 반환된다.

우리가 보는 건 단 5%다.
95%는 보이지 않는다.

---

# **내가 깨달은 핵심: 튜토리얼 RAG는 ‘입구’일 뿐이다**

| ChatGPT/Claude UI | 내가 만든 RAG   |
| ----------------- | ----------- |
| 오케스트레이션 엔진        | 단순 호출       |
| 구조 기반 청킹          | naive 분할    |
| 그래프 기반 추론         | 단순 semantic |
| 멀티 패스 추론          | 단일 호출       |
| 동적 메모리            | 없음          |
| 지능형 재랭킹           | top_k brute |
| 고급 임베딩            | 일반 임베딩      |
| 구조화된 거대 프롬프트      | 그냥 붙여넣기     |

그래서 이걸 보면 솔직히 인정할 수 밖에 없다.

> **튜토리얼 RAG는 챕터 1이다.
> 본격적인 AI 시스템 설계는 그 이후에서 시작한다.**

---

# **그래서 무엇을 만들어야 할까?**

나의 결론은:

### **ChatGPT/Claude의 내부 시스템을 그대로 복제하려 해서는 안 된다.**

대충 보아도 ChatGPT/Claude의 내부 시스템에서는:

* 수십 명의 엔지니어
* 수년의 반복
* 수십억 건의 데이터
* 자체 모델/임베딩/메모리

이 필요한 일을 해낸 것이다.

그래서 나 같은 소형화된 프로젝트에서라면:

### **나만의 도메인 특화 오케스트레이션 시스템**

* 내가 다루는 문서
* 내가 만든 리서치
* 내가 원하는 추론 방식
* 나의 프로젝트 워크플로우

여기에 최적화된 시스템을 추구해야 된다는 것.

즉, 내가 만든 문서 구조 및 시스템 로직에만 맞는:

내가 정한 청킹 규칙
내가 정한 메모리 규칙
내가 정한 retrieval flow
내가 정한 context 재구성
내가 정한 multi-pass reasoning

등등을 직접 설계하는 것이다.

규모는 작지만, 똑똑한 시스템.
복잡하지 않지만, 실용적인 시스템.
튜토리얼을 넘어, *나만의 시스템.*

그래서 이 조금한 AI 시스템에서는 원하는 답변을 제대로 답변해나가는 것.
그것이 올바른 시스템 구축의 방향이 아닐까 생각한다.

---

# **마지막 깨달음 — 드디어 실체에 접근해 보았다.**

RAG 시스템을 만들면서 나는 LLM 모델 뒤로 일어나는 일에 대해서 처음으로 몸서 느끼게 된 것 같다.

* ChatGPT/Claude가 “똑똑해 보이는 이유”는 숨겨진 시스템 때문이다.
* API 기반 RAG는 “엔진만 노출”된 상태다.
* 튜토리얼 RAG는 정답이 아니라 **입구**다.
* 진짜 시스템은 **오케스트레이션**이다.
* 그 오케스트레이션은 **각자의 도메인에 맞게** 직접 설계해야 한다.

그리고 이런 경험 때문에 방향도 보이게 된 것 같다.

> 무엇을 더 배워야 할지도 알게 되었고, 내가 만들고 시스템에 대해 보다 진지한 생각을 하게 되었다.

생각보다 재미있는 여정이라 다행이라고 생각한다.