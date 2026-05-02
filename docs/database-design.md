# Database Design

## Receipt

영수증 원본 및 OCR 결과를 저장한다.

| Field | Type | Description |
| --- | --- | --- |
| id | UUID | 영수증 ID |
| user_id | UUID | 사용자 ID |
| image_url | String | 영수증 이미지 URL |
| ocr_text | Text | OCR 원문 |
| purchased_at | Date | 구매일 |
| store_name | String | 판매처 |
| total_price | Number | 총 금액 |
| status | String | 처리 상태 |
| created_at | DateTime | 생성일 |
| updated_at | DateTime | 수정일 |

## Product

구매한 제품 정보를 저장한다.

| Field | Type | Description |
| --- | --- | --- |
| id | UUID | 제품 ID |
| user_id | UUID | 사용자 ID |
| receipt_id | UUID | 영수증 ID |
| name | String | 상품명 |
| brand | String | 브랜드 |
| model_name | String | 모델명 |
| category | String | 카테고리 |
| price | Number | 가격 |
| serial_number | String | 시리얼번호 |
| purchased_at | Date | 구매일 |
| store_name | String | 판매처 |
| created_at | DateTime | 생성일 |
| updated_at | DateTime | 수정일 |

## Warranty

제품 워런티 정보를 저장한다.

| Field | Type | Description |
| --- | --- | --- |
| id | UUID | 워런티 ID |
| product_id | UUID | 제품 ID |
| start_date | Date | 시작일 |
| end_date | Date | 종료일 |
| period_months | Number | 보증 기간 |
| source | String | 자동/수동 여부 |
| created_at | DateTime | 생성일 |
| updated_at | DateTime | 수정일 |

## Reminder

알림 정보를 저장한다.

| Field | Type | Description |
| --- | --- | --- |
| id | UUID | 리마인더 ID |
| user_id | UUID | 사용자 ID |
| product_id | UUID | 제품 ID |
| type | String | 알림 유형 |
| remind_at | DateTime | 알림 예정 시각 |
| status | String | 예정/발송/취소 |
| created_at | DateTime | 생성일 |
| updated_at | DateTime | 수정일 |

## Attachment

제품 관련 첨부 파일을 저장한다.

| Field | Type | Description |
| --- | --- | --- |
| id | UUID | 첨부 파일 ID |
| product_id | UUID | 제품 ID |
| type | String | 파일 유형 |
| file_url | String | 파일 URL |
| file_name | String | 파일명 |
| created_at | DateTime | 생성일 |
| updated_at | DateTime | 수정일 |

## 관계 구조

```text
User
 ├─ Receipt
 │   └─ Product
 │       ├─ Warranty
 │       ├─ Reminder
 │       └─ Attachment
```
