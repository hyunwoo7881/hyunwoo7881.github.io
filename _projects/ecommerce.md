---
name: SQL 분석 프로젝트 - eCommerce
tools: [SQL, Tableau] 
image: assets/pngs/ecommerce_썸.jpeg
description: This project visualizes key U.S. ecommerce metrics, exploring user behavioral data
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

## SQL 분석 프로젝트 - eCommerce
<br><br>

### 분석의 목적
이 프로젝트는 eCommerce 데이터를 활용하여 마케팅 채널 분석, 웹사이트 퍼포먼스 측정, 제품 포트폴리오 분석을 수행하는 것을 목표로 한다. 특히, 트래픽 소스별 성과를 분석하고, 브랜드 인지도의 성장 여부를 평가하며, A/B 테스트를 통해 랜딩 페이지 변경이 수익에 미치는 영향을 확인한다.


- 데이터베이스 설명:
	- UTM sources로는 gsearch(Google)와 bsearch(Bing).
	- UTM capmaigns로는 nonbrand와 brand.
		- (nonbrand 그룹은 제품의 카테고리 또는 관련 검색어로 찾아온 고객들 / brand 그룹은 브랜드의 이름을 검색해서 들어온 고객들.)

- 프로젝트 배경:
    - 상황: 8개월된 인터넷 소매업체가 있고, CEO가 프레젠테이션에 필요한 회사의 performance metrics가 필요한 상황.
    - 목표: performance 데이터와 웹 트래픽등을 SQL로 추출하고, 회사의 성장을 수치화하고 분석하기.

<br><br>
<br><br>
### 결과
- **Gsearch 트래픽 증가**: 

> Gsearch(구글 광고)에서 발생한 세션 수가 꾸준히 증가하며, 주문 수 및 전환율 또한 상승하는 경향을 보였다. 첫 달 1,860건에서 시작하여 마지막 달에는 8,895건으로 증가하였으며, 주문 수 역시 92건에서 373건으로 약 4배 증가하였다. 전환율 또한 2.6%에서 4%로 상승하여 광고 캠페인이 지속적으로 성과를 내고 있음을 보여준다.

- **Brand vs. Nonbrand 비교**:

> 브랜드 키워드를 검색한 고객들의 세션 수가 비약적으로 증가하여, 브랜드 인지도가 상승했음을 시사한다. 특히 브랜드 검색 트래픽이 지속적으로 증가하면서, 유료 광고 트래픽의 의존도를 줄이고 브랜드 자체의 검색 유입이 늘어나고 있다. 이는 장기적으로 광고 비용 절감과 브랜드 가치 향상에 기여할 가능성이 있다.

- **기기별 Nonbrand 분석**: 

> Nonbrand 검색을 통한 트래픽에서 데스크탑과 모바일의 비율이 초기 2:1에서 3:1로 확대되었으며, 주문 수에서도 유사한 변화가 나타났다. 특히, 모바일 트래픽이 증가하는 속도가 빠르지만, 여전히 데스크탑에서의 전환율이 높게 유지되는 경향을 보였다. 이는 모바일 UX 최적화가 필요할 수 있음을 시사하며, 향후 데이터 분석을 통해 모바일 고객의 구매 여정을 더욱 세밀하게 파악할 필요가 있다.

- **Gsearch 트래픽 비율 분석**: 

> 전체 트래픽에서 Gsearch의 비중이 지나치게 높은 것으로 나타났다. 유료 검색 채널뿐만 아니라, organic search 및 direct 유입 비율도 증가하고 있어 자연 유입을 더욱 강화할 필요가 있다. 이는 마케팅 전략을 조정하여 광고 비용 대비 효과적인 고객 확보 전략을 수립할 기회를 제공한다.

- **A/B 테스트 결과**: 

> 새로운 랜딩 페이지(l/lander-1)의 전환율이 기존 홈페이지(/home)보다 약 0.88% 더 높은 것으로 나타났으며, 실험 이후 4개월간 약 50건의 추가 주문이 발생했다. 특히 실험 이후 새로운 랜딩 페이지로 유입된 트래픽이 증가하며, 전환율이 꾸준히 향상되는 경향을 보였다.

<br><br>
<br><br>
### 제안
1. 브랜드 트래픽 강화: 브랜드 검색을 통해 유입되는 사용자가 증가하는 경향이므로, 장기적으로 유료 광고 의존도를 줄이고 브랜드 인지도를 높이는 전략이 필요하다.

2. 모바일 UX 개선: 모바일을 통한 트래픽 비율이 증가하고 있으므로, 모바일 최적화된 UX/UI 개선을 통해 전환율을 더욱 향상시킬 수 있다.

3. 랜딩 페이지 최적화: A/B 테스트 결과를 반영하여, 전환율이 더 높은 l/lander-1을 기본 랜딩 페이지로 설정하는 것이 유리할 것으로 보인다.

4. 유료 검색 채널 최적화: Gsearch 유입 비중이 지나치게 높은 점을 고려하여, organic 및 direct 유입을 더욱 강화하는 전략이 필요하다.

<br><br>
<br><br>
### 데이터 설명
- UTM Source: 트래픽 유입 경로 (Gsearch: 구글 광고, Bsearch: 빙 광고)

- UTM Campaign: 브랜드 검색(brand)과 비브랜드 검색(nonbrand) 구분

- Sessions: 웹사이트 방문 세션 수

- Orders: 발생한 주문 수

- Device Type: 트래픽 발생 기기 (데스크탑, 모바일)

- Landing Page: 사용자 최초 방문 페이지 (/home vs. /lander-1)




<br><br>
<br><br>
### 분석과정/ 근거

##### 1. gsearch의 세션수와 주문수의 월별 트렌드 보기

{% highlight sql %}
-- gsearch의 월별 세션수와 주문수 트렌드
SELECT YEAR(website_sessions.created_at) AS year
     , MONTH(website_sessions.created_at) AS month
     , COUNT(website_sessions.website_session_id) 
            AS gsearch_sessions
     , COUNT(order_id) AS gsearch_orders
     , COUNT(order_id) 
            / COUNT(website_sessions.website_sessions_id) 
            AS gsearch_conversion
FROM website_sessions
    LEFT JOIN orders ON website_sessions.website_session_id 
                            = orders.website_session_id
WHERE utm_source = 'gsearch' AND website_sessions.created_at < '2012-11-27'
GROUP BY 1, 2
;
{% endhighlight %}



<img src="{{ site.baseurl }}/assets/pngs/사진1.png" alt="사진1" style="width: 80%;">



**결과** :
 
> 확실하게 세션수는 시간이 지나면서 증가하고 있다. 첫달에 1860정도에 비해, 현재는 8895의 세션이 발생한다. 



> 주문수 또한 성장하고 있는데, 3월달 (92건)에 비해 현재는 거의 4배인 (373건)으로 많아진걸 확인 할 수 있다. 



> 전환율 같은 경우에는 첫 3달에는 2.6% 정도에 머물다가, 마지막 달에는 4%까지 높아진게 보인다.


<br><br>
<br><br>

##### 2. 검색 루트별 월별 트렌드 보기

- 이번엔 nonbrand/brand별로 나누어서 Gsearch의 월별 트렌드를 확인해보자.


{% highlight sql %}
SELECT YEAR(website_sessions.created_at) AS year
     , MONTH(website_sessions.created_at) AS month
     , COUNT(DISTINCT CASE WHEN utm_campaign = 'nonbrand' 
        THEN website_sessions.website_session_id ELSE NULL END)
            AS nonbrand_sessions
    , COUNT(DISTINCT CASE WHEN utm_campaign = 'nonbrand' 
        THEN website_sessions.orders.order_id ELSE NULL END)
            AS nonbrand_orders
    , COUNT(DISTINCT CASE WHEN utm_campaign = 'brand' 
        THEN website_sessions.website_session_id ELSE NULL END)
            AS brand_sessions
    , COUNT(DISTINCT CASE WHEN utm_campaign = 'brand' 
        THEN website_sessions.orders.order_id ELSE NULL END)
            AS brand_orders
FROM website_sessions
    LEFT JOIN orders
        ON website_sessions.website_session_id 
                        = orders.website_session_id
WHERE utm_source = 'gsearch' AND website_sessions.created_at < '2012-11-27'
GROUP BY  1, 2
;
{% endhighlight %}




<img src="{{ site.baseurl }}/assets/pngs/사진2.png" alt="사진2" style="width: 80%;">




**결과**: 
> 브랜드 캠페인은 검색 엔진에서 우리의 브랜드를 찾아서, 우리의 광고를 클릭해서 들어온 고객들을 나타낸다. 우리 회사는 유료 트래픽에 항상 의존해야 할까? 아니면 브랜드가 점점 인식되고 있을까? 위의 결과를 보았을때, 브랜드 세션수가 굉장히 많아 졌다. 자체 브랜드 인지도가 많이 늘었다는 걸 알수 있다.



<br><br>
<br><br>

##### 3. nonbrand 그룹의 기기별 세션수와 주문수 변화
{% highlight sql %}
SELECT YEAR(website_sessions.created_at) AS year
     , MONTH(website_sessions.created_at) AS month
     , COUNT(CASE WHEN device_type = 'desktop'
		THEN website_sessions.website_session_id ELSE NULL END)
			AS desktop_sessions
     , COUNT(CASE WHEN device_type = 'desktop'
		THEN orders.order_id ELSE NULL END) 
			AS desktop_orders
	 , COUNT(CASE WHEN device_type = 'mobile'
		THEN website_sessions.website_session_id ELSE NULL END)
			AS mobile_sessions
     , COUNT(CASE WHEN device_type = 'mobile'
		THEN orders.order_id ELSE NULL END)
			AS mobile_orders
FROM website_sessions
	LEFT JOIN orders
		ON website_sessions.website_session_id = orders.website_session_id
WHERE utm_source = 'gsearch'
	AND utm_campaign = 'nonbrand'
    AND website_sessions.created_at < '2012-11-27'
GROUP BY 1, 2;
{% endhighlight %}



<img src="{{ site.baseurl }}/assets/pngs/사진3.png" alt="사진3" style="width: 100%;">




**결과**: 
> - 여기서 확인 할수 있는건, 데스트탑의 세션수가 모바일보다 훨씬 많다는 점이다. 초기에는 (데스트탑:모바일) 비율이 거의 2:1인데, 거의 뒤에 오면 3:1 수준으로 차이가 더 벌이지고 있다.
<br><br>
>- 주문수를 확인하면 이 변화가 더 뚜렸한데, 초기에 (데스트탑:모바일) 5:1이던 비율이  10:1로 변한걸 볼수 있다.


<br><br> 
<br><br>

##### 4. gsearch의 각 채널당 월별 트랜드 확인하기
{% highlight sql %}
SELECT DISTINCT utm_source
     , utm_campaign
     , http_referer
FROM website_sessions
WHERE created_at < '2012-11-27';
{% endhighlight %}


<img src="{{ site.baseurl }}/assets/pngs/사진4.png" alt="사진4" style="width: 80%;">



**결과**: 

> 현재 회사의 gseach의 트래픽 비중이 너무 큰건 아닐까?  우리 회사는 현재 UTM source로 Gsearch(google)과 Bsearch(bing)이 있다. 그리고 각각 nonbrand와 brand로 나눠서 볼수 있다.




> 이런 유료채널 외에도 direct typie-in과 organic 검색 채널들을 보자.(direct type-in은 링크에 검색해서  / organic search는 우리가 정의하지 않은 검색 엔진을 통해 들어온 트래픽을 나타낸다.)




{% highlight sql %}
SELECT YEAR(website_sessions.created_at) AS year
     , MONTH(website_sessions.created_at) AS month
     , COUNT(DISTINCT CASE WHEN utm_source = 'gsearch'
		THEN website_sessions.website_session_id ELSE NULL END)
			AS gsearch_paid_sessions
	, COUNT(DISTINCT CASE WHEN utm_source = 'bsearch'
		THEN website_sessions.website_session_id ELSE NULL END)
			AS bsearch_paid_sessions
	, COUNT(DISTINCT CASE WHEN utm_source IS NULL AND http_referer 
        IS NOT NULL THEN website_sessions.website_session_id ELSE 
            NULL END)
			    AS organic_search_sessions
	, COUNT(DISTINCT CASE WHEN utm_source IS NULL AND http_referer
          IS NULL THEN website_sessions.website_session_id ELSE 
            NULL END)
			    AS direct_type_in_sessions
FROM website_sessions
	LEFT JOIN orders
		ON website_sessions.website_session_id = orders.website_session_id
WHERE website_sessions.created_at < '2012-11-27'
GROUP BY 1, 2;
{% endhighlight %}




<img src="{{ site.baseurl }}/assets/pngs/사진5.png" alt="사진5" style="width: 100%;">


**결과**:
> 여기서 보이는건, 처음 2개 (gsearch, bsearch) 같은 경우에는 회사에서 비용을 지불하고 있고, 세션 수가 늘면 그에 비례해서 비용도 늘어날 것이다.
하지만 뒤에 2개 (organic, direct type in) 같은 경우에는 돈을 내지 않고 있다. 그럼에도 뒤에 organic, direct 채널에서도 세션수가 늘어나고 있다는 건 긍정적인 신호이다.



<br><br>
<br><br>
 
##### 5. 월별 웹사이트의 전환율 변화

{% highlight sql %}
SELECT YEAR(website_sessions.created_at) AS year
     , MONTH(website_sessions.created_at) AS month
     , COUNT(DISTINCT website_sessions.website_session_id) 
        AS sessions
     , COUNT(DISTINCT orders.order_id) AS orders
     , COUNT(DISTINCT orders.order_id) /
		COUNT(DISTINCT website_sessions.website_session_id) 
            AS conversion_rate
FROM website_sessions
	LEFT JOIN orders
		ON website_sessions.website_session_id = orders.website_session_id
WHERE website_sessions.created_at < '2012-11-27'
GROUP BY 1, 2;
{% endhighlight %}


<img src="{{ site.baseurl }}/assets/pngs/사진6.png" alt="사진6" style="width: 80%;">


**결과**:
> 전환율 같은 경우에는 4월에는 2.6% 였지만, 점점 증가하다가 4.4%까지 개선된걸 볼수 있다.


<br><br>
<br><br>
 
##### 6. A/B 테스트 (랜딩 페이지별 수익 비교)
*홈페이지 관리자가 만든 새로운 랜딩 페이지(/lander-1)와 기존 홈페이지(/home)을 6월 17일 부터 6월 28일 까지 시험적으로 사용해 보았을때, 어떤 페이지가 더 많은 수익을 발생시켰을까?

###### Step 1: 테스트 시작 시점 찾기.
{% highlight sql %}
SELECT MIN(website_pageview_id) AS first_test_pv
FROM website_pageviews
WHERE pageview_url = '/lander-1';
{% endhighlight %}


<img src="{{ site.baseurl }}/assets/pngs/사진7.png" alt="사진7" style="width: 80%;">


> /lander-1의 첫 페이지뷰 Id(23504)를 가져와서 테스트의 시작 시점을 확인하자.




<br><br> 
###### Step 2: 테스트 기간동안의 세션 데이터 가져오기.

{% highlight sql %}
DROP TABLE IF EXISTS first_test_pageview;
CREATE TEMPORARY TABLE first_test_pageview
SELECT website_sessions.website_session_id
     , MIN(website_pageviews.website_pageview_id) AS min_pageview_id
FROM website_pageviews
	JOIN website_sessions
		ON website_pageviews.website_session_id = 
			website_sessions.website_session_id
WHERE website_pageviews.website_pageview_id >= '23504'
	AND website_sessions.created_at < '2012-07-28'
    AND utm_source = 'gsearch'
	AND utm_campaign = 'nonbrand'
GROUP BY website_sessions.website_session_id
;

SELECT *
FROM first_test_pageview
;
{% endhighlight %}


<img src="{{ site.baseurl }}/assets/pngs/사진8.png" alt="사진8" style="width: 80%;">



> 테스트 기간동안의 gsearch nonbrand의 트래픽 중에, 각 세션별로 첫 페이지뷰(랜딩 페이지)를 찾는다.



<br><br> 
###### Step 3: 랜딩 페이지 매핑하기.

{% highlight sql %}
DROP TABLE IF EXISTS nonbrand_test_sessions_landing_pages
;
CREATE TEMPORARY TABLE nonbrand_test_sessions_landing_pages
SELECT website_pageviews.website_session_id
     , pageview_url AS landing_page
FROM first_test_pageview
	LEFT JOIN website_pageviews
		ON first_test_pageview.min_pageview_id =
			website_pageviews.website_pageview_id
WHERE pageview_url IN ('/home', '/lander-1')
;

SELECT *
FROM nonbrand_test_sessions_landing_pages
;
{% endhighlight %}



<img src="{{ site.baseurl }}/assets/pngs/사진9.png" alt="사진9" style="width: 80%;">



> 각 세션의 랜딩 페이지를 기반으로, 각각의 세션이 /home 또는 /lander-1 중에서 어떤 랜딩 페이지인지 매핑을 한다. 다시 말해, 어떤 랜딩 페이지를 통해 사용자가 유입되었는지 식별하기 위한 작업이다.

<br><br>

###### Step 4: 세션별로 주문이 발생했는지 확인하자.

{% highlight sql %}
DROP TABLE IF EXISTS nonbrand_test_session_orders
;
CREATE TEMPORARY TABLE nonbrand_test_session_orders
SELECT nonbrand_test_sessions_landing_pages.website_session_id
     , nonbrand_test_sessions_landing_pages.landing_page
     , orders.order_id
FROM nonbrand_test_sessions_landing_pages
	LEFT JOIN orders
		ON nonbrand_test_sessions_landing_pages.website_session_id 
            = orders.website_session_id
;
SELECT *
FROM nonbrand_test_session_orders
;
{% endhighlight %}


<img src="{{ site.baseurl }}/assets/pngs/사진10.png" alt="사진10" style="width: 80%;">



> 각 세션 id를 기준으로 주문 데이터와 연결한다. 이를 통해 각각의 세션에서 실제로 주문으로 이어졌는지 알수있다.


<br><br> 
###### Step 5: 전환율 계산하기

{% highlight sql %}
-- /home 과 /lander-1의 성과를 비교하기 위해 전환율을 계산하자 
-- (전환율 = 주문 수 / 세션 수). 

SELECT landing_page
     , COUNT(DISTINCT website_session_id) AS sessions
     , COUNT(DISTINCT order_id) AS orders
     , COUNT(DISTINCT order_id) 
        / COUNT(DISTINCT website_session_id) 
        AS conv_rate
FROM nonbrand_test_session_orders
GROUP BY 1
;
{% endhighlight %}


<img src="{{ site.baseurl }}/assets/pngs/사진11.png" alt="사진11" style="width: 80%;">



**결과**:
> - /home의 전환율: 3.18%
> - /lander-1의 전환율: 4.06%
> - /lander-1의 전환율이 더 높음  ⇒ 약 0.88%의 추가 전환율.


<br><br> 
###### Step 6: 가장 최근에 /home으로 랜딩된 세션 찾기.

{% highlight sql %}
SELECT MAX(website_sessions.website_session_id) 
        AS most_recent_gsearch_nonbrand_home_session
FROM website_sessions
	LEFT JOIN website_pageviews
		ON website_sessions.website_session_id 
            = website_pageviews.website_session_id
WHERE utm_source = 'gsearch'
	AND utm_campaign = 'nonbrand'
    AND pageview_url = '/home'
    AND website_sessions.created_at < '2012-11-27'
    ;
{% endhighlight %}


<img src="{{ site.baseurl }}/assets/pngs/사진12.png" alt="사진12" style="width: 80%;">


**결과**:
> 가장 최근에 /home 페이지로 연결된 트래픽의 세션 id를 찾아보니, ‘17145’인걸 알수 있음. 이 이후에는 새로운 /lander-1으로 트래픽이 리라우팅 되었다.


<br><br> 
###### Step 7: 추가 주문 수 계산하기

{% highlight sql %}
SELECT
	COUNT(website_session_id) AS sessions_since_test
FROM website_sessions
WHERE created_at < '2012-11-27'
	AND website_session_id > 17145
    AND utm_source = 'gsearch'
    AND utm_campaign = 'nonbrand'
;
{% endhighlight %}


<img src="{{ site.baseurl }}/assets/pngs/사진13.png" alt="사진13" style="width: 80%;">



**결과**:
> 테스트가 끝난 후에 발생한 총 세션수: 22972.

1. 추가 주문 수 계산하기:
- 증가한 전환율(0.0088)로 인해 발생한 추가 주문 수 계산을 한다면:
- 추가 주문 수  =  총 세션 수 x 추가 전환율
    
            = 22,988 x 0.0088     ≈ 202
    

2. 월별 추가 주문 수 계산하기:

- 실험 이후 약 4개월 간의 데이터를 바탕으로 계산하면,
    - 202 / 4 = 50.5
    - 월평균 약 50건의 추가 주문이 발생한걸 알수있다.


<div class="left">
{% include elements/button.html link="https://www.kaggle.com/datasets/ammaraahmad/us-ecommerce-record-2020" text="The Data" %}
</div>
