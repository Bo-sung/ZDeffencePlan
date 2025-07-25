# UI/UX 설계

## 🎮 게임 UI 전체 구성

### 메인 화면 레이아웃 (탑뷰 기준)
```
┌─────────────────────────────────────────────────────────────┐
│  [로고]    웨이브: 5/∞    날짜: 3일차    시간: 14:30      │  상단바
├─────────────────────────────────────────────────────────────┤
│ [음성] [일시정지] [설정]                    [자원 현황]     │  상단 UI
├─────────────────────────────────────────────────────────────┤
│                                                             │
│                   메인 게임 뷰                               │  중앙
│                  (탑뷰 폐교 거점)                           │  게임
│                                                             │  화면
│                                                             │
├─────────────────────────────────────────────────────────────┤
│ [인력관리] [건설] [탐사] [연구] [차원소환]    [미니맵]      │  하단 UI
└─────────────────────────────────────────────────────────────┘
```

## 📊 상단 UI 시스템

### 자원 현황 표시
```
┌─ 자원 현황 ──────────────────────────────────────┐
│ 🍞 45/50  💧 78/100  ⛽ 12/30  🔧 23/100  🏥 8  │
│ 식량      물        연료      스크랩     의약품   │
└──────────────────────────────────────────────────┘

표시 방식:
- 아이콘 + 현재량/최대량
- 부족시 빨간색 경고
- 풍족시 초록색 표시
- 클릭시 상세 정보 팝업
```

### 시간 및 상태 정보
```
┌─ 게임 상태 ──────────────────────────────────────┐
│ 📅 3일차  🕐 14:30  ⚡ 웨이브 5  👥 12명        │
│ 날짜     시간      다음공격    생존자수           │
└──────────────────────────────────────────────────┘

기능:
- 시간 가속 버튼 (1x, 2x, 4x)
- 일시정지 기능
- 다음 웨이브까지 카운트다운
```

## 🏗️ 건설 모드 UI

### 건설 메뉴
```
┌─ 건설 메뉴 ──────────────────────────────────────┐
│ [방어시설] [생산시설] [편의시설] [저장시설]       │
├──────────────────────────────────────────────────┤
│ 🛡️ 바리케이드     🔧 10  💰 5                   │
│ 🗼 감시탑         🔧 5   ⚡ 1   💰 2           │
│ 💣 함정           🔧 3   💥 2                   │
└──────────────────────────────────────────────────┘

표시 요소:
- 시설 아이콘 및 이름
- 필요 자원 (아이콘으로 표시)
- 건설 불가능시 회색 처리
- 건설 시간 표시
```

### 건설 진행 상황
```
┌─ 건설 중 ────────────────────────────────────────┐
│ 🗼 감시탑 건설중...  [██████████] 75%  2시간 남음 │
│ 담당자: 김기술 (작업 15)                         │
└──────────────────────────────────────────────────┘
```

## 👥 인력 관리 UI

### 생존자 목록
```
┌─ 생존자 관리 ────────────────────────────────────┐
│ [전체] [거점] [탐사중] [부상자] [휴식중]          │
├──────────────────────────────────────────────────┤
│ 👤 김민수  [리더]    💪15 🎯12 🏃14 🧠18        │
│    현재: 교장실 근무  상태: 건강  피로: 30%      │
│    특성: 지휘관, 협상가                          │
├──────────────────────────────────────────────────┤
│ 👤 박지영  [전투원]  💪18 🎯15 🏃16 🧠12        │
│    현재: 호위 근무    상태: 경상  피로: 60%      │
│    특성: 근접 전문가                             │
└──────────────────────────────────────────────────┘

아이콘 의미:
💪 체력  🎯 전투  🏃 민첩  🧠 정신
🔧 작업  ⚙️ 기술  🏥 의료  🎯 사격
```

### 배치 및 교대 관리
```
┌─ 구역별 배치 ────────────────────────────────────┐
│ 🏫 교장실    👤 김민수 (리더)                   │
│ 🍽️ 급식실    👤 이요리 + 👤 박보조             │
│ 🏥 보건실    👤 최의사                          │
│ 📚 도서관    👤 정연구                          │
│ 🏃 체육관    👤 소환담당 필요! [배치하기]       │
└──────────────────────────────────────────────────┘
```

## 🗺️ 탐사 시스템 UI

### 탐사 지역 선택 (이미 제작됨)
- 지역 맵과 상세 정보
- 탐사 목적 설정
- 팀 구성 및 장비 설정

### 탐사 진행 현황
```
┌─ 탐사 중 ────────────────────────────────────────┐
│ 📍 상인동 상점가 - 자원 탐색                     │
│ 👥 5명 파견  ⏱️ 6시간 중 2시간 경과             │
│ 📻 "상점가 진입 완료, 약탈자 흔적 발견"          │
│ [📞 연락] [🚨 긴급철수]                         │
└──────────────────────────────────────────────────┘
```

## ⚡ 차원 소환 UI

### 소환 인터페이스
```
┌─ 차원 소환 ──────────────────────────────────────┐
│ 💫 균열 상태: 안정    담당자: 김소환 (기술 16)   │
├──────────────────────────────────────────────────┤
│ 필요 자원: 🔧 3개  ⛽ 2개                       │
│ 보유 자원: 🔧 23개 ⛽ 12개  ✅ 소환 가능        │
├──────────────────────────────────────────────────┤
│          [🌟 소환 시작]                         │
│                                                  │
│ 소환 확률 정보:                                  │
│ 강력한 전문가: 5%                                │
│ 숙련된 전문가: 15%                               │
│ 일반 전문가: 35%                                 │
│ 초보자: 45%                                      │
└──────────────────────────────────────────────────┘
```

### 소환 결과 화면
```
┌─ 소환 성공! ─────────────────────────────────────┐
│                  ✨ 특수부대원 ✨                │
│                     👤 이전투                    │
│                                                  │
│ 💪 체력: 18   🎯 전투: 18   🏹 사격: 20         │
│ 🏃 민첩: 16   🔧 작업: 10   ⚙️ 기술: 12         │
│ 🏥 의료: 8    🧠 정신: 14                       │
│                                                  │
│ 🌟 특성: 야간 작전, 생존 본능                   │
│ 🎒 장비: 돌격소총, 전술 장비                    │
│                                                  │
│              [영입하기] [거절하기]                │
└──────────────────────────────────────────────────┘
```

## ⚔️ 전투 UI

### 웨이브 예고
```
┌─ 웨이브 경고! ───────────────────────────────────┐
│ 🚨 5번째 웨이브 접근 중! 🚨                     │
│ ⏰ 2시간 30분 후 도착 예정                       │
│ 📊 예상 적 규모: 중규모 (15-20마리)              │
│ 👹 주요 위협: 강화 감염자, 돌진형 몬스터         │
│                                                  │
│ [방어 준비] [긴급 건설] [인력 재배치]            │
└──────────────────────────────────────────────────┘
```

### 전투 진행 화면
```
┌─ 웨이브 5 진행 중 ───────────────────────────────┐
│ 📊 진행도: [████████░░] 80%                     │
│ 👹 남은 적: 3마리  💀 처치: 17마리               │
│ ❤️ 아군 상태: 부상 2명, 정상 10명               │
│ 🛡️ 거점 내구도: [████████░░] 85%               │
│                                                  │
│ 📻 "동쪽 바리케이드 파손! 수리 필요!"           │
└──────────────────────────────────────────────────┘
```

## 📱 미니맵 및 정보 패널

### 미니맵
```
┌─ 미니맵 ─────────────────┐
│ ┌─────────────────────┐  │
│ │  🏫    🗼    📡    │  │
│ │      운동장        │  │
│ │  🛡️   👥   🛡️    │  │
│ │                   │  │
│ │ 🚪 ←→ 🌊 몬스터    │  │
│ └─────────────────────┘  │
│ [+] [-] [📍 탐사팀]      │
└──────────────────────────┘

기능:
- 확대/축소
- 탐사팀 위치 표시
- 적 침입 방향 표시
- 중요 이벤트 마커
```

## 🔧 설정 및 메뉴

### 게임 설정
```
┌─ 설정 ───────────────────────────────────────────┐
│ 🔊 음향 설정                                     │
│   마스터 볼륨    [████████░░] 80%                │
│   효과음        [███████░░░] 70%                │
│   배경음악      [██████░░░░] 60%                │
│                                                  │
│ 🎮 게임 설정                                     │
│   자동 일시정지  ☑️ 탐사 완료시                  │
│   자동 저장      ☑️ 30분마다                     │
│   난이도        [보통] [어려움] [지옥]           │
└──────────────────────────────────────────────────┘
```

## 📋 알림 및 메시지 시스템

### 알림 큐
```
┌─ 최근 알림 ──────────────────────────────────────┐
│ 🔴 [긴급] 식량 부족! 2일분만 남음               │
│ 🟡 [주의] 박지영 부상 상태, 치료 필요           │
│ 🟢 [완료] 감시탑 건설 완료                      │
│ 🔵 [정보] 탐사팀 상인동 도착                    │
└──────────────────────────────────────────────────┘
```

## 🎯 UI/UX 설계 원칙

### 접근성
- **명확한 아이콘**: 직관적이고 이해하기 쉬운 아이콘 사용
- **색상 구분**: 색맹 고려한 색상 선택
- **글꼴 크기**: 가독성 좋은 크기와 폰트
- **키보드 단축키**: 마우스 없이도 조작 가능

### 정보 계층
- **중요도별 배치**: 핵심 정보는 눈에 잘 띄는 위치
- **그룹핑**: 관련 기능들을 함께 배치
- **일관성**: 같은 기능은 항상 같은 위치

### 피드백
- **즉시성**: 클릭, 호버 등에 즉각적 반응
- **상태 표시**: 로딩, 진행, 완료 상태 명확히 표시
- **에러 처리**: 오류 발생시 명확한 안내

### 효율성
- **원클릭 액세스**: 자주 사용하는 기능은 빠른 접근
- **드래그 앤 드롭**: 직관적인 배치 및 이동
- **배치 단축키**: 빠른 인력 및 자원 관리