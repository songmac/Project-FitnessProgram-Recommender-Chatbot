# 프로젝트 개요

## 1. 기획단계 (Planning)

- **프로젝트 배경 및 주제 선정 아이디어 개념 소개**
- **데이터 수집 플랫폼 소개 및 데이터 후보 선정**
  - K-ICT 빅데이터센터, 공공데이터포털, 서울열린데이터광장, 구별 시설 공단
- **프로젝트 환경 구축 및 사용한 툴 소개**
  - git, vscode, colab, excel, API, mokaroo
- **피드백 사항**
  - filtering 기능 구현 정도에 그치는 것 같음 → 오픈AI API를 사용해서 자연어 처리로 입/출력 단계를 구현하면 의미있는 프로젝트가 될듯 함

## 2-1. 개발 단계 - 데이터전처리 (Data Feature Extraction)

### 1) 공공데이터 선정 및 전처리

- **지자체별공공체육시설현황데이터 정제 및 전처리**
- **정제 및 전처리 기준 설명**
- **복합 프로그램의 경우 강습프로그램이 아닌 것들을 제외**

### 2) 리뷰 데이터 항목 생성

- **사용자기본정보를 포함한 운동선호도 리뷰 샘플데이터 생성**
- **피드백 사항**
  - 사용자 선호도에 대한 기준이 명확하게 와닿지 않고, 개인 맞춤화된 추천을 위해서는 카테고리에 대한 세분화와 함께 사용자에게 안내하는 화면이 구현될 것을 생각하여 샘플 데이터를 생성해야 할 듯함

### 3) Unique한 리뷰샘플데이터 재생성

- **프로그램명-운동목표-건강상태의 연관성을 고려하여 데이터프레임을 프로그램명으로 매칭**
- **피드백 개선으로 Unique한 프로그램ID 구성**

## 2-2. 개발 단계 - OpenAI API 연동

### 1) 연동 test

- **OpenAI API key 발급 및 패키지 설치**
- **토큰 결제 및 기술 사용 요금 확인**

### 2) 사용자 선호도 데이터로 질문 구성

- **선호도 항목을 부드럽게 질문하도록 수정 진행**
- **건강상태의 기준이 불명확하여 개인의 병력은 고려하지 않기로 함함**

### 3) 룰기반/랭체인기반 입출력 테스트

- **룰기반 및 랭체인기반 테스트 결과와 이슈 해결 방안**

### 4) 챗봇 형태로 사용자에게 정보 제공

- **피드백 사항**
  - 추천 모델링 결과를 기반으로 사용자 정보에 맞게 필터링하는 기본적인 코드 구현
  - 여력이 된다면 랭체인 방법도 진행

### 5) 반응형 인터페이스로 UI 구성

- **Panel 라이브러리를 활용한 초기 인터페이스 구현**
- **UI 디자인 작업 진행**

## 2-3. 개발 단계 - 추천시스템 모델링 (Recommendation System Development)

### 1) 모델링 학습용 데이터셋 생성

- **약 1000개의 데이터셋 생성 및 구성**

### 2) MF-SVD 모델을 사용한 추천결과 출력 및 예측 데이터에 대한 교차 검증

- **모델링 추천 결과에 대한 와이어프레임 및 예측 결과의 유효성 검증**

### 3) 예측 데이터에 대한 교차검증

- **cross validation, GridSearchCV를 활용한 교차검증 코드 구현**

### 4) DeepFM 모델링 구현 및 비교

- **MF-SVD와 비교하여 DeepFM 모델링 진행중**

## 3. 테스트 및 결과 확인 및 논의 단계 (Test, Peer Review of the results)

- **랭체인을 활용한 사용자 입/출력에 대한 자연어 처리 진행**
- **리뷰 데이터셋의 n수를 3~5배수 늘려서 진행**
- **테스트 결과 시각화 및 동영상 레코딩**
- **리뷰데이터셋과 시설 데이터셋 수치 정량화 및 시각화**

## 4. 프로젝트 개선 방향에 대한 고찰 (Rhetorical Review)

- **설문조사 형태 및 선택항목의 맞춤형(targeting) 구체화 필요**
- **상세한 문진표 기재 정도에 따른 추천 결과 변화 고려**
- **프로그램별 이점 비교를 위한 샘플데이터 구성 제안**

## 5. 향후 프로젝트 디벨롭 아이디어 (Idea for Development)

- **운동성향 MBTI처럼 가능한 성향을 레벨화하여 적절한 운동 추천**
- **사용자 리뷰 데이터를 DB에 수집/저장/호출하는 방식으로 구현**
- **사설/공공 시설 통합 고려 및 사용성, 문제 자체의 어려움에 대한 고찰**
