# READ ME  

## 1. Project 소개

![28조](C:/Users/DoGeun/Desktop/project/bigdata-sub2/assets/28%EC%A1%B0.gif)

- 본 프로젝트는 4인 프로젝트로 다양한 기준으로 세권 분석을 통한 동네 추천 시스템을 구현한 웹 페이지 입니다.
- 클러스러링 알고리즘(Kmeans, Hierarchical, EM)과 sparse matrix를 사용하여 데이터를 빠르게 전처리 하여 사용자가 편리하게 동네 검색을 할 수 있게 구현했습니다.
- Javascript와 Vue를 사용하여 Front를 구성하고 상태관리를 하였습니다.
- 곽동령 : 팀장, 프론트엔드, Javascript, Html, CSS
- 안도건 : 백엔드, 데이터크롤링, Python, Django 
- 박병준 : 백엔드, MapApi 요청
- 송건호 : 백엔드, AWS 서버 연동



## 2. Project setup

1. 파이썬 및 pip 설치

   - https://www.python.orf/downlodas 에서 설치
   - 운영 체제에 맞는 최선 버전의 파이썬 설치

2. Node.js 설치

   - https://nodejs.orf/en/download
   - 운영 체제에 맞는 최선 버전의 Node.js 설치

3. Backend 설치

   - /backend 디렉토리 진입 후 다음 커멘드 순차적으로 진행

   ```
   pip install -r requirements.txt
   python manage.py makemigrations
   python manage.py migrate
   ```

   - backend 서버 실행

   ```
   python manage.py runserver
   ```

4. Frontend 설치

   - /frontend 디렉토리 진입 후 다음 커멘드 순차적으로 진행

   ```
   npm install
   ```

   - frontend 서버 실행

   ```
   npm run serve
   ```

5. Django admin 계정 생성

   - /backend 디렉토리 진입 후

   ```
   python manage.py shell < create_admin.txt
   ```



## 3. 사용프로그램

- Pycharm
- Python
- Django
- Vue.js
- vuetity
- vue + vuex
- jira
- git





## 4. 주요 Component

```
backend
├── api
│   ├── __pycache__
│   └── migrations
│      └── 0001_initial.py
│   └── admin.py
│   └── apps.py
│   └── models.py
│   └── serializers.py
│   └── tests.py
│   └── urls.py
│   └── views.py
├── backend
│   └── settings.py
│   └── urls.py
├── yogeuncheo
│   └── api
│      └── serializers.py
│
├── db.sqlite3
└── manage.py

data
├── data_adg
├── data_gdr
├── data_nenemttin
└── data_sgh

frontend
├── public
│   └── index.html
├── src
│   └── api
│      └── index.js
│   └── assets
│   └── components
│      └── pages
│         └── MapPage.vue
│         └── YoGeunCheoPage.vue
│      └── ModalForm.vue
│      └── RoomRecommendList.vue
│      └── SearchForm.vue
│   └── plugins
│      └── vuetify.js
│   └── router
│      └── index.js
│   └── store
│      └── modules
│         └── data.js
│      └── index.js
│   └── App.vue
│   └── main.js
└── REAME.md
```



| 단계 |       Component       |                         description                          |
| :--: | :-------------------: | :----------------------------------------------------------: |
|  00  |        App.vue        |                     Vue 최상단 인스턴스                      |
|  01  |  YoGeunCheoPage.vue   |           사용자가 검색을 시작할 수 있는 홈페이지            |
|  02  |      MapPage.vue      |       사용자에게 세권분석을 통한 동네 추천과 지도 표시       |
|  03  |     ModalForm.vue     | 편의시설, 공원 분포, 학교 비율, 범죄율 등의 빅데이터를 표준 지수로 변환해 정보를 제공하는 Modal Form |
|  04  | RoomRecommendList.vue |    트위터 크롤링 데이터를 이용해 가장 많이 찾는 동네 추천    |
|  05  |    SearchForm.vue     |             동네 검색을 시작할 수 있는 인스턴스              |
|  06  |         data/         |    api요청을 통한 data를 서버 업로딩을 위한 csv 디렉토리     |




## 5. 사이트 화면

#### 1) homepage('/')

- 사용자 진화적인 ui를 통해 쉽고 간편하게 동네 검색을 할 수 있게 제작했습니다. 
- 동네를 입력하면 동네의 편의지수 점수, 범죄율, 물가 정보가 Modal Form으로 표시됩니다.
- 트위터 크롤링 데이터를 이용해 가장 많이 언급된 동네를 추천합니다.
- 카드를 클릭하면 네이버 검색 페이지로 이동합니다.

![홈](C:/Users/DoGeun/Desktop/project/bigdata-sub2/assets/%ED%99%88.PNG)



#### 2) homepage에서 search 버튼 -> 해당 동네의 편의지수, 치안, 물가 정보 등 생성

- 편의지수, 숲세권, 교육지수, 물가지수, 범죄지수 등의 정보를 데이터화하여 제공합니다.
- 자세히 보러 가기 클릭시 해당 동네의 상세한 정보로 이동합니다.

![22](C:/Users/DoGeun/Desktop/project/bigdata-sub2/assets/22.PNG)



#### 3) 상세한 동네 정보와 유사한 동네 추천 시스템

- 해당 페이지는 Scikit-learn 빅데이터 알고리즘을 이용해 사용자가 검색한 동네와 유사한 동네를 추천하는 시스템을 제공합니다. 

![33](C:/Users/DoGeun/Desktop/project/bigdata-sub2/assets/33.PNG)