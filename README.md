# Anti-Churn-Committee

웰니스 앱 리텐션 패턴 분석 공모전 프로젝트 저장소입니다.

## 팀

이탈방지위원회  
English Name: Anti-Churn-Committee


---
## 환경 구축 방법

### 1. 저장소 초대 받기
Git 관리자에게 **GitHub ID 또는 이메일**을 전달한 뒤, 저장소 초대를 수락한다.

### 2. 저장소 클론 및 환경 설정
```bash
# 저장소 클론
git clone https://github.com/leegolem/Anti-Churn-Committee.git
cd Anti-Churn-Committee

# 가상환경 생성 및 패키지 설치
uv sync

# 가상환경 활성화 방법은 사용하는 터미널에 따라 아래와 같다.
## Git Bash 사용 시
source .venv/Scripts/activate

## PowerShell 사용 시
.venv\Scripts\Activate.ps1

# 가상환경이 정상적으로 활성화되면 터미널 앞에
(Anti-Churn-Committee) 또는 (.venv) 와 같은 표시가 나타날 수 있다.
```
### 3. 연결 확인 방법
초대 수락 및 환경 설정이 끝난 뒤, 아래 순서로 정상 연결 여부를 확인한다.
```
1. git pull
2. 본인이 배정받은 member 폴더에서 테스트 파일 생성 또는 수정
3. git add "본인폴더명"
4. git commit -m "test: OOO 작업 환경 연결 확인"
5. git push
```
---

## 작업 시작 루틴
- 작업 시작 전 반드시 git pull을 실행한다.
- 원격 저장소(GitHub)의 최신 작업물을 먼저 로컬에 동기화한 뒤 작업한다.

---
## 라이브러리 추가 규칙 (`uv`)
새 라이브러리를 추가한 경우 아래 순서를 따른다.

### 추가한 사람
1. `uv add 패키지명` 실행
2. 변경된 `pyproject.toml`, `uv.lock` 파일을 함께 커밋
3. push까지 반영

### 다른 팀원
1. `git pull`
2. `uv sync`
---

## 작업물 받기 (조원이 해야 할 일)
기본적으로 아래 명령어를 먼저 실행한다.
```
git pull
- 아래 중 하나라도 해당하면 추가로 uv sync를 실행한다.
    - pyproject.toml이 변경된 경우
    - uv.lock이 변경된 경우
    - import error 또는 라이브러리 관련 에러가 발생한 경우
- 이 경우:
    - uv sync
```

---

## Git 작업 주의사항
1. git add . 사용 금지
    - 개인 작업물 커밋 시 git add . 사용을 금지한다.
    - 반드시 필요한 파일만 명시적으로 add한다.
    - 개인 작업물은 아래처럼 본인 폴더만 add한다.
```powershell
git add "본인폴더명"
```

2. 공용 파일 수정 시
    - 수정한 파일만 명시적으로 add한다.
    - 커밋 메시지에는 어떤 파일을 어떻게 수정했는지 드러나도록 작성한다.
    - 공용 파일 수정 전에는 팀원과 먼저 공유하거나 협의한다.

---

## 파일 및 데이터 관리 규칙
- 대용량 파일은 GitHub에 업로드하지 않는다.
- 원본 데이터는 integrated/data/에만 보관한다.
- 공용 반영이 필요한 내용만 협의 후 integrated/에 반영한다.
- 공용 저장소에는 코드, 문서, 설정 파일 위주로 관리한다.
- 대용량 데이터 및 산출물은 아래 구글 드라이브에서 관리한다.\

---

## 오류 발생시 대처헙

- `git pull` 전에 커밋해서 충돌이 발생한 경우
    1. `git pull --rebase origin main`으로 최신 내용을 먼저 반영한다.
    2. 충돌이 발생하면 충돌 내용을 수정한다.
    3.  `git add 수정한파일` -> `git rebase --continue` 순서로 진행한다.
    4. `git push --force`는 팀 협의 없이 사용하지 않는다.

- 라이브러리 관련 오류가 발생한 경우
    1. 먼저 `git pull`을 실행한다.
    2. 이후 `uv sync`를 실행한다.
    3. 그래도 해결되지 않으면 `pyproject.toml`, `uv.lock` 변경 여부를 확인한다.

--- 

## 프로젝트 파일 구성
```


## 

본 프로젝트는 헤이빗 웰니스 앱의 사용자 행동 로그와 가입자 프로필 데이터를 분석하여  
D30 리텐션 하락 원인을 파악하고, 다음 분기 리텐션 개선 전략을 제안하는 것을 목표로 합니다.

## 파일 구성

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


