# 반응형 웹 UI 프로젝트

Vanilla JavaScript, Swiper, GSAP를 기반으로 제작한 반응형 랜딩 페이지입니다.<br>
PC 및 모바일에서 자연스럽고 부드러운 사용자 경험을 제공합니다.

## 주요 기능
- 창 너비 체크 및 메뉴 초기화
- 메뉴 버튼 클릭 시 메뉴 열고 닫기
- GNB 항목 클릭/마우스 이벤트 처리
- 슬라이드 이미지 경로 설정
- 디바이스 종류 확인 및 GSAP 타이포 효과 설정
- 요소에 스크롤 트리거 효과
## 사용 기술
|기술|설명|
|---|---|
|![HTML](https://img.shields.io/badge/-HTML-F05032?style=flat-square&logo=html5&logoColor=ffffff)|HTML5 마크업 구조|
|![CSS](https://img.shields.io/badge/-CSS-007ACC?style=flat-square&logo=css3)|CSS3 반응형 스타일 처리|
|![JavaScript](https://img.shields.io/badge/-JavaScript-dc8d2d?style=flat-square&logo=javascript&logoColor=ffffff)|JavaScript DOM 제어, Swiper & GSAP 연동|
|![Swiper](https://img.shields.io/badge/Swiper-6332F6?logo=swiper&logoColor=white&style=flat-square) |Swiper.js 슬라이더 구현|
|![GSAP](https://img.shields.io/badge/GSAP-88CE02?logo=greensock&logoColor=white&style=flat-square)|GSAP 고급 스크롤 애니메이션|
## 웹 이미지
|메인 슬라이더|모바일 메뉴|
|ㅇㅇ|ㅇㅇ|
## 주요기능 상세설명

### 1. checkWindowSize() – 창 너비 체크 및 메뉴 초기화

- desktopFlag: 현재 창이 데스크탑 크기인지 여부를 저장합니다.
- 창 너비가 1240px 이상이면 데스크탑 모드입니다.
- 메뉴와 네비게이션의 열림 상태를 초기화합니다.
``` React
let desktopFlag;

function checkWindowSize() {
	...
}
checkWindowSize();
export default App;
```
***

### 2. 메뉴 버튼 클릭 시 메뉴 열고 닫기

- 메뉴 탭 클릭 시 메뉴 열기/닫기가 실행됩니다.
- 기본 동작이 차단됩니다.
``` React
menuTab.addEventListener("click", function(e) {
	e.preventDefault();
	header.classList.toggle("menu-open");
});
export default App;
```

***

### 3. GNB 항목 클릭/마우스 이벤트 처리
``` React
Array.from(gnbList).forEach(function(item1, i) {
	...
});
export default App;
```
3-1. GNB 항목 클릭 (모바일일 때만 동작)
- 데스크탑이면 무시합니다.
- no-depth 클래스가 있으면 무시합니다.
- 하나만 열고 나머지 항목은 닫습니다.
``` React
item1.addEventListener("click", function(e) {
...
});
export default App;
```
3-2. 마우스 진입/이탈 (데스크탑만 동작)
- 마우스가 오버 시 header에 on 클래스 추가와 높이가 조정됩니다.
- 마우스가 나갈 때 원상복구됩니다.
``` React
item1.addEventListener("mouseenter", ...);
item1.addEventListener("mouseleave", ...);
export default App;
```
***

### 4. 슬라이드 이미지 경로 설정
- imageData에 PC/모바일 이미지 파일명을 배열합니다.
- 슬라이드별로 각각 PC/모바일 이미지 경로를 설정합니다.
``` React
const imageData = [ ... ];
let swiperSlides = document.querySelectorAll(".main-slider .swiper-slide");

swiperSlides.forEach(function(item, i) {
	...
});
export default App;
```
***

### 5. 디바이스 종류 확인 및 GSAP 타이포 효과 설정
- window.matchMedia로 디바이스 종류 구분합니다. (모바일/PC).
- 타이포그래피(.main-typo)에 GSAP 스크롤 트리거 효과를 적용합니다.
- 좌우로 글자가 움직이는 애니메이션입니다.
``` React
function checkDevice() {
	...
}
checkDevice();
export default App;
```
***

### 6. 요소에 스크롤 트리거 효과
- 요소가 보이면 .active 클래스가 추가됩니다.
- 다시 사라지면 .active 클래스가 제거됩니다.
``` React
gsap.utils.toArray(".scale-ani").forEach(function(item) {
	...
});
export default App;
```
***
