# Chapter 4-2. 성능 최적화 Part 2 Basic

## 배포 주소
- https://d30xik1jnvalme.cloudfront.net/

## 성능 개선 보고서
### 측정 도구
- PageSpeed Insights

### 성능 전후 비교

| **항목**             | **성능 개선 전**                                                                                       | **성능 개선 후**                                                                                        |
|-----------------------|-------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------|
| **LCP**              | 14.63s                                                                                               | 2.86s                                                                                                 |
| **CLS**              | 0.011                                                                                                | 0.000                                                                                                |
| **분석 링크**        | [성능 개선 전 분석 결과 보기](https://pagespeed.web.dev/analysis/https-d30xik1jnvalme-cloudfront-net/n1t099zqfg?form_factor=desktop) | [성능 개선 후 분석 결과 보기](https://pagespeed.web.dev/analysis/https-d30xik1jnvalme-cloudfront-net/ax9xerh759?form_factor=desktop) |
| **이미지**           | <img width="800" alt="image" src="https://github.com/user-attachments/assets/e12b9984-14ad-48c6-9ce4-35238a4ace72"> | <img width="800" alt="image" src="https://github.com/user-attachments/assets/ae97ffcd-4e29-4d5f-b845-d15ba53cdfde"> |
| **주요 개선 사항**   | - 히어로 이미지 JPG 사용<br>- Lazy loading 미적용<br>- CSS 및 폰트 비최적화                          | - WebP 포맷 적용 및 이미지 압축<br>- Lazy loading 적용<br>- CSS 및 폰트 최적화(woff2 사용)            |
| **개선 효과**        | - 초기 로드 속도가 느림<br>- 주요 콘텐츠 표시 시간 지연<br>- 일부 레이아웃 이동 발생                  | - 초기 로드 속도 대폭 단축<br>- 주요 콘텐츠 빠르게 표시<br>- 레이아웃 이동 완전 제거                   |


### 개선 이유
1. LCP (Largest Contentful Paint) 개선 필요성

   - 이유: LCP는 사용자가 페이지를 로드할 때 가장 큰 콘텐츠(예: 히어로 이미지 또는 주요 텍스트)가 화면에 표시되기까지 걸리는 시간을 측정합니다.
   - 문제점: 성능 개선 전에는 LCP가 14.63초로, 사용자가 주요 콘텐츠를 보는데 상당한 대기 시간이 발생했습니다. 이는 사용자 이탈율 증가와 검색 엔진 최적화(SEO) 점수 하락으로 이어질 가능성이 높았습니다.
   CLS (Cumulative Layout Shift) 안정화 필요성

2. 이미지 최적화 부족
    - 이유: 히어로 이미지와 기타 주요 콘텐츠 이미지가 비효율적인 포맷(JPG)과 크기(최적화되지 않은 해상도)로 제공되어 로드 시간 증가의 주요 원인이 되었습니다.
    - 문제점: 이미지 크기가 크고 모든 이미지를 한 번에 로드하여 초기 렌더링 속도가 느림.
   폰트 및 CSS 비최적화

3. 폰트 및 CSS 비최적화
   - 이유: 외부 폰트를 로드할 때 네트워크 요청이 과도하게 발생하거나, 사용하지 않는 스타일이 포함되어 성능이 저하되었습니다.
   - 문제점: 초기 로드 시 폰트 파일 크기가 크고, 스타일 정리가 부족하여 불필요한 리소스가 로드되면서 속도와 안정성에 영향을 미침.
   Lazy Loading 미적용

4. Lazy Loading 미적용
    - 이유: 초기 화면에서 보이지 않는 이미지를 렌더링하지 않도록 Lazy Loading을 적용하지 않아 불필요한 리소스 로드가 발생.
    - 문제점: 사용자가 필요로 하지 않는 리소스까지 한 번에 로드하여 페이지 로딩 속도가 느림.
