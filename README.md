# BERTSUM을 활용한 뉴스 추출 요약 웹

## 프로젝트 소개
네이버 뉴스 카테고리 중 3개의 카테고리 정치, 뉴스, 경제의 헤드라인 뉴스 중 중복된 내용을 제외한 중요한 뉴스를 선정하여 3-5줄로 요약하여<br>
다양한 시각 정보들과 함께 보여줍니다.<br>

## 프로젝트 기술 소개
 - Tockenizer : sentencepiece
 - BERT model : BERT를 직접 modeling/pretrain/finetune 진행
 - BERTSUM model : BERT기반 추출 요약 모델인 BERTSUM modeling/finetune 진행 및 rouge 지표 확인
 - 크롤링 라이브러리 : BeautifulSoup4 / Selenium
 - 시각화 라이브러리 : matplotlib / wordcloud /networkX
 - 웹 : django / bootstrap
 - db : mysql

## 사용 데이터
 - pretrain : KoWiki, 모두의 말뭉치(2.23gb)
 - finetune : AI Hub (문서요약 텍스트 중 신문기사)
 - crawling : 네이버 뉴스 (정치,경제,사회)

## 개발 기간
 - 22.03 - 22.09

## 구성원
 - 김지성

## 사용 언어
 - python

## 프로젝트 결과
### model size
|model|size|
|:------:|:-----:|
|**layer**|**6**|
|**hidden layer**|**512**|
|**feed forward**|**1024**|
|**attention layer**|**6**|
|vocab|32000|
|sequence|512|
|segment type|2|
|multihead attention|6|
|dropout|6|
|layer norm|1e-12|
 - BERT base의 파라미터 수는 110M 정도의 수치이지만 개인적으로 만든 모델의 파라미터 수는 약 18M 정도이다.
 - layer, hidden layer, feed forward, attention layer 가 기존 BERT base보다 작다.
 - 다양한 모델의 사이즈들을 만들어 직접 비교하였으나 개인 pc 기준 가장 최적의 모델이라고 생각되어지는 사이즈를 채택하였다.
![그림1](https://github.com/intelligence-kim/BERTSUM/assets/128572870/da83b9bc-d3f8-4d4a-b8e8-2980e0890a4a)

