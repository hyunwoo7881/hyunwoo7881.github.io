---
name: SQL 분석 프로젝트 - 온라인 리테일(리텐션 분석)
tools: [SQL, Excel]
image: assets/pngs/retention/rt2.jpg
description: This project visualizes key online retail company's metrics, exploring customers' purchasing pattern.
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

#### SQL 분석 프로젝트 - 온라인 리테일 (리텐션 분석)
<br><br>

#### 분석의 목적
온라인 리테일 회사의 고객 재구매 패턴과 유지율(Retention Rate)을 분석하여, 고객 이탈을 줄이고 장기적인 충성도를 높이는 전략을 수립하는 것임. 이를 위해, 클래식 리텐션과 롤링 리텐션을 비교하여 고객의 재방문 패턴을 이해하고, 효과적인 리텐션 전략을 도출하는 것이 목표.

<br><br>

**초기, 중기, 장기적인** 관점에서,

1️⃣ **신규 고객의 이탈률은 얼마나 높은가?**
- 첫 구매 후 일정 기간 내 이탈하는 고객 비율을 파악하여, 초기 리텐션을 개선할 방법을 찾는다.

2️⃣ **고객이 다시 돌아오는 패턴이 존재하는가?**
- 특정 기간(예: 6개월~9개월 후)에 고객이 재방문하는지 확인하여, 재참여(Re-engagement) 전략을 설계한다.

3️⃣ **충성 고객의 특징은 무엇인가?**
- 장기적으로 브랜드와 관계를 유지하는 고객이 얼마나 되는지 분석하여, VIP 고객을 위한 맞춤 전략을 마련한다.

<br><br>

#### 결과
1. 신규 고객 이탈률이 높음  —> 초기 고객 유지 전략이 필요함.
    1. `month_1`(첫 구매 후 1개월 차)에서 고객 수가 급감함.
    2. 많은 고객이 한번 구매 후 더이상 구매하지 않음.
    3. 이는 온보딩 경험 부족 또는 첫 구매 후 추가적인 유입 유도가 부족한 것일 수도 있음.
<br><br>
2. 일정 기간 후 고객이 다시 돌아오는 경향 존재 —> 재참여 전략 필요.
    1. 클래식 리텐션에서 `month_8`~`month_9`에 고객 수가 증가하는 패턴 발견.
    2. 고객이 특정 시점(할인 행사, 시즌 이벤트 등)에 돌아올 가능성이 높음.
    3. 이는 고객의 재구매 주기가 존재할 가능성이 높으며, 프로모션의 영향을 받는것일 수도 있음.

<br><br>

#### 제안
1. **신규 고객 유치 전략 (초기 리텐션 개선)**
    1. 첫 구매 후 30일 내 추가 구매 유도 → “Welcome 리텐션 캠페인” 실행
        1. 목표: 첫 구매 후 1개월 내 재구매율을 높여 month_1 이탈률 줄이기.
        2. 방법:
            1. 첫 구매 후 “재방문 유도 할인 쿠폰” 제공 (ex. 첫 구개 감사 쿠폰! 30일 이내 사용 가능)
            2. 개인화된 추천 제품 전송 (첫 구매 제품과 연관된 상품 추천 → 같이 잘팔리는 상품 조합을 추후에 분석해 볼수 있음  Market Basket Analysis)
            3. 푸시 알림 & 리마인더 메시지 활용 (이전 관련 상품과 연관된 상품등으로 + 대신 알림 메시지 활용이 정말 필요한지에 대한 접근은 좀더 조심히 해야함)
<br><br>
            
2. **고객 재참여 전략 (휴면 고객 활성화)**
    1. 특정 기간 이후 다시 돌아온 고객을 대상을로 “재활성화 프로모션” 진행.
        1. 목표: 특정 월(`month_8`, `month_9`)에 다시 증가하는 고객을 효과적으로 타겟팅하여 리텐션 향상.
        2. 방법:
            1. 장기 미구매 고객에게 “재방문 특별 혜택” 제공 (ex. “오랜만이에요! 돌아와 주셔서 감사합니다. 특별 10% 할인 쿠폰 증정”)
            2. 이탈 고객을 위한 맞춤형 이메일 캠페인 (개인 맞춤 상품 추천)
<br><br> 
            
3. **충성 고객 대상**
    1. 재구매 패턴이 있는 고객을 대상으로 구독 모델 & 멤버십 프로그램 도입
        1. 목표: 롤링 리텐션에서 나타난 "장기 유지 고객"을 더욱 락인하여, 이탈을 줄이고 LTV(Customer Lifetime Value)를 극대화.
        2. 방법:
            - "프리미엄 멤버십" 도입 (예: "VIP 고객 전용 무료 배송 & 특별 할인")
            - 정기구독 모델 도입 (예: "매달 필요한 제품을 자동으로 받아보세요! 정기구독 할인 적용")
            - 포인트 적립 & 리워드 시스템 (예: "3개월 연속 구매 시 추가 할인 혜택 제공")

<br><br>
<br><br> 
### 데이터 설명
**클래식 리텐션**

<img src="{{ site.baseurl }}/assets/pngs/retention/rt1.jpg" alt="사진1" style="width: 100%;">

- **클래식 리텐션은 특정 코호트에서 특정 달에 다시 구매한 고객 수를 나타냄.**
- `month_0`(첫 구매 달) 이후, `month_1`부터 급격히 감소하는 패턴을 보임.
- 하지만 **몇몇 코호트에서 특정 달(`month_8`, `month_9` 등)에 고객 수가 증가하는 패턴**이 나타남.
    - 이는 고객이 일정 기간 구매를 하지 않다가 다시 돌아오는 경우가 있음을 의미함.
    - 예를 들어, `2011-01-01` 코호트에서 `month_8`(8개월 차)에서 131명으로 다시 증가.
- **즉, 고객의 재구매 행동이 일정한 간격을 두고 발생하는 경향이 있음.**
    - 시즌 할인, 프로모션, 이메일 마케팅 효과 가능성이 있음.
    - 제품의 소비 주기가 존재할 가능성 있음.

<br><br>

**클래식 리텐션**

<img src="{{ site.baseurl }}/assets/pngs/retention/rt2.jpg" alt="사진2" style="width: 100%;">


- **롤링 리텐션은 고객이 한 번이라도 돌아오면 이탈하지 않은 것으로 간주되므로, 값이 더 높게 유지됨.**
- `month_0` 이후에도 `month_N`에서 여전히 높은 고객 수 유지.
- **클래식 리텐션보다 훨씬 천천히 감소하는 형태**를 띄며, `month_6` 이후에도 일정 수준 이상 유지됨.
- **고객들이 일정 주기로 돌아오는 패턴이 확인됨** → 고객이 브랜드를 완전히 이탈하지 않고 재구매하는 성향이 있음.

<br><br>
<br><br>
#### 쿼리
1. 클랙식 리텐션 쿼리
```sql
-- 날짜 형식을 시간을 제외해줌
WITH id_and_new_date AS ( 
 SELECT CustomerID
    , PARSE_DATE("%Y.%m.%d", REGEXP_REPLACE(InvoiceDate, 
                r'[\s].*', ""))  as invoiceDate
 FROM `eminent-ring-451902-n9.ai. new_table`
 WHERE CustomerID is not null
       and CustomerID != "CustomerID"
), purch_months AS (  -- 구매한 달과 가장 처음 구매한 달
 SELECT CustomerID
     , invoiceDate
     , DATE_TRUNC(invoiceDate, MONTH) 
            as purchase_month
     , DATE_TRUNC(MIN(invoiceDate) OVER (PARTITION BY CustomerID 
        ORDER BY invoiceDate), MONTH) 
            as first_purchase_month
 FROM id_and_new_date
), records_preprocessed AS ( -- 구매한 달과 처음 구매한 달 차이 = 코호트 달
 SELECT *
     , CONCAT("month_", DATE_DIFF(purchase_month, 
                first_purchase_month, MONTH))
                    as cohort_month
 FROM purch_months
)  -- 처음 구매한 달과 코호트 달을 기준으로 피벗
SELECT first_purchase_month
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_0' 
            THEN CustomerID END) AS month_0
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_1' 
            THEN CustomerID END) AS month_1
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_2' 
            THEN CustomerID END) AS month_2
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_3' 
            THEN CustomerID END) AS month_3
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_4' 
            THEN CustomerID END) AS month_4
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_5' 
            THEN CustomerID END) AS month_5
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_6' 
            THEN CustomerID END) AS month_6
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_7' 
            THEN CustomerID END) AS month_7
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_8' 
            THEN CustomerID END) AS month_8
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_9' 
            THEN CustomerID END) AS month_9
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_10' 
            THEN CustomerID END) AS month_10
    , COUNT(DISTINCT CASE WHEN cohort_month = 'month_11' 
            THEN CustomerID END) AS month_11
FROM records_preprocessed
WHERE first_purchase_month >= '2010-12-31'
GROUP BY first_purchase_month
ORDER BY first_purchase_month
;
```

<img src="{{ site.baseurl }}/assets/pngs/retention/rt3.jpg" alt="사진3" style="width: 120%;">

<br><br>

2. 롤링 리텐션 쿼리
```sql
WITH id_and_new_date AS ( -- 날짜 형식을 시간을 제외해줌
SELECT CustomerID
    , PARSE_DATE("%Y.%m.%d", REGEXP_REPLACE(InvoiceDate, 
                r'[\s].*', "")) as invoiceDate
FROM `eminent-ring-451902-n9.ai. new_table`
WHERE CustomerID is not null
      and CustomerID != "CustomerID"
), purch_months AS ( -- 구매한 달과 가장 처음 구매한 달 + 마지막 구매한 달
SELECT CustomerID
    , invoiceDate
    , DATE_TRUNC(invoiceDate, MONTH) as purchase_month
    , DATE_TRUNC(MIN(invoiceDate) OVER (PARTITION BY CustomerID 
            ORDER BY invoiceDate), MONTH) 
                as first_purchase_month
    , DATE_TRUNC(MAX(invoiceDate) OVER (PARTITION BY CustomerID 
            ORDER BY invoiceDate), MONTH) 
                as last_purchase_month
FROM id_and_new_date
)
-- 롤링 리텐션 - 월별 구매
SELECT first_purchase_month
   , COUNT(DISTINCT CustomerID) as month_0
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 1 month) = purchase_month THEN CustomerID END) 
            AS month_1
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 2 month) = purchase_month THEN CustomerID END) 
            AS month_2
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 3 month) = purchase_month THEN CustomerID END) 
            AS month_3
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 4 month) = purchase_month THEN CustomerID END) 
            AS month_4
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 5 month) = purchase_month THEN CustomerID END) 
            AS month_5
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 6 month) = purchase_month THEN CustomerID END) 
            AS month_6
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 7 month) = purchase_month THEN CustomerID END) 
            AS month_7
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 8 month) = purchase_month THEN CustomerID END) 
            AS month_8
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 9 month) = purchase_month THEN CustomerID END) 
            AS month_9
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 10 month) = purchase_month THEN CustomerID END)
            AS month_10
   , COUNT(DISTINCT CASE WHEN DATE_ADD(first_purchase_month, 
        INTERVAL 11 month) = purchase_month THEN CustomerID END)
            AS month_11
FROM purch_months
WHERE first_purchase_month >= '2010-12-31'
GROUP BY first_purchase_month
ORDER BY first_purchase_month
;
```
<img src="{{ site.baseurl }}/assets/pngs/retention/rt4.jpg" alt="사진4" style="width: 120%;">
<br><br>
