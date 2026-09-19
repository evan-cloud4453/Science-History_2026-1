# 과학사 상식 퀴즈
### History of Science : Interactive Quiz

> 세종대학교 2026학년도 1학기 「과학사」 수업의 주차별 퀴즈를,
> 고대 이집트 테마의 학습 게임으로 다시 만든 웹 애플리케이션입니다.

**▶ 바로 플레이 : https://evan-cloud4453.github.io/Science-History_2026-1/**

![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-live-2ea44f?logo=github)
![HTML5](https://img.shields.io/badge/HTML5-single%20file-E34F26?logo=html5&logoColor=white)
![Vanilla JS](https://img.shields.io/badge/Vanilla%20JS-no%20build-F7DF1E?logo=javascript&logoColor=black)
![Questions](https://img.shields.io/badge/questions-214-d4af37)

---
<details>
<summary><b>English Summary</b></summary>

A single-file, dependency-free quiz app built for the *History of Science* course
(Sejong University, Spring 2026). It started as my own review tool for the weekly
quizzes and the midterm/final exams, then grew into a Duolingo-style learning game
so that classmates could study the same material with a bit more fun.

- **214 O/X questions across 14 weekly chapters**, each with a written explanation
- **Instant grading** — the answer and the rationale appear the moment you choose
- **Ancient-Egyptian dark theme**, background music, and correct/wrong sound effects
- **Local progress records + a "wrong-answer notebook"**, persisted in `localStorage`
- **No build step, no backend, no dependencies** — just open `index.html`

Quiz items are taken from Prof. **Jeong Yeon-cheol**'s *History of Science* lectures
at Sejong University and are used for non-commercial study purposes only.
</details>
---

## 개발 배경

이 프로젝트는 처음부터 서비스로 기획한 것이 아니라, **제 시험공부용 도구**로 시작했습니다.

2026학년도 1학기에 듣는 「과학사」 수업은 매주 퀴즈가 있었고, 중간고사와 기말고사도
그 퀴즈 범위에서 크게 벗어나지 않았습니다. 처음에는 문제를 한곳에 모아 반복해서 풀
수 있게 만드는 것이 전부였습니다.

개발을 진행하면서 목표를 한 단계 확장했습니다. 개인용 문제 풀이 페이지에 그치지 않고
**학습 동기를 유지시키는 구조를 갖춘다면 같은 수업을 듣는 다른 수강생에게도 쓸모가 있다고
판단**했기 때문입니다.

그래서 단순한 문제 풀이 페이지 대신, 듀오링고처럼 **학습을 게임화(gamification)** 하는
방향으로 방향을 틀었습니다. 과목이 과학사인 만큼 테마는 고대 문명 — **이집트 신전**
콘셉트로 잡았고, UI 문구도 세계관에 맞췄습니다.

| 일반적인 표현 | 이 앱에서의 표현 |
|---|---|
| 메인 화면으로 | **신전으로 돌아가기** |
| 학습 기록 | **과거의 기록 / 보관된 고문서** |
| 오답 노트 | **비망록** |
| 점수 | **지혜의 증명** |
| 기록 초기화 | **⚠ 모든 학습 기록 파기** |

황금색(`#d4af37`)과 명조 계열 서체(Noto Serif KR), 어두운 배경과 은은한 글로우를 조합해
고문서를 열람하는 듯한 화면을 구성했습니다. 정답·오답 효과음과 배경음악은 반복 학습 과정에서
집중이 흐트러지는 것을 완화하기 위해 추가한 요소입니다.

개인 학습 자료에서 출발했으나 **같은 수업을 듣는 수강생이라면 링크 하나로 접속해 바로
복습할 수 있는 형태로 공개했다는 점**에 이 프로젝트의 의의가 있습니다.

---

## 주요 기능

### 학습
- **주차별 챕터 선택** — 14개 챕터, 총 214문항
- **주차별 시간차 공개** — 각 챕터에 `releaseDate`가 지정되어 있어, 학기 진도에 맞춰
  아직 배우지 않은 주차는 `[N주차] (05.19 공개)` 형태로 잠글 수 있습니다.
  (학기가 끝난 현재는 전 주차가 열려 있습니다.)
- **즉시 채점 + 해설** — 보기를 고르는 즉시 정답 여부, 정답, 그리고 해설이 함께 표시됩니다.
  틀린 보기는 붉게, 정답 보기는 초록으로 동시에 표시되어 무엇을 잘못 알고 있었는지 바로 보입니다.
- **진행도 바** — 상단의 칸이 현재 위치(금색) / 정답(초록) / 오답(빨강)으로 채워집니다.
- **이전 · 다음 자유 이동** — 이미 푼 문제로 돌아가면 선택했던 답과 해설이 그대로 복원됩니다.

### 기록
- **나의 기록 열람** — 퀴즈를 끝내면 주차·날짜·점수와 함께 모든 문항의 풀이 내역이 저장됩니다.
- **비망록(오답 노트)** — 기록별로 문항 / 내가 고른 답 / 정답 / 해설을 카드 형태로 다시 볼 수 있습니다.
- **기록은 전부 내 브라우저 안에만** 저장됩니다 (`localStorage`). 서버로 전송되는 데이터가 없습니다.
- **전체 기록 파기** — 환경 설정에서 저장된 기록을 한 번에 삭제할 수 있습니다.

### 연출 · 편의
- **BGM 자동 전환** — 메인 화면 BGM과 퀴즈 전용 BGM이 화면 전환에 맞춰 자연스럽게 교체됩니다.
- **정답 / 오답 효과음**
- **배경음 · 효과음 분리 조절** — 각각 볼륨 슬라이더와 음소거 버튼을 따로 둡니다.
- **설치 불필요 · 모바일 대응** — 브라우저만 있으면 되고, 화면 폭에 맞춰 레이아웃이 조정됩니다.

---

## 챕터 구성

| 주차 | 주제 | 문항 수 |
|:--:|---|:--:|
| 1 | 역사와 과학사 | 16 |
| 2 | 자연철학과 소피즘 | 17 |
| 3 | 에라토스테네스와 앙부일구 | 15 |
| 4 | 과학혁명의 구조 | 15 |
| 5 | 고대의 종말과 중세 | 15 |
| 6 | 이슬람 과학과 르네상스 | 15 |
| 7 | 과학혁명기 | 15 |
| 8 | *중간고사 주간 (수업 없음)* | — |
| 9 | 과학방법론과 생리학 | 15 |
| 10 | 근대과학과 계몽주의 | 16 |
| 11 | 산업혁명, 화학혁명, 프랑스대혁명 | 15 |
| 12 | 지질학혁명과 진화론 | 15 |
| 13 | 진화론과 유전학 | 15 |
| 14 | 열역학, 전자기학, 상대성이론 | 15 |
| 15 | 양자역학, 원자폭탄 | 15 |

**총 14개 챕터 · 214문항** (전 문항 O/X 형식, 모든 문항에 해설 포함)

---

## 사용 방법

### 온라인 (권장)
아래 링크로 접속하면 끝입니다. 설치도, 로그인도 없습니다.

**https://evan-cloud4453.github.io/Science-History_2026-1/**

### 로컬에서 실행

```bash
git clone https://github.com/evan-cloud4453/Science-History_2026-1.git
```

클론한 폴더의 `index.html`을 브라우저로 열면 됩니다. 서버를 띄울 필요가 없습니다.

> 브라우저의 자동재생 정책 때문에 **배경음악은 페이지에서 아무 곳이나 한 번 클릭한 뒤**
> 재생되기 시작합니다. 정상 동작입니다.

---

## 기술 구성

| 항목 | 내용 |
|---|---|
| 구조 | **단일 HTML 파일** (`index.html`, 약 2,100줄) — 마크업 · 스타일 · 로직 · 문항 데이터가 모두 인라인 |
| 프레임워크 | 없음. **Vanilla JavaScript** (빌드 · 번들러 · 패키지 매니저 · 백엔드 전부 불필요) |
| 스타일 | CSS 변수 기반 다크 테마, Flexbox 레이아웃, `@keyframes` 화면 전환 애니메이션 |
| 서체 | Noto Serif KR (Google Fonts) |
| 저장 | 브라우저 `localStorage` (키: `scienceQuizRecords`) |
| 오디오 | HTML5 `<audio>` 4트랙 (메인 BGM / 퀴즈 BGM / 정답음 / 오답음) |
| 배포 | GitHub Pages (`main` 브랜치 루트) |

```
Science-History_2026-1/
├── index.html      # 앱 전체 (UI + 로직 + 문항 214개 + 해설)
├── bgm.mp3         # 메인 화면 배경음악
├── quiz_bgm.mp3    # 퀴즈 화면 배경음악
├── correct.mp3     # 정답 효과음
└── wrong.mp3       # 오답 효과음
```

의존성을 두지 않은 것은 의도한 선택입니다. 수강생이 링크를 열면 즉시 동작해야 했고,
학기가 끝난 뒤에도 파일 하나만으로 유지될 수 있어야 했기 때문입니다.

---

## 문항 데이터 구조

문항은 `index.html` 안의 두 자료구조로 관리됩니다.

```js
// 1) 챕터 목록 — 제목과 공개 시점
const chaptersInfo = [
    { id: 1, title: "역사와 과학사", releaseDate: new Date("2000-01-01T00:00:00") },
    { id: 2, title: "자연철학과 소피즘", releaseDate: new Date("2000-01-01T00:00:00") },
    // ...
];

// 2) 챕터 id를 키로 하는 문항 배열
const quizData = {
    1: [
        {
            q: "역사학의 목적은 진리를 발견하는 것이다.",
            options: ["O", "X"],
            answer: "X",
            rationale: "교안에 따르면 역사학의 목적은 단 하나의 절대적 진리를 발견하는 것이 아니라, 세상을 다르게 보고 다양하게 보게 하는 비판적 도구로서 기능하는 것입니다."
        },
        // ...
    ],
};
```

- 문항을 추가하려면 `quizData`의 해당 챕터 배열에 객체를 하나 넣으면 됩니다.
- 새 챕터를 만들려면 `chaptersInfo`에 한 줄, `quizData`에 키 하나를 추가합니다.
- `releaseDate`를 미래로 잡으면 그 시점까지 해당 챕터 버튼이 자동으로 잠깁니다.
- 채점 로직은 `options` 배열을 그대로 버튼으로 그리고 `answer` 문자열과 비교하는 방식이라,
  **O/X뿐 아니라 4지선다로도 수정 없이 확장할 수 있습니다.**

---

## 해설은 어떻게 만들었나

각 문항의 `rationale`(해설)은 교수님의 **강의 교안을 근거 자료로 삼아, 생성형 AI를 활용해
초안을 작성한 뒤 정리한 것**입니다. 정답만 제시하는 대신 근거를 함께 제공함으로써,
문항을 암기하는 것이 아니라 맥락을 이해하도록 유도하는 것이 목적이었습니다.

> ⚠️ 해설은 학습 보조 자료입니다. 생성형 AI로 작성한 만큼 표현이나 세부 사실에 오류가
> 있을 수 있으니, 최종적인 근거는 반드시 강의 교안과 수업 내용을 따라 주세요.

---

## 저작권 및 이용 안내

- **문항 출처 : 세종대학교 정연철 교수님 「과학사」 강의 퀴즈.**
  문항의 저작권은 정연철 교수님께 있으며, 이 저장소는 수강생의 복습·시험 대비라는
  **비영리 교육 목적**으로만 이용합니다.
- 해설은 위 강의 교안을 바탕으로 생성형 AI를 활용해 작성한 2차 정리물입니다.
- 오디오 파일(`bgm.mp3`, `quiz_bgm.mp3`, `correct.mp3`, `wrong.mp3`)은 출처가 확인되지
  않은 상태입니다. 권리자의 요청이 있을 경우 즉시 교체하거나 삭제하겠습니다.
- 문의나 삭제 요청은 이 저장소의 Issues로 남겨 주시면 신속히 처리하겠습니다.

---

## 앞으로 개선하면 좋을 것들

- 배경 이미지가 외부 URL을 직접 참조하고 있어, 원본 링크가 사라지면 배경이 깨질 수 있습니다.
  → 로컬 이미지 에셋으로 교체
- O/X 외 4지선다·주관식 문항 유형 추가 (데이터 구조는 이미 대응 가능)
- 오답만 모아서 다시 푸는 **오답 재도전 모드**
- 연속 정답 스트릭 · 챕터 완주 배지 등 게임화 요소 확장
