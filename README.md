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
- **Analytics**: Google Tag Manager (GTM) + Google Analytics 4 (GA4)
- **Hosting**: GitHub Pages

## 📊 트래킹 이벤트

### 구현된 dataLayer 이벤트
1. **select_content**: 탭 전환 (배우용/감독용)
2. **view_content**: 섹션 50% 이상 노출
3. **cta_primary**: 메인 CTA 버튼 클릭
4. **cta_feature**: 핵심 기능별 CTA 클릭
5. **generate_lead**: 사전 신청 폼 제출
6. **psf_vote_yes/no**: PSF 모달 투표

### GTM 설정 필요사항
```javascript
// GTM에서 수신할 dataLayer 이벤트 예시
{
  event: 'cta_feature',
  tab: 'actor' | 'director',
  feature: 'video_profile' | 'review_system' | 'fair_matching' | 
           'trust_score' | 'contract_auto' | 'video_search',
  role: 'actor' | 'director',
  utm_source: '...',
  utm_medium: '...',
  utm_campaign: '...'
}
```

## 🎯 측정 가능한 지표

- 탭별 사용자 선호도 (배우 vs 감독)
- 핵심 기능별 관심도 (클릭률)
- UTM 캠페인별 전환율
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

### 1. GTM 컨테이너 ID 설정
`index.html`에서 GTM 컨테이너 ID를 실제 값으로 교체:
```javascript
// 현재: GTM-S4302VXZLJ
// 실제 GTM ID로 교체 필요
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
- **Font Family**: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans KR'
- **Sizes**: Hero (5xl-7xl), Section (4xl-5xl), Body (xl-2xl)

## 🧪 QA 체크리스트

- [ ] 탭 전환 시 select_content 이벤트 푸시 확인
- [ ] 섹션 50% 이상 노출 시 view_content 이벤트 푸시 확인
- [ ] CTA 버튼 클릭 시 이벤트 푸시 확인
- [ ] 핵심 기능 CTA 클릭 시 cta_feature 이벤트 푸시 확인
- [ ] 폼 제출 성공 시 generate_lead 이벤트 푸시 확인
- [ ] PSF 모달 투표 시 이벤트 푸시 확인
- [ ] UTM 파라미터 파싱 및 모든 이벤트에 포함 확인
- [ ] GTM에서 dataLayer 이벤트 수신 및 GA4 전송 설정 확인
- [ ] 모바일 반응형 디자인 확인
- [ ] 접근성 (키보드 네비게이션, 스크린 리더) 확인

## 📞 문의

프로젝트 관련 문의사항이 있으시면 이슈를 생성해 주세요.

---

**Actor-Director** - 영상으로 증명하고, 신뢰로 연결하다 🎬✨
