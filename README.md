# Actor-Director 랜딩페이지 🎬

영상 중심 캐스팅 플랫폼 Actor-Director의 공식 랜딩페이지입니다.

## 📖 프로젝트 개요

**Actor-Director**는 배우와 감독을 연결하는 혁신적인 캐스팅 플랫폼입니다.
- 배우: 영상 프로필로 실력을 증명하고 공정한 기회를 얻습니다
- 감독: 검증된 배우와 안전하게 협업할 수 있습니다

## 🚀 주요 기능

### 배우용 기능
- **영상 중심 프로필**: 짧은 연기 영상으로 실력 증명
- **상호리뷰 평판 시스템**: 협업 기반 신뢰도 평가
- **공정한 매칭**: 인맥이 아닌 실력 중심 캐스팅

### 감독·제작자용 기능
- **신뢰 온도 시스템**: 노쇼 방지를 위한 신뢰도 점수
- **표준 근로계약서 자동화**: 법률 검토 완료된 계약 템플릿
- **영상 포트폴리오 검색**: 조건별 배우 검색 및 영상 확인

## 🛠 기술 스택

- **Frontend**: HTML5, CSS3, JavaScript (Vanilla)
- **Styling**: Tailwind CSS
- **Analytics**: Google Analytics 4 (GA4) with gtag
- **Hosting**: GitHub Pages

## 📊 트래킹 이벤트

### 구현된 GA4 이벤트

#### 1. 개별 CTA 이벤트 (고유 이벤트 이름)
각 CTA는 고유한 이벤트 이름을 가지며, GA4에서 개별 분석이 가능합니다:

**네비게이션 이벤트:**
- **`tab_switch`**: 탭 전환 (배우용/감독용)

**CTA 클릭 이벤트:**
- **`primary_cta_click`**: 메인 CTA 버튼 클릭 (✨ 배우로 시작하기, 감독으로 시작하기)
- **`explore_features_click`**: 기능 살펴보기 CTA 클릭

**개별 기능 CTA 이벤트 (각각 고유 이벤트):**
- **`video_profile_click`**: 영상 프로필 CTA 클릭
- **`review_system_click`**: 상호리뷰 평판 시스템 CTA 클릭
- **`fair_matching_click`**: 공정한 매칭 CTA 클릭
- **`trust_score_click`**: 신뢰 온도 시스템 CTA 클릭
- **`contract_auto_click`**: 표준 근로계약서 자동화 CTA 클릭
- **`video_search_click`**: 영상 포트폴리오 검색 CTA 클릭

**전환 이벤트:**
- **`form_submit`**: 사전 신청 폼 제출
- **`interview_cta_click`**: 인터뷰 참여 CTA 클릭

**피드백 이벤트:**
- **`psf_vote`**: PSF 모달 투표

**UI 상호작용 이벤트:**
- **`modal_close`**: 모달 닫기 버튼 클릭
- **`section_view`**: 섹션 50% 이상 노출

#### 2. 리드 생성 이벤트 (`generate_lead`)
Enhanced Ecommerce 구조로 리드 생성을 추적합니다.

#### 3. 사용자 참여도 이벤트
- **scroll**: 스크롤 깊이 추적 (25%, 50%, 75%)
- **user_engagement**: 시간 기반 참여도 (30초, 1분, 3분)

#### 4. 사용자 생명주기 이벤트
- **first_visit**: 첫 방문자 추적
- **return_visit**: 재방문자 추적
- **session_start**: 세션 시작 추적

#### 5. 페이지 성능 이벤트
- **page_timing**: 페이지 로딩 시간 추적

### GA4 이벤트 구조

**개별 기능 CTA 이벤트 (고유 이벤트 이름):**
```javascript
// 영상 프로필 CTA 클릭 시
gtag('event', 'video_profile_click', {
  event_category: 'feature_cta',
  event_label: 'video_profile',
  tab: 'actor',
  feature: 'video_profile',
  feature_name: '영상 프로필',
  utm_source: '...',
  utm_medium: '...',
  utm_campaign: '...'
});
```

**메인 CTA 이벤트:**
```javascript
// 메인 CTA 버튼 클릭 시
gtag('event', 'primary_cta_click', {
  event_category: 'cta',
  event_label: 'actor_start',
  tab: 'actor',
  role: 'actor',
  utm_source: '...',
  utm_medium: '...',
  utm_campaign: '...'
});
```

**탭 전환 이벤트:**
```javascript
// 탭 전환 시
gtag('event', 'tab_switch', {
  event_category: 'navigation',
  event_label: 'actor',
  tab: 'actor',
  utm_source: '...',
  utm_medium: '...',
  utm_campaign: '...'
});
```

## 🎯 측정 가능한 지표

### 사용자 행동 분석
- **탭별 사용자 선호도**: `tab_switch` 이벤트로 배우 vs 감독 탭 사용률 분석
- **개별 기능별 관심도**: 6개 고유 이벤트로 핵심 기능 클릭률 개별 비교
  - `video_profile_click`, `review_system_click`, `fair_matching_click`
  - `trust_score_click`, `contract_auto_click`, `video_search_click`
- **CTA 성과 분석**: `primary_cta_click`, `explore_features_click` 개별 측정
- **사용자 여정 분석**: `section_view` 이벤트로 섹션별 체류 시간 및 이탈률
- **UTM 캠페인 효과**: 모든 이벤트에 UTM 파라미터 포함으로 소스별 전환율 분석

### 웹 트래픽 및 리텐션 KPI
- **사용자 참여도**: 스크롤 깊이, 체류 시간, 상호작용 횟수
- **리텐션 분석**: 신규 vs 재방문자 비율, 세션 지속 시간
- **페이지 성능**: 로딩 시간, Core Web Vitals
- **전환율 최적화**: 리드 생성률, 폼 완료율
- **사용자 세그멘테이션**: 참여도별 사용자 분류 (low/high engagement)

### 기능별 상세 분석

**배우용 기능:**
- 영상 프로필 (`video_profile`)
- 상호리뷰 평판 시스템 (`review_system`)
- 공정한 매칭 (`fair_matching`)

**감독용 기능:**
- 신뢰 온도 시스템 (`trust_score`)
- 표준 근로계약서 자동화 (`contract_auto`)
- 영상 포트폴리오 검색 (`video_search`)

### 비즈니스 인사이트
- 어떤 기능이 리드 전환에 가장 효과적인지
- 사용자 세그먼트별 기능 선호도
- 기능 개발 우선순위 결정 데이터
- 리드 생성 퍼널 분석
- PSF(Problem-Solution Fit) 검증

## 📁 파일 구조

```
Actor-Director/
├── index.html          # 메인 랜딩페이지
├── styles.css          # 스타일시트
├── README.md           # 프로젝트 문서
└── assets/             # 이미지 및 리소스 (향후 추가)
```

## 🚀 배포 및 실행

### 로컬 개발 서버 실행
```bash
# Python 3 사용
python -m http.server 8000

# 또는 Node.js 사용
npx serve .
```

브라우저에서 `http://localhost:8000` 접속

### GitHub Pages 배포
1. GitHub 저장소에 코드 푸시
2. Settings > Pages에서 소스를 `main` 브랜치로 설정
3. 자동으로 `https://username.github.io/repository-name/`에 배포

## 🔧 설정 방법

### 1. GA4 측정 ID 설정
`index.html`에서 GA4 측정 ID가 이미 설정되어 있습니다:
```javascript
// 현재 설정: G-S43Q2VXZLJ
// 필요시 실제 GA4 측정 ID로 교체
```

### 2. UTM 파라미터 테스트
URL에 UTM 파라미터를 추가하여 트래킹 테스트:
```
https://your-domain.com/?utm_source=test&utm_medium=social&utm_campaign=launch
```

## 📈 성능 최적화

- **Tailwind CSS CDN**: 빠른 프로토타이핑
- **Vanilla JavaScript**: 프레임워크 의존성 없음
- **Lazy Loading**: 이미지 지연 로딩 (향후 구현)
- **Code Splitting**: CSS/JS 파일 분리

## 🎨 디자인 시스템

### 컬러 팔레트
- **Cinema Dark**: `#0a0a0a`, `#1a1a1a`, `#2a2a2a`, `#3a3a3a`
- **Gradient**: Purple to Indigo (`#667eea` → `#764ba2`)
- **Accent**: Purple (`#9333ea`)

### 타이포그래피
- **Font Family**: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans KR'
- **Sizes**: Hero (5xl-7xl), Section (4xl-5xl), Body (xl-2xl)

## 🎨 새로운 UI/UX 기능

### 로딩 및 인터랙션
- **로딩 스크린**: 브랜드 일관성 있는 스피너 애니메이션
- **스크롤 프로그레스**: 상단 그라디언트 진행 바
- **부드러운 스크롤**: scroll-behavior: smooth 적용
- **마이크로 애니메이션**: 버튼 hover/active 상태 개선

### 포트폴리오 배경
- **Netflix 스타일**: 6x4 그리드 배우 포트폴리오 썸네일
- **동적 애니메이션**: 플로팅 효과 및 featured 카드 강조
- **반응형 그리드**: 모바일(3x6), 태블릿(4x5), 데스크톱(6x4)

### 기능 준비 중 모달
- **개별 기능 추적**: 6개 핵심 기능별 개별 CTA 트래킹
- **사용자 피드백**: '기능이 준비 중입니다!' 모달
- **동적 콘텐츠**: 클릭한 기능명 자동 표시

## 🧪 QA 체크리스트

### GA4 개별 이벤트 트래킹
- [ ] 탭 전환 시 `tab_switch` 이벤트 발생 확인
- [ ] 섹션 50% 이상 노출 시 `section_view` 이벤트 발생 확인
- [ ] 메인 CTA 버튼 클릭 시 `primary_cta_click` 이벤트 발생 확인
- [ ] 기능 살펴보기 CTA 클릭 시 `explore_features_click` 이벤트 발생 확인
- [ ] 인터뷰 참여 CTA 클릭 시 `interview_cta_click` 이벤트 발생 확인
- [ ] 모달 닫기 버튼 클릭 시 `modal_close` 이벤트 발생 확인
- [ ] 폼 제출 성공 시 `form_submit` 이벤트 발생 확인
- [ ] PSF 모달 투표 시 `psf_vote` 이벤트 발생 확인
- [ ] 리드 생성 시 `generate_lead` 이벤트 발생 확인 (Enhanced Ecommerce 구조)

### 개별 기능 CTA 이벤트 트래킹
**배우용 기능:**
- [ ] 영상 프로필 CTA 클릭 시 `video_profile_click` 이벤트 발생 확인
- [ ] 상호리뷰 평판 시스템 CTA 클릭 시 `review_system_click` 이벤트 발생 확인
- [ ] 공정한 매칭 CTA 클릭 시 `fair_matching_click` 이벤트 발생 확인

**감독용 기능:**
- [ ] 신뢰 온도 시스템 CTA 클릭 시 `trust_score_click` 이벤트 발생 확인
- [ ] 표준 근로계약서 자동화 CTA 클릭 시 `contract_auto_click` 이벤트 발생 확인
- [ ] 영상 포트폴리오 검색 CTA 클릭 시 `video_search_click` 이벤트 발생 확인

### 사용자 참여도 및 리텐션 트래킹
- [ ] 스크롤 25%, 50%, 75% 지점에서 scroll 이벤트 발생 확인
- [ ] 30초, 1분, 3분 체류 시 user_engagement 이벤트 발생 확인
- [ ] 5회 이상 클릭 시 user_engagement (active_user) 이벤트 발생 확인
- [ ] 첫 방문 시 first_visit 이벤트 발생 확인
- [ ] 재방문 시 return_visit 이벤트 발생 확인
- [ ] 세션 시작 시 session_start 이벤트 발생 확인
- [ ] 페이지 로딩 완료 시 page_timing 이벤트 발생 확인

### 사용자 속성 검증
- [ ] user_type: 'new' 또는 'returning' 설정 확인
- [ ] preferred_tab: 사용자가 선택한 탭 기록 확인
- [ ] engagement_level: 'low' 또는 'high' 설정 확인 (3분 이상 체류 시)

### 기능별 모달 및 이벤트 테스트
**배우용 기능:**
- [ ] 영상 프로필 CTA → `video_profile_click` 이벤트 + 모달 표시 확인
- [ ] 상호리뷰 평판 시스템 CTA → `review_system_click` 이벤트 + 모달 표시 확인
- [ ] 공정한 매칭 CTA → `fair_matching_click` 이벤트 + 모달 표시 확인

**감독용 기능:**
- [ ] 신뢰 온도 시스템 CTA → `trust_score_click` 이벤트 + 모달 표시 확인
- [ ] 표준 근로계약서 자동화 CTA → `contract_auto_click` 이벤트 + 모달 표시 확인
- [ ] 영상 포트폴리오 검색 CTA → `video_search_click` 이벤트 + 모달 표시 확인

### 기술적 검증
- [ ] UTM 파라미터 파싱 및 모든 이벤트에 포함 확인
- [ ] GA4에서 모든 개별 이벤트 수신 확인 (17개 고유 이벤트)
- [ ] 개발자 도구에서 gtag 이벤트 전송 확인
- [ ] GA4 실시간 보고서에서 이벤트별 개별 집계 확인
- [ ] '기능이 준비 중입니다!' 모달 정상 작동 확인

### UI/UX 검증
- [ ] 로딩 스크린 정상 작동 확인
- [ ] 스크롤 프로그레스 바 정상 작동 확인
- [ ] 모바일 반응형 디자인 확인
- [ ] 접근성 (키보드 네비게이션, 스크린 리더) 확인
- [ ] 포트폴리오 배경 그리드 정상 표시 확인

## 📞 문의

프로젝트 관련 문의사항이 있으시면 이슈를 생성해 주세요.

---

**Actor-Director** - 영상으로 증명하고, 신뢰로 연결하다 🎬✨
