# 1주차: 프로젝트 세팅 상세 계획

## 📅 주차 개요
- **기간**: 1주차 (7일)
- **목표**: 개발 환경 완전 구축 및 협업 체계 확립
- **핵심 성과물**: 모든 팀원이 동일한 환경에서 작업 가능한 기반 마련

## 👥 팀별 상세 작업 계획

### 🎮 개발자 A (게임플레이 담당)

#### **1-2일차: 언리얼 프로젝트 기초 설정**
```
언리얼 5.6 프로젝트 생성:
□ 새 프로젝트 생성 (Games > Top Down)
□ 프로젝트명: "SchoolSurvival" 
□ 위치: D:/Projects/SchoolSurvival/
□ 스타터 콘텐츠 포함 체크
□ 레이트레이싱 비활성화 (성능 고려)

초기 설정 조정:
□ 에디터 설정 > 일반 > 로딩 & 저장
  - 자동 저장 활성화 (5분 간격)
  - 백업 설정 (3개 파일 유지)
□ 프로젝트 설정 > 엔진 > 렌더링
  - 기본 RHI: DirectX 12
  - 모바일 HDR 비활성화
□ 월드 설정 조정
  - 킬 Z: -1000
  - 월드 바운드리 설정
```

#### **3-4일차: 게임플레이 프레임워크 구조 설계**
```
기본 클래스 구조 계획:
□ GameMode 설계
  - BP_SchoolSurvivalGameMode
  - 게임 상태 관리 (웨이브, 시간, 자원)
  - 승리/패배 조건 정의

□ PlayerController 설계  
  - BP_SurvivalPlayerController
  - 입력 처리 (마우스, 키보드)
  - 카메라 제어
  - UI 상호작용

□ GameState 설계
  - BP_SurvivalGameState
  - 전역 게임 정보 저장
  - 생존자 목록 관리
  - 자원 현황 관리

폴더 구조 정의:
/Content/
├── Blueprints/
│   ├── Core/           # GameMode, PlayerController 등
│   ├── Actors/         # Pawn, Actor 클래스들
│   ├── Components/     # 재사용 가능한 컴포넌트들
│   └── AI/            # AI 관련 블루프린트
├── UI/                # 모든 UI 위젯
├── Data/              # DataTable, 구조체
├── Maps/              # 레벨 맵들
├── Materials/         # 머티리얼
├── Meshes/            # 3D 모델
├── Textures/          # 텍스처
├── Audio/             # 사운드
└── Particles/         # 파티클 이펙트
```

#### **5-7일차: 기본 입력 시스템 설계**
```
Enhanced Input 시스템 설정:
□ 입력 액션 생성
  - IA_Move (WASD 카메라 이동)
  - IA_Zoom (마우스 휠 줌)
  - IA_Select (좌클릭 선택)
  - IA_Command (우클릭 명령)
  - IA_ModifySelection (Shift, Ctrl)

□ 입력 매핑 컨텍스트
  - IMC_Default (기본 조작)
  - IMC_BuildMode (건설 모드)
  - IMC_ActionMode (액션 모드)

워크래프트 스타일 명령 키 준비:
□ 명령 키 정의
  - A: 공격 명령
  - M: 이동 명령  
  - G: 자원 수집
  - B: 건설 모드
  - S: 정지
  - H: 제자리 대기
  - 1-9: 컨트롤 그룹

카메라 시스템 기초 설계:
□ 탑뷰 카메라 컴포넌트
□ 카메라 이동 제한 (월드 경계)
□ 부드러운 줌 인/아웃
□ 미니맵 클릭 이동 준비
```

### 🖼️ 개발자 B (UI/데이터 담당)

#### **1-2일차: UI 스타일 가이드 및 기본 설정**
```
UI 스타일 가이드 작성:
□ 색상 팔레트 정의
  - 주요 색상: #2C3E50 (어두운 청회색)
  - 강조 색상: #F39C12 (주황색)
  - 성공: #27AE60 (녹색)
  - 경고: #E74C3C (빨간색)
  - 배경: #34495E (회색)

□ 폰트 체계
  - 기본 폰트: Noto Sans CJK KR
  - 제목: Bold, 18-24pt
  - 본문: Regular, 12-16pt
  - 캡션: Regular, 10-12pt

□ UI 컴포넌트 가이드라인
  - 버튼 높이: 32px, 40px, 48px
  - 여백: 8px, 16px, 24px, 32px
  - 모서리 반지름: 4px, 8px
  - 그림자: 0 2px 4px rgba(0,0,0,0.2)
```

#### **3-4일차: 기본 데이터 구조체 설계**
```
핵심 구조체 정의:
□ S_SurvivorData
  - Name (String): 생존자 이름
  - Stats (S_Stats): 8개 능력치
  - Health (Float): 현재 체력
  - Fatigue (Float): 피로도
  - Status (Enum): 상태 (Idle, Working, Injured 등)
  - Traits (Array<E_Trait>): 특성 목록
  - Equipment (Array<S_ItemData>): 장비

□ S_Stats
  - Combat (Int): 전투 능력치
  - Shooting (Int): 사격 능력치  
  - Physical (Int): 체력 능력치
  - Agility (Int): 민첩 능력치
  - Working (Int): 작업 능력치
  - Technical (Int): 기술 능력치
  - Medical (Int): 의료 능력치
  - Mental (Int): 정신 능력치

□ S_ResourceData
  - Food (Int): 식량
  - Water (Int): 물
  - Fuel (Int): 연료
  - Scrap (Int): 스크랩
  - Wood (Int): 목재
  - Electronics (Int): 전자부품

□ S_BuildingData
  - BuildingType (Enum): 건물 종류
  - Name (String): 건물 이름
  - Description (String): 설명
  - Cost (S_ResourceData): 건설 비용
  - BuildTime (Float): 건설 시간 (분)
  - PowerConsumption (Int): 전력 소모
  - WorkerCapacity (Int): 작업자 수용 인원
```

#### **5-7일차: 기본 UI 위젯 프레임워크**
```
메인 HUD 구조 설계:
□ WBP_MainHUD (메인 HUD)
  ├── WBP_TopBar (상단 자원 표시)
  ├── WBP_BottomPanel (하단 제어 패널)  
  ├── WBP_LeftSidebar (생존자 목록)
  ├── WBP_RightSidebar (미니맵, 로그)
  └── WBP_NotificationSystem (알림)

□ WBP_TopBar 상세 설계
  - 자원 표시 (아이콘 + 수량/최대량)
  - 날짜/시간 표시
  - 웨이브 정보
  - 생존자 수

□ WBP_BottomPanel 상세 설계
  - 메인 메뉴 버튼들 (건설, 탐사 등)
  - 선택된 대상 정보 패널
  - 명령 버튼들

기본 UI 컴포넌트 제작:
□ Resource Display Component
  - 자원 아이콘 + 텍스트
  - 부족/풍족 상태 색상 변화
  - 클릭시 상세 정보 툴팁

□ Survivor Info Component  
  - 초상화 + 이름
  - 체력/피로도 바
  - 상태 아이콘
  - 능력치 요약 표시
```

### 🤖 개발자 C (AI/전투 담당)

#### **1-2일차: AI 시스템 아키텍처 설계**
```
AI 기본 구조 계획:
□ AI Controller 계층
  - BP_SurvivorAIController (생존자 AI)
  - BP_EnemyAIController (적 AI)
  - BP_NeutralAIController (중립 NPC)

□ Behavior Tree 구조 설계
  - BT_Survivor (생존자 행동 트리)
    ├── Emergency Response (긴급 상황 대응)
    ├── Player Commands (플레이어 명령 수행)
    ├── Idle Behavior (대기 중 행동)
    └── Auto Management (자동 관리)

□ Blackboard 키 정의
  - BB_Survivor
    - TargetLocation (Vector): 목표 위치
    - CurrentTask (Enum): 현재 작업
    - AssignedBuilding (Object): 배정된 건물
    - InventoryItems (Array): 소지품
    - EnemyTarget (Object): 적 대상
    - IsEmergency (Bool): 비상 상황 여부
```

#### **3-4일차: 네비게이션 및 기본 AI 설정**
```
NavMesh 시스템 설정:
□ NavMesh Bounds Volume 배치
  - 학교 건물 전체 영역 커버
  - 운동장 영역 포함
  - Agent 설정: 반지름 34, 높이 144

□ NavMesh 생성 설정
  - Cell Size: 19
  - Cell Height: 10  
  - Agent Max Slope: 45도
  - Agent Max Step Height: 35

□ NavLink Proxy 설정
  - 건물 입구/출구 연결
  - 층간 이동 (계단) 연결
  - 특수 지형 연결점

기본 AI 행동 구현:
□ 이동 시스템
  - AI Move To 노드 활용
  - 경로 탐색 실패시 대안 경로
  - 장애물 회피 행동

□ 기본 상태 관리
  - Idle: 대기 상태
  - Moving: 이동 중
  - Working: 작업 수행 중
  - Following: 추적 중
  - Fleeing: 도주 중
```

#### **5-7일차: 생존자 기본 AI 구현**
```
생존자 AI 기본 행동:
□ 플레이어 명령 처리
  - 이동 명령 수신 및 실행
  - 명령 대기열 관리
  - 명령 취소 처리

□ 자율 행동 시스템
  - 휴식 필요성 판단 (피로도 기반)
  - 안전 지역 탐색
  - 위험 회피 행동

□ 상호작용 시스템
  - 자원 오브젝트 인식
  - 수집 애니메이션 트리거
  - 인벤토리 아이템 추가

적 AI 기초 구현:
□ 기본 적 행동
  - 플레이어 생존자 추적
  - 기본 공격 패턴
  - 체력 시스템

□ 스폰 시스템 기초
  - 웨이브 시작시 스폰
  - 스폰 위치 관리
  - 적 타입별 차별화 준비
```

## 📊 전체팀 공통 작업

### **Git 저장소 설정 (1일차)**
```
저장소 초기 설정:
□ GitHub/GitLab 저장소 생성
  - 저장소명: school-survival-game
  - Private 저장소로 설정
  - README.md, .gitignore 생성

□ Git LFS 설정
  - .uasset, .umap 파일들
  - .fbx, .png, .wav 등 바이너리 파일
  - 100MB 이상 모든 파일

□ .gitignore 설정 (언리얼 전용)
  - Binaries/
  - Intermediate/  
  - DerivedDataCache/
  - Saved/
  - .vs/
  - *.tmp
  - *.sln
  - *.suo
```

### **협업 규칙 확정 (2일차)**
```
브랜치 전략:
□ main: 안정 버전 (배포용)
□ develop: 개발 통합 브랜치
□ feature/기능명: 개별 기능 개발
□ hotfix/버그명: 긴급 버그 수정

커밋 메시지 규칙:
□ [ADD] 새로운 기능 추가
□ [FIX] 버그 수정
□ [UPDATE] 기존 기능 개선
□ [REMOVE] 코드/파일 삭제
□ [DOCS] 문서 작업

Pull Request 규칙:
□ 최소 1명 리뷰 후 머지
□ 빌드 성공 확인 후 머지
□ 충돌 해결 후 머지
□ 기능 완성 단위로 PR 생성
```

### **Trello 보드 구성 (3일차)**
```
보드 구성:
□ 📋 Backlog: 전체 작업 목록
□ 📅 Sprint Planning: 주간 계획
□ 🏃 In Progress: 진행 중
□ 👀 Code Review: 리뷰 대기
□ 🧪 Testing: 테스트 중
□ ✅ Done: 완료

라벨 시스템:
□ 🔴 High Priority (긴급)
□ 🟡 Medium Priority (중요)  
□ 🟢 Low Priority (여유시)
□ 🔵 Bug (버그)
□ 🟣 Research (조사 필요)
□ ⚫ Blocked (대기 중)

카드 템플릿:
□ 제목: 간단명료한 작업 설명
□ 설명: 상세 요구사항
□ 체크리스트: 세부 작업 항목
□ 담당자 지정
□ 예상 소요 시간
□ 완료 기준 명시
```

### **Discord 채널 구성 (4일차)**
```
채널 구조:
□ #general: 일반 대화
□ #daily-standup: 일일 진행 공유
□ #dev-progress: 개발 진행도 공유
□ #bug-reports: 버그 신고
□ #code-review: 코드 리뷰 요청
□ #resources: 학습 자료 공유
□ #voice-coding: 페어 프로그래밍용

봇 설정:
□ GitHub 연동 봇 (푸시 알림)
□ Trello 연동 봇 (카드 업데이트)
□ 일일 리마인더 봇
```

## ✅ 1주차 완료 기준

### **기술적 완료 기준**
```
필수 완료 항목:
□ 모든 팀원이 동일한 UE5.6 프로젝트에서 작업 가능
□ Git 푸시/풀 정상 작동
□ 기본 레벨에서 카메라 이동 가능
□ 간단한 Actor 배치 및 이동 테스트 완료
□ 기본 UI 위젯 표시 가능

검증 방법:
□ 각자 간단한 기능 구현 후 푸시
□ 다른 팀원이 풀 받아서 정상 빌드 확인
□ 기본 조작 테스트 (WASD 카메라 이동)
□ UI 테스트 (버튼 클릭 반응)
```

### **협업 체계 완료 기준**
```
필수 완료 항목:
□ Trello 보드에 1주차 작업 완료 표시
□ Discord에서 일일 진행 공유 1회 이상
□ Git PR 생성 및 리뷰 1회 이상 경험
□ 팀 회의록 작성 및 공유

검증 방법:
□ 각자 완성한 작업을 Trello에서 Done으로 이동
□ PR 생성하여 팀원 리뷰 받기
□ 주간 회고 진행 (무엇을 배웠는지, 어려웠던 점)
```

## 🎯 1주차 마무리 회의

### **금요일 회의 안건**
```
진행 상황 점검:
□ 각자 완료한 작업 시연
□ 미완료 작업 및 이유 공유
□ 다음 주 계획 확인

기술적 이슈 해결:
□ Git 충돌 경험 공유
□ 언리얼 사용 중 어려웠던 점
□ 서로 도움이 필요한 부분

협업 개선점:
□ 의사소통 방식 개선안
□ 작업 분배 방식 조정
□ 도구 사용법 개선
```

### **주간 성과 정리**
```
목표 달성도:
□ 개발 환경 구축: ○○%
□ 협업 체계 구축: ○○%
□ 기술 학습: ○○%

다음 주 준비사항:
□ 부족한 부분 보완 학습
□ 다음 주 작업 분배
□ 필요한 에셋 및 리소스 준비
```