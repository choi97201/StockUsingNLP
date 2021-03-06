# Stock Using NLP (자연어 처리를 이용한 주가예측)

## Abstract

#### 종목의 화제성과 등락률

많은 연구들은 언급이 많이되는 주식 종목은 그렇지 않은 종목에 비해 주가가 상승할 확률이 높다고 한다. 일례로, 
Hristidis(2012)는 빅데이터(Big-data)와 주식시장의 상관관계를 파악하려 했다. 약 3억 4천만개의 트위터를분석한 결과 특정 기업에 대해 언급이 많을수록 주가상승확률이 높아짐을 실증분석 하였다. 4개월 동안의 모델 시뮬레이션 결과 빅데이터(Big-data)에 많이 언급된 회사일수록 다우지수와 비교하여 약 2%정도 덜 하락함을 보였다. 또한 기업의 신제품 출시 등의 정보가해당 기업의 주식 거래량에 영향을 미침을 보였다.(이득환 외, 2013)
이 프로젝트에서는 최근 3개월 기준 가장 많이 언급된 종목 10개를 중심으로 기존의 펀드상품과는 차별되는 새로운 투자상품을 개발하려 한다.

#### 한국 주식 투자자의 패턴

주식을 잘 알지 못하는 일반인이더라도, 우리나라의 주식 투자자들은 대부분 장기 투자보다는 단기 매매를 통한 수익 창출을 목적으로 한다는 것을 잘 알고있다. 이 처럼 우리나라의 주식 투자 패턴은 단기 매매, 속된 말로 '단타'에 굳혀져 있는듯 하다. 이 때문에 대부분의 주식 투자자들은 단기간에 수익을 얻는 거래에 익숙해져 있고, 또 그러한 상품을 원한다.

#### 4차 산업 혁명에서 펀드 매니저의 한계

펀드를 '펀드매니저가 운영하는 계모임'이라 일컫는 말이 괜히 나온 것은 아닐 것이다. 이 말의 속 뜻은 투자자들은 잘 알지 못하고, 또 이해하기 어려운 근거 또는 펀드 매니저의 직감에 의존한 종목 선정 및 거래 양상을 비꼬는 말일 것이다. 이 프로젝트에서는 4차 산업 혁명의 분야 중 하나인 인공지능 및 빅데이터를 주식 투자 상품과 접목시키려 한다. 빅데이터를 이용하여 인간의 직감을 배제하고 인간이 미처 발견하지 못한 패턴을 발견하며 분석된 데이터를 시각화하여 이용자들에게 종목 추천의 근거를 쉽게 설명할 수 있다.

## Requirements

python==3.x

pandas

xlrd

finance-datareader

sklearn

matplotlib

numpy

## Data

뉴스데이터: '빅카인즈'에서 주식으로 검색했을 때 19177개의 뉴스데이터 이용

주식데이터: finance-datareader 라이브러리 사용

## Results

전체적인 성능은 좋지 않은편이고, 감성사전을 이용했을 때 성능이 올라가는 경우도 있는 반면 오히려 내려가는 경우도 발생함.

추후 추가 데이터 수집 및 전처리, 예측 모델의 개선, 그리고 현재 휴리스틱한 방법으로 진행했던 자연어처리를 딥러닝과 접목시켜 정확도를 올리는 등과 같은 확장 연구가 필요하다.

</style>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Name</th>
      <th>감성분석</th>
      <th>선형회귀</th>
      <th>선형회귀_감성</th>
      <th>lightgbm</th>
      <th>lightgbm_감성</th>
      <th>XGBOOST</th>
      <th>XGBOOST_감성</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>삼성전자</td>
      <td>0.611111</td>
      <td>0.611111</td>
      <td>0.611111</td>
      <td>0.583333</td>
      <td>0.597222</td>
      <td>0.541667</td>
      <td>0.597222</td>
    </tr>
    <tr>
      <th>1</th>
      <td>현대차</td>
      <td>0.619718</td>
      <td>0.521127</td>
      <td>0.521127</td>
      <td>0.647887</td>
      <td>0.492958</td>
      <td>0.464789</td>
      <td>0.492958</td>
    </tr>
    <tr>
      <th>2</th>
      <td>두산중공업</td>
      <td>0.583333</td>
      <td>0.583333</td>
      <td>0.583333</td>
      <td>0.513889</td>
      <td>0.555556</td>
      <td>0.472222</td>
      <td>0.555556</td>
    </tr>
    <tr>
      <th>3</th>
      <td>SK</td>
      <td>0.666667</td>
      <td>0.652778</td>
      <td>0.666667</td>
      <td>0.527778</td>
      <td>0.652778</td>
      <td>0.569444</td>
      <td>0.680556</td>
    </tr>
    <tr>
      <th>4</th>
      <td>카카오</td>
      <td>0.652778</td>
      <td>0.597222</td>
      <td>0.597222</td>
      <td>0.430556</td>
      <td>0.527778</td>
      <td>0.444444</td>
      <td>0.500000</td>
    </tr>
    <tr>
      <th>5</th>
      <td>키움증권</td>
      <td>0.694444</td>
      <td>0.625000</td>
      <td>0.625000</td>
      <td>0.597222</td>
      <td>0.638889</td>
      <td>0.583333</td>
      <td>0.666667</td>
    </tr>
    <tr>
      <th>6</th>
      <td>현대모비스</td>
      <td>0.611111</td>
      <td>0.583333</td>
      <td>0.583333</td>
      <td>0.583333</td>
      <td>0.541667</td>
      <td>0.513889</td>
      <td>0.541667</td>
    </tr>
    <tr>
      <th>7</th>
      <td>셀트리온</td>
      <td>0.736111</td>
      <td>0.638889</td>
      <td>0.736111</td>
      <td>0.500000</td>
      <td>0.708333</td>
      <td>0.513889</td>
      <td>0.708333</td>
    </tr>
    <tr>
      <th>8</th>
      <td>유안타증권</td>
      <td>0.680556</td>
      <td>0.625000</td>
      <td>0.680556</td>
      <td>0.652778</td>
      <td>0.611111</td>
      <td>0.527778</td>
      <td>0.638889</td>
    </tr>
    <tr>
      <th>9</th>
      <td>KB금융</td>
      <td>0.611111</td>
      <td>0.541667</td>
      <td>0.611111</td>
      <td>0.736111</td>
      <td>0.611111</td>
      <td>0.555556</td>
      <td>0.611111</td>
    </tr>
  </tbody>
</table>

</div>

## 그 외 코드 등은 results/results.md 참고

