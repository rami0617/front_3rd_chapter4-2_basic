# Chapter 4-2. 성능 최적화 Part 2

## 배포 주소
- https://d30xik1jnvalme.cloudfront.net/

## 성능최적화 전
- PageSpeed Insights를 사용한 성능 측정
  - https://pagespeed.web.dev/analysis/https-d30xik1jnvalme-cloudfront-net/n1t099zqfg?form_factor=desktop

## 개선 이유

## 개선 방법
1. 히어로 이미지 jpg -> webp로 변경
2. 히어로 이미지를 뷰포트에 맞는 이미지만 보여주도록 변경
3. 히어로 이미지 압축 후 webp로 변경
4. 화면에 처음 보는 이미지를 제외하고는 모두 lazy loading 처리
5. 모든 이미지에 width, height 지정
6. 폰트를 로컬에서 다운받아 사용할 수 있도록 수정
7. 폰트를 woff2, woff 확장자로 변경
8. 히어로 외 다른 이미지 압축, webp로 변경, product 이미지 lazy loading 처리
9. 쿠키 스크립트가 페이지 로딩을 차단하지 않도록 defer 속성 추가
10. style.css 파일 minify
11. 9,10번이 제대로 적용이 안된걸 알고 수정
12. 안쓰는 스타일 정리

## 개선 후 향상된 지표
1. LCP 14.63s -> 9.76s
2. CLS 0.011 -> 0.000
3. LCP 9.76s -> 4.88s
4. LCP 4.88s -> 4.80s
5. LCP 4.80s -> 4.88s
6. LPC 4.88s -> 4.58s
7. LCP 4.58s -> 4.58s
8. LCP 4.58s -> 3.83s
9. LCP 3.83s -> 2.86s
10. LCP 2.86s -> 2.85s
11. LCP 2.85s -> 4.28s
12. LCP 4.28s -> 3.16s