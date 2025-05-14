# 반응형 웹 UI 프로젝트

Vanilla JavaScript, Swiper, GSAP를 기반으로 제작한 반응형 랜딩 페이지입니다.<br>
PC 및 모바일에서 자연스럽고 부드러운 사용자 경험을 제공합니다.

## 주요 기능

## 사용 기술

## 웹 이미지

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

a. GNB 항목 클릭 (모바일일 때만 동작)
- 데스크탑이면 무시합니다.
- no-depth 클래스가 있으면 무시합니다.
- 하나만 열고 나머지 닫습니다.
``` React
item1.addEventListener("click", function(e) {
	...
});
export default App;
```
