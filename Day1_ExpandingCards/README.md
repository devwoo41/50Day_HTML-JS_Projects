# Day1 - Expanding Cards

## 프로젝트 구조

- index.html: 카드 UI의 구조(HTML) 정의
- style.css: 카드의 레이아웃, 애니메이션 등 시각적 스타일 담당
- script.js: 카드 클릭 시 확장/축소되는 동작 등 인터랙션 구현

## 주요 구현 포인트
1. 카드 레이아웃(HTML): 여러 개의 카드를 container 내부에 배치, 각 카드는 이미지와 텍스트로 구성
2. 스타일링 및 애니메이션(CSS): Flexbox로 가로 정렬, .active 클래스로 확장/축소 스타일 지정, transition으로 부드러운 애니메이션
3. 동작 로직(JavaScript): 카드 클릭 시 해당 카드에만 .active 클래스 적용, 나머지는 해제

## 핵심 코드 예시
```html
<div class="container">
  <div class="card active">
    <h3>Card Title</h3>
  </div>
  <!-- ...다른 카드들... -->
</div>
```
```css
.card {
  flex: 1;
  transition: flex 0.5s;
}
.card.active {
  flex: 5;
}
```
```js
const cards = document.querySelectorAll('.card');
cards.forEach(card => {
  card.addEventListener('click', () => {
    cards.forEach(c => c.classList.remove('active'));
    card.classList.add('active');
  });
});
```

## 요약
- HTML, CSS, JS의 분리와 각 역할이 명확하게 드러나는 구조입니다.
- CSS의 Flexbox와 트랜지션, JS의 클래스 토글이 핵심입니다.
