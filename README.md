# BERTSUM을 활용한 뉴스 추출 요약 웹

## 프로젝트 소개
네이버 뉴스 카테고리 중 3개의 카테고리 정치, 뉴스, 경제의 헤드라인 뉴스 중 중복된 내용을 제외한 중요한 뉴스를 선정하여 3-5줄로 요약하여<br>
다양한 시각 정보들과 함께 보여줍니다.<br>

## 프로젝트 기술 소개
 - Tockenizer : sentencepiece
 - BERT : BERT를 직접 modeling/pretrain/finetune 진행
 - BERTSUM : BERT기반 추출 요약 모델인 BERTSUM modeling/finetune 진행 및 rouge 지표 확인
 - 크롤링 라이브러리 : BeautifulSoup4, Selenium
 - 시각화 라이브러리 : matplotlib, wordcloud, networkX
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
 - [BERT](https://arxiv.org/pdf/1810.04805.pdf)<br>
 - [BERTSUM](https://arxiv.org/abs/1908.08345)<br>
 
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
 - 다양한 모델의 사이즈들을 만들어 직접 비교하였으나 개인pc에서 학습 가능한 가장 최적의 모델을 채택하였다.
![그림1](https://github.com/intelligence-kim/BERTSUM/assets/128572870/da83b9bc-d3f8-4d4a-b8e8-2980e0890a4a)

### model 성능
NSMC : 0.85
rouge-1 : 0.38
rouge-2 = 0.34
rouge-l = 0.36

### EDA
<img width="416" alt="image" src="https://github.com/intelligence-kim/BERTSUM/assets/128572870/923194b1-75b2-43e0-95bd-bf93baeafd11">
 - AI Hub에서 제공해준 추출 요약된 라벨링의 출현 빈도 그래프이다.
 - 그래프를 보면 대체적으로 라벨링된 데이터의 앞 부분이 중요도가 높은 것을 볼 수 있다.
ex) sentence_1,sentence_2,sentence_3,sentence_4,sentence_5 -> 추출요약 결과 : 1,2,3

### 크롤링
 1. 카테고리별 헤드라인 뉴스 DataFrame 변환
 2. DataFrame->DB 저장

### Web
 1. 첫화면
<img width="1276" alt="1" src="https://github.com/intelligence-kim/BERTSUM/assets/128572870/25b0b2c5-1383-46df-b6b4-85d71c4d6760">
 2. News 시각화 자료
<img width="1578" alt="2" src="https://github.com/intelligence-kim/BERTSUM/assets/128572870/aac51787-6d18-4112-870f-833ae91a909c">
 3. News 요약 본문
<img width="940" alt="3" src="https://github.com/intelligence-kim/BERTSUM/assets/128572870/e2303789-0914-4781-8bb4-6a10108ac853">
 4. 전체 뉴스 요약

![4](https://github.com/intelligence-kim/BERTSUM/assets/128572870/8a7a5816-fd31-4f27-bc7b-7cd04b56a4d9)




