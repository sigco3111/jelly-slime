# 🟣 jelly-slime

> Matter.js Soft Body로 구현된 거대한 네온 슬라임을 마우스로 잡아당기고, 늘리고, 벽에 던지세요 — Spring-Mass 제약이 출렁이며 돌아옵니다.

화면 중앙의 거대한 네온 슬라임이 마우스 드래그를 따라 늘어나고, 벽에 부딪힐 때마다 찌그러지며 출렁거리는 인터랙티브 웹페이지. Matter.js Soft Body 컴포지트(Spring-Mass 제약) + Canvas 2D 렌더링으로 구현했습니다. 외부 의존성은 Matter.js 단 하나, 단일 HTML 파일에 모든 코드가 담겨 있습니다.

---

## 🎬 라이브 데모 (Live Demo)

> **👉 [https://jelly-slime.vercel.app/](https://jelly-slime.vercel.app/)** — 브라우저에서 바로 실행

| | |
|---|---|
| ![Demo](https://img.shields.io/badge/Live-Demo-7C3AED?style=for-the-badge&logo=vercel&logoColor=white) | [![Repo](https://img.shields.io/badge/GitHub-sigco3111%2Fjelly--slime-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/sigco3111/jelly-slime) |
| ![Status](https://img.shields.io/badge/Status-Live-22C55E?style=flat-square) | ![Stack](https://img.shields.io/badge/Stack-Vanilla_JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black) |
| ![License](https://img.shields.io/badge/License-MIT-F1C40F?style=flat-square) | ![Deps](https://img.shields.io/badge/Dependencies-1_(Matter.js)-9CA3AF?style=flat-square) |

### 🎮 빠른 사용법
1. 위 데모 링크 클릭 → 브라우저에서 페이지 열기
2. **마우스로 슬라임 잡아당기기** — 젤리처럼 늘어남
3. **마우스 떼기** — 튕기며 제자리로 돌아옴
4. **벽 쪽으로 드래그** — 부딪히면 찌그러지며 출렁거림

---

## 🤖 생성 정보 (Attribution)

이 프로젝트의 코드는 아래 모델과 프롬프트를 이용해 **자동으로 생성**되었습니다.

| 항목 | 값 |
|---|---|
| **모델** | MiniMax-M3 |
| **실행 환경** | OpenCode CLI |
| **저장소** | [`sigco3111/jelly-slime`](https://github.com/sigco3111/jelly-slime) |
| **라이선스** | MIT |
| **의존성** | 1개 (Matter.js, CDN 핀) |

### 📝 사용된 프롬프트 (원문)

```
마우스로 잡아당기면 젤리처럼 늘어났다가 튕겨 나가는 탄성 물리 엔진(Spring-Mass System)이 적용된
거대한 네온 색상의 슬라임 덩어리를 화면 중앙에 구현하고, 슬라임 내부의 노드들이 서로 연결된
그물망 구조가 시각적으로 보이면서 벽에 부딪힐 때마다 찌그러지며 출렁거리는 질감이 느껴지는
인터랙티브 웹페이지를 작성해줘.
Implementation Advice: Use Matter.js (Physics logic) specifically its "Soft Body" features
(composites of constraints). Alternatively, implement a custom Spring-Mass system using
Verlet Integration on Canvas if external libraries are restricted.
모든 의존관계의 코드를 하나의 HTML에 담는 형태로 코드 작성.
```

---

## ✨ 주요 특징 (Features)

- 🧬 **Soft Body 물리** — Matter.js `Composites.softBody()` + Spring-Mass 제약 기반
- ✋ **마우스 드래그** — 임의 노드 잡아당겨 슬라임 형태 변형
- 💥 **벽 충돌 출렁임** — viscous damping + 구조 제약으로 자연스러운 찌그러짐
- 🔬 **그물망 시각화** — 내부 spring/constraint 연결 구조가 실시간으로 보임
- 🌈 **네온 발광** — additive blending + 다중 그림자로 캔디 글로우 효과
- 📦 **단일 HTML** — Matter.js CDN 핀, 외부 빌드/번들 없음

---

## 🚀 실행 방법 (Quick Start)

### 방법 1: 라이브 데모 (가장 간단)
위 **https://jelly-slime.vercel.app/** 링크 클릭만 하면 됩니다.

### 방법 2: 그냥 브라우저로 열기
```bash
git clone https://github.com/sigco3111/jelly-slime.git
cd jelly-slime
open index.html        # macOS
xdg-open index.html    # Linux
start index.html       # Windows
```

### 방법 3: 로컬 서버 (권장)
```bash
python3 -m http.server 8000
# → http://localhost:8000
```

> 🛜 **오프라인 주의**: Matter.js는 CDN에서 핀(`<script>` 태그에 URL 명시). 한 번 온라인에서 열면 브라우저 캐시에 저장되어 이후 오프라인에서도 동작합니다.

---

## 🎮 조작법 (Controls)

| 입력 | 효과 |
|---|---|
| **마우스 드래그** | 슬라임 노드를 잡아당겨 늘어남 |
| **마우스 떼기** | 스프링이 끌어당겨 제자리로 튕김 |
| **빠른 드래그** | 슬라임 전체에 관성 전달 → 벽에 던질 때 효과적 |
| **벽 충돌** | 자동 출렁임 + 그물망 재배열 |

---

## 🛠️ 기술 스택 (Tech Stack)

| 영역 | 사용 기술 |
|---|---|
| **물리 엔진** | Matter.js (Soft Body Composites, Spring-Mass Constraints) |
| **렌더링** | HTML5 Canvas 2D Context |
| **그물망 시각화** | Custom Canvas overlay (constraints 라인 렌더링) |
| **마우스 입력** | Matter.js MouseConstraint |
| **루프** | `requestAnimationFrame` (Matter.js Engine Runner) |
| **의존성** | 1개 (Matter.js, CDN 핀) |

---

## 📂 프로젝트 구조

```
jelly-slime/
├── index.html      # 단일 HTML (HTML + CSS + Matter.js 임포트 + 모든 JS 포함)
├── README.md       # 한국어
└── .gitignore
```

---

## 🎨 디자인 결정 (Design Choices)

브레인스토밍 단계에서 내린 결정 4가지:

| 결정 포인트 | 선택 | 이유 |
|---|---|---|
| **물리 엔진** | Matter.js Soft Body | 검증된 spring-mass 시스템 + 마우스 제약 통합이 가장 단순 |
| **렌더 모드** | 모든 spring/constraint 가시화 | "내부 그물망 구조"라는 요구사항과 직접 일치 |
| **색상 팔레트** | 네온 마젠타 + 시안 액센트 | 배경 다크에 형광 발광이 가장 효과적 |
| **감쇠 정책** | viscous damping + 구조 제약 유지 | 충돌 후 출렁임은 유지하되 슬라임이 깨지진 않음 |

### 직접 커스터마이즈하고 싶다면

`index.html` 상단/물리 부분에서 다음 상수를 조정하면 분위기를 바꿀 수 있어요:

```js
// Matter.js Composites.softBody 옵션
{
  stiffness: 0.05,        // 낮출수록 부드럽고 늘어짐 (0.01 ~ 0.2)
  damping: 0.1,           // 높일수록 충돌 후 빨리 가라앉음 (0.0 ~ 1.0)
  frictionAir: 0.01,      // 공기 저항
  render: { visible: true } // 그물망 가시화 on/off
}
```

고급 사용자용: `Matter.js` 대신 **Verlet Integration + Canvas** 직접 구현으로 바꿔서 의존성을 0으로 만들 수도 있어요 (프롬프트의 `Implementation Advice` 두 번째 옵션).

---

## 🧩 확장 아이디어 (Roadmap)

- [x] Spring-Mass 슬라임 코어 동작
- [x] 마우스 드래그 인터랙션
- [x] 벽 충돌 시 출렁임
- [x] 그물망 시각화
- [ ] 슬라임 다중 프리셋 (젤리 큐브 / 도넛 / 별)
- [ ] 터치 + 멀티터치 (모바일)
- [ ] 충돌 사운드 (thwack 효과)
- [ ] 물리 튜닝 UI (stiffness/damping 슬라이더)

---

## 📜 License

MIT © 2026 sigco3111

---

## 🙏 Acknowledgments

이 프로젝트는 [OpenCode CLI](https://github.com/sicknco/opencode) 환경에서 **MiniMax-M3** 모델로 생성되었습니다. 프롬프트 엔지니어링과 디자인 결정은 저장소 소유자가 직접 수행했습니다.

- **코딩미션 참조 페이지**: [cokac.com — 코드깎는노인](https://cokac.com/list/announcement/24)

<p align="center"><sub>🟣 Generated via OpenCode / MiniMax-M3 · sigco3111 · MIT</sub></p>
