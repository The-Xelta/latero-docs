# API Specification

## OCR 업로드 API

### POST /api/ocr/receipts

영수증 이미지를 업로드하고 OCR 처리를 요청한다.

### Request

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| image | File | Yes | 영수증 이미지 |

### Response

```json
{
  "receipt_id": "uuid",
  "status": "processing"
}
```

## OCR 결과 조회 API

### GET /api/ocr/receipts/{receipt_id}

OCR 처리 결과를 조회한다.

### Response

```json
{
  "receipt_id": "uuid",
  "status": "completed",
  "store_name": "Apple Store",
  "purchased_at": "2026-05-02",
  "total_price": 1290000,
  "items": [
    {
      "name": "AirPods Pro",
      "price": 359000
    }
  ]
}
```

## 제품 조회 API

### GET /api/products

사용자의 제품 목록을 조회한다.

### Response

```json
{
  "products": [
    {
      "id": "uuid",
      "name": "AirPods Pro",
      "brand": "Apple",
      "purchased_at": "2026-05-02",
      "warranty_end_date": "2027-05-02"
    }
  ]
}
```

## 제품 상세 조회 API

### GET /api/products/{product_id}

제품 상세 정보를 조회한다.

### Response

```json
{
  "id": "uuid",
  "name": "AirPods Pro",
  "brand": "Apple",
  "serial_number": "ABC123",
  "purchased_at": "2026-05-02",
  "store_name": "Apple Store",
  "warranty": {
    "start_date": "2026-05-02",
    "end_date": "2027-05-02"
  },
  "attachments": []
}
```

## 리마인더 목록 API

### GET /api/reminders

사용자의 리마인더 목록을 조회한다.

### Response

```json
{
  "reminders": [
    {
      "id": "uuid",
      "product_id": "uuid",
      "type": "warranty_expiry",
      "remind_at": "2027-04-02T09:00:00Z",
      "status": "scheduled"
    }
  ]
}
```

## 리마인더 생성 API

### POST /api/reminders

리마인더를 생성한다.

### Request

```json
{
  "product_id": "uuid",
  "type": "warranty_expiry",
  "remind_at": "2027-04-02T09:00:00Z"
}
```

### Response

```json
{
  "id": "uuid",
  "status": "scheduled"
}
```
