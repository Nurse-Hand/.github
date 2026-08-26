![Nurse Hand app screens](./assets/nurse-hand-hero.png)

<p align="center">
  <img src="./assets/nurse-hand-demo.gif" alt="Nurse Hand demo video" width="280" />
</p>

<h1 align="center">Nurse Hand</h1>

<p align="center">
  라운딩 중 남긴 기록을 환자별 타임라인, 업무 우선순위, 인수인계 근거로 이어주는 간호사 업무 보조 앱
</p>

<p align="center">
  <a href="https://github.com/Nurse-Hand/client">Client</a>
  ·
  <a href="https://github.com/Nurse-Hand/server">Server</a>
  ·
  <a href="https://github.com/Nurse-Hand/ai">AI</a>
</p>

---

## 핵심 기능

| 기능 | 앱에서 하는 일 |
| --- | --- |
| 라운딩 중 기록 | 환자별 음성, 메모, 사진을 라운딩 흐름 안에서 남깁니다. |
| 라운딩 종료 후 검토 | 전체 기록을 시간순으로 확인하고 필요한 항목을 수정합니다. |
| AI 인수인계 확인 | 기록과 근거를 바탕으로 누락 가능 항목을 검토합니다. |
| 업무 우선순위 | 미완료 업무를 환자 상태, 마감 시각, 이월 여부 기준으로 정렬합니다. |

## 사용 흐름

1. 홈에서 라운딩을 시작합니다.
2. 환자별로 음성, 메모, 사진을 남깁니다.
3. 라운딩 종료 후 기록을 환자별로 확인합니다.
4. 업무 우선순위와 인수인계 초안을 검토합니다.
5. 간호사가 근거를 확인하고 최종 저장합니다.

## Repository

| Repo | 역할 |
| --- | --- |
| [`Nurse-Hand/client`](https://github.com/Nurse-Hand/client) | React Native 앱 화면과 모바일 라운딩 흐름 |
| [`Nurse-Hand/server`](https://github.com/Nurse-Hand/server) | 공개 API, 파일 저장, 라운딩/업무/인수인계 데이터 처리 |
| [`Nurse-Hand/ai`](https://github.com/Nurse-Hand/ai) | STT, 화자 분리, 업무/인수인계 판단 보조 |

## MVP API 연결

| 화면 흐름 | 주요 API |
| --- | --- |
| 라운딩 시작 | `POST /api/v1/rounding-sessions` |
| 환자별 기록 저장 | `POST /api/v1/rounding-sessions/{sessionId}/records` |
| 라운딩 음성 청크 저장 | `POST /api/v1/rounding-sessions/{sessionId}/audio-chunks` |
| 환자 타임라인 조회 | `GET /api/v1/patients/{patientId}/timeline` |
| 업무 우선순위 확인 | `GET /api/v1/tasks`, `POST /api/v1/task-priority-suggestions` |
| 인수인계 검토 | `POST /api/v1/handoff-prechecks`, `POST /api/v1/handoffs` |
