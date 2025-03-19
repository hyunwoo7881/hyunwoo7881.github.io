---
name: SQL 분석 프로젝트 - Spotify
tools: [SQL, Tableau]
image: assets/pngs/spotify_thumb.png
description: This project visualizes key spotify metrics, exploring user data
custom_js:
  - vega.min
  - vega-lite.min
  - vega-embed.min
  - justcharts
---

### SQL 분석 프로젝트 - Spotify
<br><br>
#### 분석의 목적
- 서비스 이용 패턴 파악:
    - Spotify 사용자들의 콘텐츠 선호도(음악 vs. 팟캐스트)와 구독(유료 vs. 무료) 패턴을 분석하여, 구독 결정에 영향을 미치는 요인을 도출하고자 함.
- 만족도 및 재구매 의향 확인:
    - 추천 음악 및 팟캐스트의 만족도와 사용 기간에 따른 서비스 만족도 변화를 살펴, 구독 의향과의 상관관계를 확인.
- 연령/성별에 따른 특성 분석:
    - 주요 고객층(특히 20~35세/ 여성)의 선호 장르, 구독 행동, 콘텐츠 소비 패턴 등을 분석하여 타겟 마케팅 및 서비스 개선 방향 모색.

<br><br>

#### 결과
- 콘텐츠 선호와 구독 패턴:
    - 음악과 팟캐스트 중 음악을 선호하는 사용자 수가 압도적으로 많으나, 음악 사용자들은 구독하지 않는 비율이 높음.
    - 구독 여부에 따른 추천 음악 만족도에서는 구독자가 비구독자보다 높은 만족도를 보임.
- 사용 기간과 만족도 변화:
    - 초기 6개월~1년 사용자들의 음악 추천 만족도가 다소 낮았다가, 서비스 이용 기간이 길어질수록 만족도가 상승하는 추세를 보임.
    - 팟캐스트의 경우, 전체 만족도는 높게 유지되며, 사용 기간이 늘어나면서 불만족 비율은 감소하는 경향이 있음.
- 연령 및 성별 특성:
    - 20~35세 사용자가 전체의 대부분을 차지하며, 이 그룹에서는 음악 선호 비율이 팟캐스트보다 현저히 높음.
    - 12~35세에서의 인기 있는 음악 장르는 약간의 차이를 보이지만, Melody, Pop, Classical 장르가 전 연령층에서 공통적으로 인기를 끔.
    - 성별 분석에서는 여성 사용자가 음악 및 팟캐스트 모두에서 남성보다 훨씬 높은 비중을 차지하며, 구독 관련 결과 역시 유사한 패턴을 보임.

<br><br>

#### 제안
- 구독 전환율 개선 방안 모색:
    - 음악 콘텐츠 이용자가 구독하지 않는 이유(예: 콘텐츠 길이, 가성비, 추천 시스템의 미흡함 등)를 추가 데이터나 설문 등을 통해 심층 분석할 필요가 있음.
- 추천 시스템 개선:
    - 구독자와 비구독자 간 추천 만족도의 차이를 고려하여, 추천 알고리즘을 더욱 정교화하거나 추가 개인 맞춤형 콘텐츠 제공 방안을 마련.
- 추가 데이터 확보 및 분석:
    - 현재 분석에서 드러난 한계(예: 구독 미실시 원인 파악 등)을 보완하기 위해, 소비자 피드백, 가격 민감도, 서비스 편의성, 서비스 비교 데이터 등 추가 정보를 수집하는 것이 필요함.
- 세분화된 고객 분석:
    - 더 (연령별, 성별, 콘텐츠 선호도)별로 보다 구체적인 ABC 분석 및 세그먼트별 전략 수립을 통해 타겟 마케팅 및 서비스 개선을 추진.

<br><br>

#### 데이터 설명
- **데이터 출처 및 구조:**
    - 데이터는 Spotify 관련 사용자 행동 및 선호도를 담은 테이블로 구성됨.
    - 주요 컬럼은 사용자 인구통계(나이, 성별), 서비스 사용 기간, 구독 플랜 및 구독 의향, 선호 콘텐츠, 추천 만족도, 팟캐스트 청취 빈도 및 선호 특성(장르, 형식, 호스트, 길이) 등으로 구분됨.

<br><br>


|Age                            |나이 그룹별	|
|Gender                        |`성별`            |
|spotify_usage_period          |`시용한 기간`            |
|spotify_subscription_plan          |`구독 플랜`            |
|premium_sub_willingness        | `구독 희망 여부`  |
|preferred_listening_content            |`선호하는 콘텐츠`            |
|fav_music_genre                        |`좋아하는 음악 장르`            |
|music_time_slot                        |`음악 듣는 시간대`            |
|music_recc_rating                        |`추천 음악 만족도`            |
|pod_lis_frequency                        |`팟캐스트 듣는 주기`            |
|fav_pod_genre                        |`선호하는 팟캐스트 장르`            |
|preffered_pod_format                  |`선호하는 팟캐스트 형식`            |
|pod_host_preference                   |`선호하는 팟캐스트 호스트`            |
|preffered_pod_duration                |`선호하는 팟캐스트 길이`            |
|pod_variety_satisfaction                 |`팟캐스트 만족도`            |

- **분석 방식:**
SQL 쿼리를 활용하여 그룹화, 집계, 비율 계산 등을 통해 각 변수 간의 상관관계 및 고객 특성을 분석함.

<br><br>

#### 근거
##### 1.1 선호하는 콘텐츠 별 → 구독플랜과 추후에 구독 희망 여부	

(어느 그룹이 더 구독을 잘할까/적극적일까?)

```sql
WITH using_col AS (
SELECT Age
    , Gender
    , spotify_usage_period
    , spotify_subscription_plan
    , premium_sub_willingness
    , preferred_listening_content
    , fav_music_genre
    , music_time_slot
    , music_recc_rating
    , pod_lis_frequency
    , fav_pod_genre
    , preffered_pod_format
    , pod_host_preference
    , preffered_pod_duration
    , pod_variety_satisfaction
FROM `eminent-ring-451902-n9.spotify.Spotify`
)
SELECT preferred_listening_content
    , spotify_subscription_plan
    , COUNT(spotify_subscription_plan)
FROM using_col
GROUP BY preferred_listening_content, spotify_subscription_plan
;
```

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp1.png" alt="사진1" style="width: 100%;">


**생각**: 
> 구독 안하는 비율이 훨씬 크고, 그중에 음악 듣는 사람들 많음.<br><br>
→ 왜 음악을 듣는 많은 사람들이 구독을 안하고 듣나?<br><br>
→ 음악과 팟캐스트의 길이 차이인가?<br><br>
→ 구독의 만족도나 가성비가 안좋나? (굳이인가?)<br><br>
→ 구독한 사람들의 추천 음악/팟캐 만족도를 보자

<br><br>
<br><br>

##### 1.2 구독 희망 여부 → 추천 음악 만족도 & 팟캐스트 만족도 
(서비스 만족도가 낮아서 구독을 덜 하는걸까?)

```sql
SELECT premium_sub_willingness
    , music_recc_rating
    , COUNT(music_recc_rating) AS counts
FROM using_col
GROUP BY premium_sub_willingness, music_recc_rating
ORDER BY premium_sub_willingness DESC, music_recc_rating ASC
;
```
<img src="{{ site.baseurl }}/assets/pngs/spotify/sp2.png" alt="사진2" style="width: 80%;">


**생각**: 
> 구독 안한 사람들에 비해 구독한 사람들이 음악 추천에 대해 만족도가 더 높네.

<br><br>

그럼 만족도 점수별 (구독한다 vs 안한다)은 어떻게 나타날까?
```sql
SELECT music_recc_rating
    , premium_sub_willingness
    , COUNT(premium_sub_willingness) AS counts
FROM using_col
GROUP BY  music_recc_rating, premium_sub_willingness
ORDER BY music_recc_rating ASC, premium_sub_willingness DESC
;
```
<img src="{{ site.baseurl }}/assets/pngs/spotify/sp3.png" alt="사진3" style="width: 80%;">
**생각**: 
>→ (꽤 높은 점수인)3~4점을 줬는데, 구독은 안한다는 사람 수가 구독 한다는 사람수에 거의 2배인데..<br><br>
→ 굳이 추천이 맘에 안들어서 구독을 안하는건 아닌것 같은데?

<br><br>
<br><br>
##### 2.1 사용한 기간  → 추천 음악 & 팟캐스트 만족도

(사용한 기간이 늘어나면서 만족도 차이는? 우리 서비스에 점점 만족하는가?)
```sql
-- 스포티파이 뮤직
SELECT spotify_usage_period
    , ROUND(AVG(music_recc_rating),2) AS avg_music_recc_rating
FROM using_col
GROUP BY spotify_usage_period
ORDER BY avg_music_recc_rating DESC
;
```
<img src="{{ site.baseurl }}/assets/pngs/spotify/sp4.png" alt="사진4" style="width: 80%;">

> 사용한 기간이 늘어나면서 만족도 차이는? 우리 서비스에 점점 만족하는가?

<br><br>

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp5.png" alt="사진5" style="width: 100%;">

<br><br>

> 6개월~1년 사용자들의 음악 추천 평균 만족도가 줄어들었다가 증가함.

<br><br>
<br><br>

```sql
-- 스포티파이 팟캐스트
SELECT pod_variety_satisfaction
    , COUNT(*) AS counts
    , ROUND(100 * COUNT(*) / (SELECT COUNT(*) FROM using_col),2) AS composition_ratio
FROM using_col
GROUP BY pod_variety_satisfaction
ORDER BY composition_ratio DESC
;
```

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp6.png" alt="사진6" style="width: 80%;">


<img src="{{ site.baseurl }}/assets/pngs/spotify/sp7.png" alt="사진7" style="width: 100%;">

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp8.png" alt="사진8" style="width: 110%;">

> 일단 전체적인 비율로는 전반적으로 만족하는것 같네.

<br><br>
<br><br>

##### 2.2 그럼 각각의 사용주기에 따른 (서비스 이용기간에 따른) 만족도 변화는?
```sql
SELECT spotify_usage_period
    , pod_variety_satisfaction
    , COUNT(*) AS counts
    , SUM(COUNT(*)) OVER (PARTITION BY spotify_usage_period) AS total_counts
    , ROUND(100 * (COUNT(*) / SUM(COUNT(*)) OVER (PARTITION BY spotify_usage_period)), 2) AS composition_ratio
FROM using_col
GROUP BY spotify_usage_period, pod_variety_satisfaction
ORDER BY spotify_usage_period, pod_variety_satisfaction
;
```

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp9.png" alt="사진9" style="width: 90%;">

<br><br>

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp10.jpg" alt="사진10" style="width: 100%;">

<br><br>

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp11.jpg" alt="사진11" style="width: 100%;">

> 시간 흐를수록 불만족하는 비율이 줄어드는걸 확인할수 있음. (시간이 지날수록 서비스에 만족하는 비율 늘어남. 긍정적!)

<br><br>
<br><br>

##### 3. 나이별/성별 → 선호하는 콘텐츠
(나이별/성별로 선호하는 콘텐츠는 뭘까?)
<br><br>
##### 3.1 나이별 → 선호하는 콘텐츠 (팟캐/ 뮤직)
```sql
SELECT Age
    , preferred_listening_content
    , COUNT(preferred_listening_content) AS counts
FROM using_col
GROUP BY Age, preferred_listening_content
ORDER BY Age
;
```

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp12.png" alt="사진12" style="width: 110%;">

>  사용자의 대부분은 20~35세 그룹이고, 그중에서도 뮤직을 듣는 사람의 수가 팟캐보다 훨씬 많음.<br><br>
> (다른 나이대의 사용자들은 뮤직과 팟캐의 비율이 거의 같음.) <br><br>
> 그럼 가장 많은 비율을 차지하는 나이대인 20~35세에서의 구독에 대한 생각은 어떨까? 좋아하는 음악 장르는?

<br><br>
<br><br>

##### 3.2 나이별 인기있는 음악 장르는? 
```sql
SELECT Age
    , fav_music_genre
    , COUNT(*) AS counts
    , ROUND(100 * COUNT(*) / SUM(COUNT(*)) OVER (PARTITION BY
         Age), 2)
            AS composition_ratio
FROM using_col
GROUP BY Age, fav_music_genre
ORDER BY Age
;
```

<img src="{{ site.baseurl }}/assets/pngs/spotify/sp13.png" alt="사진13" style="width: 70%;">

> → 각 나이별로 보면, 12~20세에서는 Classical, Rap, Melody순으로 인기가 가장 많음. 사용자중에 가장 많은 비중을 차지하는 20~35세에서 인기있는 장르는 Melody(54.74%), Pop(17.6%), classical(13.27%).<br><br>
> → Melody, Pop, classical. 이 3가지 장르가 전 연령층에 걸쳐서 공통적으로 가장 인기있음.<br><br>
그럼 가장 많은 비율을 차지하는 나이대인 20~35세에서의 구독에 대한 생각은 어떨까?

<br><br>
<br><br>

##### 3.3 20~35세에서의 구독 비율
```sql
SELECT spotify_subscription_plan
     , COUNT(*) AS counts
FROM using_col
WHERE Age = '20-35'
GROUP BY spotify_subscription_plan
;
```
<img src="{{ site.baseurl }}/assets/pngs/spotify/sp14.png" alt="사진14" style="width: 100%;">

<br><br>
<br><br>

##### 3.4 20~35세에서의 구독 희망 여부
```sql
SELECT premium_sub_willingness
    , COUNT(*) AS counts
FROM using_col
WHERE Age = '20-35'
GROUP BY premium_sub_willingness
;
```
<img src="{{ site.baseurl }}/assets/pngs/spotify/sp15.png" alt="사진15" style="width: 100%;">

> → 현재 가장 많은 비율을 차지하는 나이대인 20~35세에서는 구독보다는 무료(광고)로 사용하는 비율이 훨씬 높음(거의 6:1). 하지만 긍정적인 점은 구독을 희망하는 사람 비율이 큰걸로 보아. 서비스에 만족하고 추후에 구독을 신청할 사람들이 많아보임. 

<br><br>
<br><br>

##### 4.1  성별 → 선호하는 콘텐츠 (팟캐/ 뮤직)
```sql
SELECT Gender
    , preferred_listening_content
    , COUNT(preferred_listening_content) AS counts
FROM using_col
GROUP BY Gender, preferred_listening_content
;
```
<img src="{{ site.baseurl }}/assets/pngs/spotify/sp16.png" alt="사진16" style="width: 100%;">

> - 팟캐나 뮤직 둘다 여성이 차지하는 비중이 남성보다 훨씬 큼. <br><br>
> - 팟캐에서는 여성이 남성의 4배, 뮤직에서는 여성이 3배 많음.

<br><br>
<br><br>

##### 4.2  성별 →인기있는 음악장르 
```sql
SELECT Gender
   , fav_music_genre
   , COUNT(*) AS counts
   , ROUND(100 * COUNT(*) / SUM(COUNT(*)) OVER (PARTITION BY 
        Gender), 2)
            AS composition_ratio
FROM using_col
GROUP BY Gender, fav_music_genre
ORDER BY Gender
;
```
<img src="{{ site.baseurl }}/assets/pngs/spotify/sp17.jpg" alt="사진17" style="width: 100%;">

> → 여성에게는 Melody(55.5%), Pop(15.6%), Classical(14.83%) 순으로 인기가 가장 많았고 / 남성에게는 Melody(35.96%), Pop(20.18%), Classical(20.18%) 순으로 인기가 있음. 둘다 인기있는 상위 음악 장르는 비슷한 트렌드를 보여줌. <br><br>
> → 그럼 우리 뮤직의 주 고객층인 여성들은 우리의 음악 추천 서비스에 얼만큼 만족하고 있을까?

<br><br>
<img src="{{ site.baseurl }}/assets/pngs/spotify/sp18.png" alt="사진18" style="width: 80%;">
> → 많은 수의 여성 사용자들은 현재의 음악 추천 시스템에 대해 만족하는것처럼 보임. 하지만 3점에 가장 많은 140명이 있다? 무슨 의미 일까? (추가적인 데이터 수집이 필요해보임)
