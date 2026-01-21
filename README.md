# 오뚜기 웹사이트 - Vanilla CSS/HTML/JavaScript

Figma 디자인에서 생성한 순수 Vanilla CSS와 HTML5, JavaScript로 구현된 반응형 웹사이트입니다.

## 📋 프로젝트 특징

### 기술 스택
- **HTML5**: 시맨틱 마크업
- **CSS3**: 순수 Vanilla CSS (외부 라이브러리 없음)
- **JavaScript**: Vanilla JavaScript (프레임워크 없음)

### 디자인 특징
- **Figma 레이어명 사용**: 모든 HTML 클래스명이 Figma 레이어명과 일치하여 디자인-코드 일관성 유지
- **Flexbox 기반 레이아웃**: 유연하고 반응형인 화면 구성
- **접근성 고려**: ARIA 라벨 및 시맨틱 HTML 사용

### 반응형 디자인
- **Desktop** (1200px 이상): 완전한 레이아웃
- **Tablet** (768px ~ 1200px): 최적화된 중간 사이즈
- **Mobile** (768px 미만): 터치 친화적 인터페이스
- **Small Mobile** (480px 미만): 소형 기기 최적화

## 📁 파일 구조

```
figma/02/
├── index.html      # HTML 구조 (Figma 레이어명 클래스 사용)
├── style.css       # 전체 스타일시트 (Flexbox 중심)
├── script.js       # JavaScript 기능 구현
└── README.md       # 이 파일
```

## 🎨 CSS 클래스 네이밍

Figma 디자인 레이어명을 그대로 사용하여 일관성 유지:

```css
/* Header 컴포넌트 */
.Header              /* 헤더 컨테이너 */
.Header-content      /* 헤더 콘텐츠 */
.Logo                /* 로고 */
.Nav-bar             /* 네비게이션 바 */
.Nav-item            /* 네비게이션 아이템 */
.Hamburger-menu      /* 모바일 메뉴 */
.Utility-area        /* 유틸리티 버튼 영역 */
.Language            /* 언어 선택 */

/* 비디오 섹션 */
.Video-section       /* 비디오 전체 섹션 */
.Video-container     /* 비디오 컨테이너 */
.Video-playback      /* 재생 컨트롤 */
.Video-btn           /* 컨트롤 버튼 */
.Slide-indicator     /* 슬라이드 인디케이터 */
.Progress-bar        /* 프로그레스 바 */
```

## 🎬 주요 기능

### 1. 비디오 슬라이더 (VideoSlider 클래스)
```javascript
const videoSlider = new VideoSlider();
```
- 자동 슬라이드 변경 (7초 간격)
- 이전/다음 버튼 제어
- 일시정지/재생 토글
- 슬라이드 번호 표시
- 프로그레스 바 표시

### 2. 모바일 메뉴 (MobileMenu 클래스)
```javascript
const mobileMenu = new MobileMenu();
```
- 반응형 햄버거 메뉴
- 모바일에서 자동으로 메뉴 숨김/표시
- 메뉴 아이템 클릭 시 메뉴 닫기

### 3. 반응형 처리 (ResponsiveHandler 클래스)
```javascript
const responsiveHandler = new ResponsiveHandler();
```
- 브레이크포인트 감지
- 화면 크기 변경 시 자동 적응

### 4. 부드러운 스크롤 (SmoothScrollHandler 클래스)
```javascript
const smoothScroll = new SmoothScrollHandler();
```
- 내부 링크 클릭 시 부드러운 스크롤

## 🎯 Flexbox 레이아웃 구조

### Header Layout
```css
.Header-content {
    display: flex;
    align-items: center;
    justify-content: space-between;  /* Logo | Nav | Utility | Language */
}
```

### Navigation Bar
```css
.Nav-bar {
    flex: 1;
    display: flex;
    gap: 50px;  /* 데스크톱 */
    /* 반응형으로 gap 감소 */
}
```

### Video Controls
```css
.Video-playback {
    display: flex;
    gap: 30px;  /* 컨트롤 버튼들의 간격 */
    flex-wrap: wrap;  /* 모바일에서 줄바꿈 */
}
```

## 📱 반응형 중단점 (Breakpoints)

```javascript
{
    tablet: 768,    /* 768px 이상 1200px 미만 */
    desktop: 1200   /* 1200px 이상 */
}
```

각 중단점별로 다음과 같이 최적화됨:
- **Desktop**: 완전한 네비게이션 표시
- **Tablet**: 감소된 gap, 최적화된 크기
- **Mobile**: 햄버거 메뉴, 숨김 처리

## 🚀 사용 방법

### 1. 기본 셋업
```html
<link rel="stylesheet" href="style.css">
<script src="script.js"></script>
```

### 2. 자동 초기화
```javascript
// DOMContentLoaded 시 자동으로 모든 기능 초기화
document.addEventListener('DOMContentLoaded', () => {
    // VideoSlider, MobileMenu, ResponsiveHandler 등 자동 실행
});
```

### 3. 외부에서 기능 접근
```javascript
// 전역 객체로 접근 가능
window.app.videoSlider.nextSlide();
window.app.mobileMenu.toggleMenu();
```

## 🎨 색상 및 디자인 토큰

Figma에서 추출한 색상:
- 배경: `#fff`
- 텍스트: `#333`
- 헤더 배경: `rgba(0, 0, 0, 0.5)`
- 헤더 텍스트: `#fff`
- 오뚜기몰 버튼: `#fffc29`
- 그라디언트: `rgba(0, 0, 0, 0.5)`

## 📐 Typography

폰트 패밀리: `'Pretendard Variable', 'Pretendard', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif`

## ⚡ 성능 최적화

1. **Throttling**: 스크롤 이벤트에 throttle 적용
2. **자동 재생**: 비디오 자동 재생 (7초 간격)
3. **지연 로딩**: 이미지는 lazy loading 권장

## 🔧 개발자 가이드

### 새로운 컴포넌트 추가

1. HTML에 Figma 레이어명으로 클래스 추가
```html
<div class="NewComponent">
    <h3 class="NewComponent-title">제목</h3>
</div>
```

2. CSS에 스타일 추가
```css
.NewComponent {
    display: flex;
    gap: 20px;
}

.NewComponent-title {
    font-size: 24px;
}
```

3. JavaScript에 기능 추가 (필요시)
```javascript
class NewComponentHandler {
    constructor() {
        this.element = document.querySelector('.NewComponent');
        this.init();
    }

    init() {
        // 초기화 로직
    }
}
```

### 반응형 스타일 추가

```css
/* 태블릿 (768px 이상 1200px 미만) */
@media (max-width: 1200px) {
    .Component {
        gap: 15px;  /* 데스크톱 30px -> 15px */
    }
}

/* 모바일 (768px 미만) */
@media (max-width: 768px) {
    .Component {
        flex-direction: column;
    }
}
```

## 🐛 트러블슈팅

### 비디오가 재생되지 않음
- 브라우저가 자동 재생 정책을 지원하는지 확인
- `muted` 속성이 있는지 확인
- 비디오 파일 형식 확인 (MP4 권장)

### 반응형 메뉴가 작동하지 않음
- JavaScript가 로드되었는지 확인
- 콘솔에서 에러 확인
- `Hamburger-menu` 클래스가 있는지 확인

### 이미지가 표시되지 않음
- 이미지 URL이 유효한지 확인
- Figma API 에셋 URL이 만료되지 않았는지 확인 (7일 유효)

## 📝 라이선스

이 프로젝트는 개인/상업용 목적으로 자유롭게 사용할 수 있습니다.

## 🤝 기여하기

개선사항이 있으면 자유롭게 수정하세요.

---

**생성일**: 2024년
**기술**: HTML5, CSS3, Vanilla JavaScript
**브라우저 지원**: Chrome, Firefox, Safari, Edge (최신 버전)
