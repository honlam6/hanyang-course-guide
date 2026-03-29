# 한양대학교 수강후기 시스템

[中文](./README.md) | [English](./README.en.md)

한양대학교 학생을 위한 수강후기, 시간표, AI 기반 수강 보조 웹사이트입니다.

- 라이브 데모: <https://hanyang.eu.cc>
- GitHub 메타데이터: [docs/github-metadata.md](./docs/github-metadata.md)
- 아키텍처 및 사이트 로직: [docs/architecture.md](./docs/architecture.md)
- 데이터 처리 설명: [docs/data-source.md](./docs/data-source.md)
- 데이터 구성 개요: [docs/data-model.md](./docs/data-model.md)
- 기여 가이드: [CONTRIBUTING.md](./CONTRIBUTING.md)
- 보안 안내: [SECURITY.md](./SECURITY.md)

## 미리보기

### Desktop

![Desktop Demo](./docs/images/homepage-desktop.png)

### Mobile

![Mobile Demo](./docs/images/homepage-mobile.png)

## 프로젝트 개요

현재 프로젝트에는 다음 기능이 포함됩니다.

- 강의 탐색, 검색, 필터링
- 강의 상세 페이지
- 시간표 기능
- 시간 충돌 감지
- 후기 및 정정 제출
- 관리자 검수 흐름
- AI 수강 도우미

## 핵심 아이디어

이 프로젝트의 핵심은 Everytime 내용을 그대로 옮기는 데 있지 않습니다.

더 중요한 부분은 흩어진 후기 신호를 강의 단위의 안정적인 정보층으로 바꾸는 것입니다.

전체적인 접근은 다음과 같습니다.

1. Everytime 관련 페이지에서 강의 정보와 사용자 후기를 정리한다
2. 같은 강의에 대한 여러 후기를 함께 해석한다
3. AI를 사용해 강의 단위의 요약과 결론을 만든다
4. 이렇게 만든 강의 프로필을 검색, 추천, 질의응답, 화면 표시에 활용한다

즉 사용자가 보게 되는 것은 원본 후기 묶음이 아니라, 정리되고 통합된 강의 정보층입니다.

데이터 수집이나 처리 방식은 다른 방법을 써도 괜찮습니다.

## AI 요약과 질의응답 강화

이 부분이 프로젝트의 핵심 레이어입니다.

AI는 단순 채팅에만 쓰이지 않습니다. 먼저 후기 요약에 쓰이고, 그 다음 질의응답 단계에 다시 활용됩니다.

큰 흐름으로 보면:

- 여러 사용자 후기가 강의 단위 지식으로 요약되고
- 그 요약이 검색 가능한 형태로 조직되며
- 사용자의 질문은 관련 내용 검색을 거친 뒤 답변이 생성되고
- 모델 연동은 Google Gemini API 를 중심으로 구성됩니다

그래서 이 프로젝트의 AI 계층은 단순 챗봇보다는, 검색 증강형 강의 정보 시스템에 가깝습니다.

## 시간표와 충돌 감지

웹사이트에는 시간표 기능도 포함되어 있습니다.

사용자가 강의를 시간표에 추가하면 시스템이 자동으로 시간 충돌을 감지하며, 시간표 화면은 이미지로 내보낼 수도 있습니다.

## 데이터 설명

이 공개 저장소에는 제품 구조, 공개 Web 스택, 통합 수준의 설명이 포함됩니다.

데이터 구성과 처리 방식은 개요 수준으로 설명하고, 핵심 구현 세부사항은 그대로 두지 않습니다.

참고:

- [docs/data-source.md](./docs/data-source.md)
- [docs/data-model.md](./docs/data-model.md)
- [docs/architecture.md](./docs/architecture.md)

## 로컬 실행

```bash
npm install
cp .env.example .env
npm run dev
```

기본 주소:

- 프런트엔드: `http://localhost:3000/`
- 관리자: `http://localhost:3000/admin`

데이터베이스 초기화:

- Supabase SQL Editor 에서 [`supabase_setup.sql`](./supabase_setup.sql) 실행

## 다른 한국 대학으로의 확장

현재 프로젝트는 한양대학교를 기준으로 설계되었지만, 전체 방법론은 특정 학교에만 묶여 있지 않습니다.

다른 한국 대학으로 확장하려면 학교 명칭, 캠퍼스 체계, 강의 분류, 데이터 소스, AI 요약 전략 등을 다시 설계하면 됩니다.

보다 정확한 표현은 다음과 같습니다.

- 현재 제품: 한양대학교 수강후기 시스템
- 방법론: 다른 한국 대학으로 확장 가능
