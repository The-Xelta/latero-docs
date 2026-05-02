# Information Architecture

## 주요 화면 구조

### Home

- 최근 등록한 구매 기록
- 다가오는 리마인더
- 영수증 업로드 버튼

### Receipt Upload

- 영수증 이미지 업로드
- OCR 처리 상태
- 추출 결과 확인

### Purchase Detail

- 상품명
- 구매일
- 가격
- 판매처
- 워런티 정보
- 반품 정보
- 첨부 파일
- 시리얼번호

### Reminder

- 예정된 알림 목록
- 만료 임박 항목
- 완료된 알림

### Product Library

- 저장된 제품 목록
- 카테고리 필터
- 검색

### Settings

- 알림 설정
- 기본 워런티 기간 설정
- 계정 설정

## 사용자 흐름 구조

```text
Home
 ├─ Receipt Upload
 │   └─ OCR Result
 │       └─ Purchase Detail
 ├─ Product Library
 │   └─ Purchase Detail
 ├─ Reminder
 │   └─ Purchase Detail
 └─ Settings
```

## 주요 탐색 기준

- 구매 기록 중심
- 제품 중심
- 리마인더 중심
