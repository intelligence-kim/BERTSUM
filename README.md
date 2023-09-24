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
|vocab|32000|
|sequence|512|
|segment type|2|
|<span style="color:red">**layer**</sapn>|**6**|
|**hidden layer**|**512**|
|**feed forward**|**1024**|
|**attention layer**|**6**|
|multihead attention|6|
|dropout|6|
|layer norm|1e-12|
