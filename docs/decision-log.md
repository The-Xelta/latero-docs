# Decision Log

## 기록 방식

프로젝트 주요 결정 사항을 기록한다.

## Decision Template

```text
Date:
Decision:
Background:
Impact:
Owner:
```

## Decisions

### 2026-05-02

**Decision:** MVP는 영수증 OCR 기반 구매 기록 저장에 집중한다.

**Background:** 초기 버전에서 자동화 범위를 넓히면 개발 복잡도가 높아진다.

**Impact:** 제품 자동 매칭, 제조사 연동, 이메일 영수증 수집은 후순위로 둔다.

**Owner:** Product Team

---

### 2026-05-02

**Decision:** 워런티와 반품 기간은 사용자가 직접 수정할 수 있게 한다.

**Background:** OCR 및 자동 계산 결과가 항상 정확하지 않을 수 있다.

**Impact:** 자동 계산값은 초안으로 제공하고, 최종 데이터는 사용자 확인 후 저장한다.

**Owner:** Product Team

---

### 2026-05-02

**Decision:** 첨부 파일은 제품 단위로 관리한다.

**Background:** 보증서, 설명서, 제품 사진은 특정 제품과 연결되는 정보다.

**Impact:** Attachment는 Product에 연결한다.

**Owner:** Design / Development Team
