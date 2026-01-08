# DuckDuckGo Search Scraper

[![Promo](https://media.brightdata.com/2025/08/SERP-API-50-off-GitHub-banner_1389_166.png)](https://brightdata.co.kr/products/serp-api/duckduckgo-search)

이 리포지토리는 DuckDuckGo 검색 엔진 결과 페이지(SERP)에서 데이터를 추출하기 위한 두 가지 솔루션을 제공합니다:

- **무료 DuckDuckGo Scraper:** 소규모로 DuckDuckGo 검색 결과를 スクレイピング하기 위한 도구입니다
- **엔터프라이즈급 DuckDuckGo SERP API:** 대량·실시간 데이터 추출을 위한 확장 가능하고 프로덕션 준비가 된 솔루션입니다([Bright Data's SERP Scraper API](https://brightdata.co.kr/products/serp-api)의 일부입니다)

## Table of Contents

- [Free DuckDuckGo SERP Scraper](#free-duckduckgo-serp-scraper)
  - [Setup Requirements](#setup-requirements)
  - [Quick Start Guide](#quick-start-guide)
  - [Sample Output](#sample-output)
  - [Limitations](#limitations)
- [DuckDuckGo SERP API](#duckduckgo-serp-api)
  - [Key Benefits](#key-benefits)
  - [Getting Started](#getting-started)
- [Implementation Methods](#implementation-methods)
  - [Direct API Access](#direct-api-access)
  - [Native Proxy-Based Access](#native-proxy-based-access)
- [DuckDuckGo Search Query Parameters](#duckduckgo-search-query-parameters)
  - [Localization](#localization)
  - [Safe Search Configuration)](#safe-search-configuration-kp)
  - [Time Range Filtering](#time-range-filtering-df)
  - [Device Targeting](#device-targeting-brd_mobile)
  - [Browser Emulation](#browser-emulation-brd_browser)
- [Practical Example](#practical-example)
- [Support & Resources](#support--resources)

## Free DuckDuckGo SERP Scraper
무료 DuckDuckGo SERP Scraper는 소규모로 검색 결과 데이터를 수집하기 위한 간단한 방법을 제공합니다. プロキシ를 관리하거나 대량 처리를 다루는 부담 없이 제한된 데이터가 필요할 때 적합합니다.

<img width="800" alt="free-duckduckgo-serp-scraper" src="https://github.com/bright-kr/duckduckgo-api/blob/main/images/428465443-0472593e-615c-4723-96e7-08f83cb0b477.png" />

### Setup Requirements

- **Python 3.9+** – [Download Python](https://www.python.org/downloads/)
- **필수 패키지:**
    - `selenium` (브라우저 자동화용)
    - `webdriver-manager` (브라우저 드라이버 관리용)
    - `beautifulsoup4` (HTML 파싱용)

다음 명령으로 패키지를 설치합니다:
```bash
pip install selenium webdriver-manager beautifulsoup4
```

> **Webスクレイピング이 처음이신가요?** <br>
우리의 [Beginner’s Guide to Web Scraping with Python](https://brightdata.co.kr/blog/how-tos/web-scraping-with-python)으로 여정을 시작해 보십시오. 이후 [Using Selenium for Web Scraping](https://brightdata.co.kr/blog/how-tos/using-selenium-for-web-scraping) 튜토리얼로 한 단계 더 나아가고, 이미 Selenium에 익숙하시다면 고급 [SeleniumBase guide](https://brightdata.co.kr/blog/web-data/web-scraping-with-seleniumbase)로 역량을 더 확장해 보십시오.
>

### Quick Start Guide

1. [duckduckgo-serp-scraper.py](https://github.com/triposat/DuckDuckGo-Search-Scraper/blob/main/duckduckgo-serp-scraper/duckduckgo-serp-scraper.py) 파일을 엽니다.
2. 필요에 따라 검색어를 사용자 지정합니다:
    
    ```python
    SEARCH_TERMS = [
        "ergonomic office chair",
        "coffee maker",
    ]
    ```
    
3. 스크립트를 실행하여 スクレイピング을 시작합니다.

### Sample Output
아래는 스크레이퍼 출력의 미리보기입니다:

<img width="800" alt="free-duckduckgo-serp-scraper-output" src="https://github.com/bright-kr/duckduckgo-api/blob/main/images/428465286-d6891a93-2b5f-4243-8a17-e2a037c91570.png" />


### Limitations

무료 스크레이퍼는 기본 작업에 매우 유용하지만, 다음과 같은 중요한 제한 사항이 있음을 유의하십시오:

- 자주 사용할 경우 IPアドレス 차단 위험이 높습니다
- リクエスト 볼륨 처리 용량이 제한적입니다
- CAPTCHA 중단이 자주 발생합니다
- 프로덕션 환경에 적합하지 않습니다

확장 가능하고 안정적인 솔루션을 원하신다면, 아래에 상세히 설명된 Bright Data의 전용 API를 고려해 보십시오 👇

## DuckDuckGo SERP API

DuckDuckGo SERP API는 Bright Data의 포괄적인 [SERP Scraper API](https://brightdata.co.kr/products/serp-api) 제품군의 일부입니다. 업계 최고 수준의 [DuckDuckGo proxy infrastructure](https://brightdata.co.kr/solutions/duckduckgo-proxies)를 활용하여 단일 API 호출로 실시간 DuckDuckGo 검색 결과를 제공합니다.

### Key Benefits

- **글로벌 정확도**: 전 세계 특정 위치에 맞춘 결과를 प्राप्त할 수 있습니다.
- **Pay-Per-Success**: 성공한 リクエスト에 대해서만 비용을 지불합니다.
- **실시간 데이터**: 최신 검색 결과를 수초 내로 액세스할 수 있습니다.
- **무제한 확장성**: 대량 スクレイピング을 손쉽게 처리합니다.
- **비용 효율성**: 고가의 인프라가 필요하지 않습니다.
- **신뢰할 수 있는 성능**: 고급 안티-차단 기술로 일관된 결과를 보장합니다.
- **24/7 전문가 지원**: 필요할 때 언제든 지원을 받을 수 있습니다.

📌 구매 전 사용해 보기: [SERP API Live Demo](https://brightdata.co.kr/products/serp-api/duckduckgo-search)로 솔루션을 경험해 보십시오.

<img width="800" alt="bright-data-serp-api-playground" src="https://github.com/bright-kr/duckduckgo-api/blob/main/images/428471522-fc60e165-e4db-41d2-93eb-2b6a01398353.png" />

### Getting Started

1. [Bright Data account를 생성합니다](https://brightdata.co.kr/) (신규 사용자는 $5 크레딧을 받습니다).
2. [API key](https://docs.brightdata.com/general/account/api-token)를 생성합니다.
3. [단계별 구성 가이드](https://github.com/triposat/DuckDuckGo-Search-Scraper/blob/main/setup-serp-api.md)를 따라 SERP API를 통합합니다.

## Implementation Methods

다음 두 가지 접근 방식 중 하나로 DuckDuckGo SERP API를 워크플로에 통합할 수 있습니다:

### Direct API Access

Bright Data의 API 엔드포인트로 직접 リクエスト를 전송합니다.

#### cURL Example

```bash
curl https://api.brightdata.com/request \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer API_TOKEN" \
  -d '{
        "zone": "ZONE_NAME",
        "url": "https://duckduckgo.com/?q=budget+laptops+under+500+gbp&kl=uk-en&kad=en-gb&df=w",
        "format": "raw"
      }'
```

#### Python Example

```python
import requests

url = "https://api.brightdata.com/request"

headers = {
    "Content-Type": "application/json",
    "Authorization": "Bearer API_TOKEN"
}

payload = {
    "zone": "ZONE_NAME",
    "url": "https://duckduckgo.com/?q=budget+laptops+under+500+gbp&kl=uk-en&kad=en-gb&df=w",
    "format": "raw",
}

response = requests.post(url, headers=headers, json=payload)

with open("duckduckgo-scraper-api-result.html", "w", encoding="utf-8") as file:
    file.write(response.text)

print("Response saved!")
```

### Native Proxy-Based Access

프로キ시 라우팅을 사용하여 검색 결과에 직접 액세스합니다.

#### cURL Example

```bash
curl -i \
  --proxy brd.superproxy.io:33335 \
  --proxy-user brd-customer-<CUSTOMER_ID>-zone-<ZONE_NAME>:<ZONE_PASSWORD> \
  -k \
  "https://duckduckgo.com/?q=budget+laptops+under+500+gbp&kl=uk-en&kad=en-gb&df=w"
```

#### Python Example

```python
import requests
import urllib3

urllib3.disable_warnings(urllib3.exceptions.InsecureRequestWarning)

host = "brd.superproxy.io"
port = 33335
username = "brd-customer-<CUSTOMER_ID>-zone-<ZONE_NAME>"
password = "<ZONE_PASSWORD>"
proxy_url = f"http://{username}:{password}@{host}:{port}"

proxies = {
    "http": proxy_url,
    "https": proxy_url
}

url = "https://duckduckgo.com/?q=budget+laptops+under+500+gbp&kl=uk-en&kad=en-gb&df=w"
response = requests.get(url, proxies=proxies, verify=False)

with open("duckduckgo-scraper-api-result.html", "w", encoding="utf-8") as file:
    file.write(response.text)

print("Response saved!")
```

> 참고: 네이티브 プロキシ 접근 방식을 프로덕션에서 사용하려면 Bright Data의 SSL 인증서 설치를 권장합니다. 자세한 내용은 [SSL Certificate Guide](https://docs.brightdata.com/general/account/ssl-certificate)를 참조하십시오.
> 

👉 HTML 출력의 전체 미리보기를 보려면 [complete result](https://github.com/triposat/DuckDuckGo-Search-Scraper/blob/main/duckduckgo-scraper-api-output/duckduckgo-scraper-api-result.html)를 확인하십시오.


## DuckDuckGo Search Query Parameters

다양한 쿼리 파라미터를 사용하여 검색 결과를 미세 조정할 수 있습니다.

### Localization

#### Country and Language (`kl`)

검색 결과의 국가 및 언어를 지정합니다.

*Example:*

```bash
curl --proxy brd.superproxy.io:33335 \
     --proxy-user brd-customer-<id>-zone-<zone>:<password> \
     "https://duckduckgo.com/?q=best+coffee+brands&kl=it-it"
```

이는 이탈리아에 맞춤화된 검색 결과를 반환합니다.

#### Interface Language (`kad`)

DuckDuckGo 인터페이스의 언어를 제어합니다.

*Example:*

```bash
https://duckduckgo.com/?q=photo+editing+tools&kad=de
```

이는 검색 콘텐츠는 영어로 유지하면서, 인터페이스는 독일어로 표시합니다.

### Safe Search Configuration (`kp`)

성인 콘텐츠에 대한 필터링을 조정합니다.

#### Values

- `1` – 엄격한 Safe Search
- `-1` – 보통
- `-2` – 끔

*Example:*

```bash
https://duckduckgo.com/?q=swimsuit&kp=1
```

*"swimsuit”.*에 대해 가족 친화적인 결과만 반환합니다.

### Time Range Filtering (`df`)

검색 결과를 특정 기간으로 제한합니다.

#### Values

- `d` – 지난 하루
- `w` – 지난 1주
- `m` – 지난 1개월
- `y` – 지난 1년
- *사용자 지정 범위:* 예: `2025-03-01..2025-03-10`

*Example:*

```bash
https://duckduckgo.com/?q=iphone+15+review&df=w
```

최근 리뷰(지난 1주 이내)만 표시합니다.

### Device Targeting (`brd_mobile`)

다양한 디바이스 유형에서의 검색을 시뮬레이션합니다.

#### Options

- `0` – 데스크톱(기본값)
- `1` – 랜덤 모바일 디바이스
- `ios` 또는 `iphone` – iPhone
- `ipad` 또는 `ios_tablet` – iPad
- `android` – Android 휴대폰
- `android_tablet` – Android 태블릿

 *Example:*

```bash
https://duckduckgo.com/?q=top+travel+apps&brd_mobile=ios
```

이는 iPhone 사용자를 시뮬레이션합니다. App Store 링크, 모바일 중심 콘텐츠 또는 AMP 페이지가 표시될 수 있습니다.

### Browser Emulation (`brd_browser`)

리クエスト에 사용할 브라우저의 user-agent를 지정합니다.

#### Options

- Default (랜덤 브라우저)
- `chrome` – Google Chrome
- `safari` – Safari
- `firefox` – Mozilla Firefox *( `brd_mobile=1` 와 호환되지 않습니다)*

*Example:*

```bash
https://duckduckgo.com/?q=best+vpn+services&brd_browser=safari
```
이는 Safari 브라우저를 시뮬레이션하여 해당 플랫폼에서 콘텐츠가 어떻게 표시되고 랭킹되는지에 대한 인사이트를 제공합니다.

## Practical Example

영국에서 모바일 사용자를 타겟으로 *"budget laptops under £500"*에 대한 경쟁사의 가격 페이지를 모니터링하고 있다고 가정합니다.

목표는 다음과 같습니다:

- 영국 기반 모바일 사용자를 시뮬레이션합니다
- 로컬라이즈된 영어 결과(영국 특정 리테일러, 통화)를 प्राप्त합니다
- 모바일 Chrome user agent를 사용합니다(AMP 페이지 등 모바일 전용 결과를 포착하기 위해)
- 최신 제품 리스트형 글 또는 딜에 집중합니다

이 요구 사항을 단일 cURL 명령으로 결합합니다:

```bash
curl --proxy brd.superproxy.io:33335 \
     --proxy-user brd-customer-<CUSTOMER_ID>-zone-<ZONE_NAME>:<ZONE_PASSWORD> \
     "https://duckduckgo.com/?\
q=budget+laptops+under+500+gbp&\
kl=uk-en&\
kad=en-gb&\
df=w&\
brd_mobile=android&\
brd_browser=chrome"
```
🎯 이는 **모바일 우선**, **로컬라이즈됨**, **최신** 콘텐츠를 가져옵니다.

## Support & Resources

- **문서:** [SERP API Documentation](https://docs.brightdata.com/scraping-automation/serp-api/)
- **관련 API:**
    - [SERP API](https://github.com/bright-kr/serp-api)
    - [Google Search API](https://github.com/bright-kr/google-search-api)
    - [Google News Scraper](https://github.com/bright-kr/Google-News-Scraper)
    - [Google Trends API](https://github.com/bright-kr/google-trends-api)
    - [Google Reviews API](https://github.com/bright-kr/google-reviews-api)
    - [Google Hotels API](https://github.com/bright-kr/google-hotels-api)
    - [Google Flights API](https://github.com/bright-kr/google-flights-api)
    - [Web Unlocker API](https://github.com/bright-kr/web-unlocker-api)
- **사용 사례:**
    - [SEO & SERP Tracking](https://brightdata.co.kr/use-cases/serp-tracking)
    - [Travel Industry Data](https://brightdata.co.kr/use-cases/travel)
- **추가 읽을거리:** [Best SERP APIs](https://brightdata.co.kr/blog/web-data/best-serp-apis)
- **지원 문의:** [support@brightdata.com](mailto:support@brightdata.com)