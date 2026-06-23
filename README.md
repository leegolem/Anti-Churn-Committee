# Anti-Churn-Committee

웰니스 앱 리텐션 패턴 분석 공모전 프로젝트 저장소입니다.

## Team

이탈방지위원회  
English Name: Anti-Churn-Committee

## Project Overview

본 프로젝트는 헤이빗 웰니스 앱의 사용자 행동 로그와 가입자 프로필 데이터를 분석하여  
D30 리텐션 하락 원인을 파악하고, 다음 분기 리텐션 개선 전략을 제안하는 것을 목표로 합니다.

## Repository Structure

```text
Anti-Churn-Committee/
├─ data/
│  ├─ raw/          # 원본 데이터 저장 위치, GitHub 업로드 제외
│  └─ processed/    # 전처리 데이터 저장 위치, GitHub 업로드 제외
├─ notebooks/       # 분석 노트북
├─ src/             # 재사용 함수 코드
├─ outputs/         # 그래프, 표 등 산출물
├─ reports/         # 보고서, 발표자료
└─ docs/            # 아젠다, 의사결정 기록
```

## Data

원본 CSV 파일은 GitHub에 업로드하지 않습니다.

각자 아래 위치에 데이터를 넣고 실행합니다.

```text
data/raw/첨부파일 01_User_Profile.csv
data/raw/첨부파일 02_Event_Log.csv
```

## Environment Setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
```

## Main Analysis Topics

1. 데이터 기본 검수
2. 가입자 프로필 / 이벤트 로그 전처리
3. D30 리텐션 정의
4. 코호트 분석
5. 온보딩 및 챌린지 기능 분석
6. 알림 수신 / 알림 오픈 분석
7. 유저 세그먼트 분석
8. 리텐션 개선 전략 도출