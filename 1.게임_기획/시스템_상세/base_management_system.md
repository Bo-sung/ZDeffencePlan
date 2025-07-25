# 거점 관리 시스템

## ⏰ 게임 시간 시스템

### 시간 흐름
```
기본 시간 비율: 게임 내 1일 = 실제 20분
- 게임 내 1시간 = 실제 50초
- 주간 (06:00-18:00) = 실제 10분
- 야간 (18:00-06:00) = 실제 10분

시간 가속:
- 1배속: 기본 속도
- 2배속: 게임 내 1일 = 실제 10분
- 4배속: 게임 내 1일 = 실제 5분

일시정지:
- 중요 결정시 자동 일시정지 옵션
- 수동 일시정지로 전략 수립 시간 확보
```

### 주간/야간 효과
```
주간 (06:00-18:00):
- 모든 작업 효율 100%
- 탐사 가능
- 건설 작업 가능
- 시야 확보 용이

야간 (18:00-06:00):
- 일반 작업 효율 80%
- 탐사 위험도 +20%
- 건설 작업 효율 70%
- 야간 특성 보유자만 효율 100%
- 몬스터 활동 증가
```

## 🏫 고정 구역 (폐교 기존 시설)

### 교실 구역
- **기능**: 생존자 거주 및 휴식 공간
- **수용 인원**: 구역당 2-3명
- **운영 시간**: 22:00-06:00 (수면), 14:00-18:00 (휴식)
- **업그레이드**: 침구류 개선 → 피로도 회복 +25%

### 급식실
- **기능**: 식량 생산 및 요리
- **필요 인력**: 요리사 1명 + 보조 1명
- **운영 시간**: 06:00-20:00 (3교대)
- **생산 스케줄**:
  - 06:00: 아침 식사 (2단위)
  - 12:00: 점심 식사 (5단위)
  - 18:00: 저녁 식사 (3단위)
- **업그레이드**: 조리 도구 → 일일 생산량 +2단위

### 보건실
- **기능**: 부상 치료 및 바이러스 연구
- **필요 인력**: 의료진 1명
- **운영 시간**: 24시간 (응급실)
- **치료 시간**:
  - 경상: 2-4시간
  - 중상: 8-12시간
  - 중태: 24-48시간
- **업그레이드**: 의료 장비 → 치료 성공률 +20%

### 도서관
- **기능**: 기술 연구 및 정보 수집
- **필요 인력**: 연구원 1명
- **운영 시간**: 08:00-20:00 (주간 위주)
- **연구 진행**: 8시간당 1포인트 (00:00 일일 체크)
- **업그레이드**: 연구 자료 → 연구 속도 +50%

### 교장실
- **기능**: 지휘부, 전략 계획 수립
- **필요 인력**: 리더(플레이어) 상주
- **운영 시간**: 06:00-22:00 (지휘 업무)
- **업그레이드**: 통신 장비 → 탐사팀 연락 효율 증대

### 체육관
- **기능**: 차원 소환 핵심 시설
- **필요 인력**: 소환 담당자 1명
- **운영 시간**: 제한 없음 (소환시에만 운영)
- **소환 시간**: 기본 30분 (기술 능력치에 따라 단축)
- **업그레이드**: 균열 안정화 장치 → 소환 성공률 +10%

## 👥 생존자 배치 및 교대 시스템

### 3교대 근무제
```
1교대 (06:00-14:00): 주요 생산 활동
- 건설, 연구, 생산 작업
- 탐사팀 파견 및 준비
- 높은 작업 효율

2교대 (14:00-22:00): 오후 운영
- 탐사팀 복귀 대응
- 저녁 식사 준비
- 시설 정비 및 관리

3교대 (22:00-06:00): 야간 경비
- 필수 시설 운영 (보건실, 경비)
- 긴급 상황 대응
- 제한적 작업만 수행
```

### 교대 관리
```
자동 교대 조건:
- 8시간 연속 근무 후
- 피로도 80% 도달시
- 부상자 자동 휴식 배치

교대 불가 상황:
- 전투 중일 때
- 중요 작업 진행 중
- 대체 인력 부족시
```

### 피로도 시스템
```
피로도 누적:
- 일반 작업: +5%/시간
- 고강도 작업: +10%/시간
- 전투: +20%/시간
- 야간 작업: +7%/시간 (야간 특성 없을 시)

피로도 회복:
- 일반 휴식: -15%/시간
- 휴게소 이용: -20%/시간
- 침실 휴식: -25%/시간

피로도 효과:
- 0-25%: 효율 100%
- 26-50%: 효율 90%
- 51-75%: 효율 75%
- 76-100%: 효율 50%, 부상 위험 증가
```

## 📊 구역별 효율성 계산

### 작업 효율 공식
**기본 효율 = (능력치 + 장비 보너스) × 피로도 보정 × 시간대 보정 × 시설 보정**

### 급식실 생산량
```
일일 기본 생산: 10단위
+ 요리사 작업 능력치 × 0.5단위
+ 보조 인력시 +50%
+ 조리 도구 업그레이드 +2단위
+ 야간 조리시 -20% (특성 없을 시)

최대 생산량: 약 18단위/일
```

### 보건실 치료율
```
기본 성공률: 60%
+ 의료진 의료 능력치 × 2%
+ 의료 장비 업그레이드 +20%
+ 야간 치료 -10%
+ 환자 상태: 경상 +20%, 중상 ±0%, 중태 -20%

최대 성공률: 95% (중태는 75%)
```

### 도서관 연구속도
```
기본 연구: 1포인트/8시간
+ 연구원 기술 능력치 × 0.2포인트
+ 연구 자료 +0.5포인트/8시간
+ 야간 연구 -20%
+ 추가 연구원 +30% per 인원

최대 연구속도: 약 3포인트/8시간
```

## ⚖️ 자원 소모 및 일일 주기

### 일일 자원 소모 (06:00 정산)
```
필수 소모:
- 식량: 생존자 수 × 1단위
- 물: 생존자 수 × 2단위

시설 운영비 (매시간):
- 발전기: 연료 0.125단위/시간 (3단위/일)
- 감시탑: 전력 0.042단위/시간 (1단위/일)
- 통신소: 전력 0.083단위/시간 (2단위/일)
```

### 일일 점검 시간
```
06:00: 자원 소모 정산 및 새로운 하루 시작
12:00: 중간 점검 (식량 생산, 건강 상태)
18:00: 저녁 점검 (탐사 결과, 시설 상태)
00:00: 연구 진행도 체크, 건설 진행 상황
```

## 🚨 비상 상황 관리

### 자원 부족 대응
```
식량 부족 (3일분 미만):
- 자동 배급 제한 모드
- 탐사 우선순위 조정
- 생존자 사기 저하 시작

인력 부족 (50% 이상 부상/피로):
- 필수 시설만 운영
- 자동 휴식 모드 전환
- 긴급 치료 우선순위

시설 고장:
- 자동 수리 대기열 생성
- 대체 시설 운영 모드
- 효율성 임시 저하
```

### 위기 경보 시스템
```
노란색 경고: 자원 7일분 미만
주황색 주의: 자원 3일분 미만  
빨간색 위험: 자원 1일분 미만
검은색 치명: 필수 자원 고갈
```

## 📈 거점 발전 단계

### 초기 정착 (1-5일)
- 기본 생존 확보
- 필수 시설 최소 운영
- 안정적 자원 공급망 구축

### 확장 단계 (6-15일)
- 시설 업그레이드 시작
- 전문 인력 확보
- 효율성 극대화

### 번영 단계 (16일+)
- 고급 시설 운영
- 잉여 자원 축적
- 주변 지역 영향력 확대