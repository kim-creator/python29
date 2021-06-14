평가 지표 만들기

MSE(Mean Squared Error)

MSE=1n∑i=1n(y^i−ti)2

예측값(y^)과 실제값(t)의 차이에 대한 제곱에 대하여 평균을 낸 값

MAE(Mean Absolute Error)

MAE=1n∑i=1n|y^i−ti|

예측값(y^)과 실제값(t)의 차이에 대한 절대값에 대하여 평균을 낸 값

RMSE(Root Mean Squared Error)

RMSE=1n∑i=1n(y^i−ti)2−−−−−−−−−−−−√

MSE에 root 를 씌운 값으로써 실제 오차의 평균이라고 봐도 무방

LinearRegression의 수식

기울기(W), 편향(b)

기울기는 다른말로 가중치(Weights)라고 한다.

가중치의 의미

입력되고 있는 데이터(x)들의 각각의 중요도를 판단 하는 것

어떠한 중요도? : 예측값(y^)에 얼마나 많이 영향을 끼칠 것인가

가중치의 절대값이 커지면 예측값에 영향을 많이 미친다.

모델이 복잡해 진다.

가중치의 절대값이 작아지면 예측값에 영향을 덜 미친다.

모델이 단순해 진다.

LinearRegression은 가중치를 조절할 방법이 없습니다.

규제(α - Regularization)를 사용하는 모델을 사용해서 가중치를 조절

α : penalty부여 매개변수 ( 또는 람다(λ) )

규제 방식

L2 규제(L2 Regularization)

각 가중치 제곱의 합에 규제 강도인 (α)를 곱하여 오차에 더한다.

α를 크게 하면 가중치가 더 많이 감소 (규제를 더 중요하게 생각하겠다.)

α를 작게 하면 가중치가 증가한다.( 규제를 중요하게 생각하지 않음 )

L1 규제(L1 Regularization)

가중치의 합을 더한 값에 규제 강도인 (α)를 곱하여 오차에 더한다.

어떤 가중치는 실제 0이 되어버린다. 즉, 모델에서 완전히 제외되는 특성이 생긴다.

모델이 특성을 선택

L2 규제가 L1규제에 비해 안정적이라 일반적으로는 L2규제가 더 많이 사용된다.

릿지(Ridge) - L2 규제

E=MSE+α∑w2

라쏘(Lasso) - L1 규제

E=MSE+α∑|w|

ElasticNet

Ridge와 Lasso의 규제 방식을 같이 사용

l1_ratio ( default = 0.5 )

l1_ratio = 0 ( L2 만 사용 )

l1_ratio = 1 ( L1 만 사용 )

0 < l1_ratio < 1 ( L1과 L2의 혼합사용)

StandardScaler(표준화)

평균을 0, 표준편차를 1로 만들어주는 스케일러

MinMaxSclaer (정규화)

최소값을 0으로, 최대값을 1로 정규화

RobustScaler

중앙값을 0으로 만든다.

IQR(Inter Quantile Range)을 1로 변환
