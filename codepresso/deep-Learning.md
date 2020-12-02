# Deep Learning

### 딥러닝 개요

컴퓨터들이 인간의 두뇌와 비슷한 모양의 대형 인공 신경망을 형성하는 일종의 기계학습

인공신경망은 인간의 뉴런 구조를 본떠 만든 머신러닝 모델의 일종



#### 인공신경망(Artificial Neural Network)

- 생물의 뇌를 수학적으로 모델링 할 수 있을 것이라는 아이디어에서 시작
- 인간의 뇌를 스위치들이 복잡하게 연결된 네트워크로 표현할 수 있다고 생각



#### 퍼셉트론(Perceptron)

- 뇌의 기본 단위인 뉴런을 수학적으로 모델링

- 입력 신호에 따라 0 또는 1 값을 출력하는 모델

- 선형 분류기 ( y = ax + b )

  - 선형 분류기는 XOR 연산을 하지 못한다

  | 사람의 뇌          | 인공신경망           |
  | ------------------ | -------------------- |
  | 뉴런들의 다층 연결 | 퍼셉트론의 다층 연결 |



인공신경망을 많은 층으로 깊게 쌓은 모델이 DNN(Deep Neural Network)

DNN 모델을 마케팅 용어로 만든 것이 **\"Deep Learning\"**



- **머신러닝** : `데이터`  ➡ `Feature Engineering` ➡ `머신러닝 알고리즘` ➡ `결과`

- **딥러닝** : `데이터` ➡ `딥러닝 알고리즘` ➡  `결과` (효율적)



---



#### Deep Learning의 핵심 개념

- 인공신경망(Neural Network)
- 인공신경망 내 데이터 흐름
- 깊은 층 (Deep Layer)
- 비선형성(Non-Linearity)
- 최적화(Optimization)
- 딥러닝 모델의 공간적 의미



##### 인공신경망

- 단일 뉴런을 여러 층으로 쌓아서 만든 모델

##### 퍼셉트론

다수의 입력신호(input)을 받아서 하나의 신호(output)를 출력

- 가중치[W] : 입력신호가 분석 결과에 미치는 중요도 조절

- 활성화 함수[f(x)] : 입력 신호의 총합을 확인해 출력 신호를 결정하는 함수

  <img src="img\perceptron.jpg" style="zoom:40%;" alt="https://deepai.org/machine-learning-glossary-and-terms/perceptron"/>



##### 깊은 층

- **층을 깊게 할 수록** 더 복잡한 문제에 대해서 대응 가능
- 이전층에서 학습한 특징을 조합하여 더 높은 차원의 문제에 대응



##### 딥러닝 응용기술

- CNN, RNN, GAN, Reinforcement Learning



### 활성화 함수(Activation Function)

- Threshold(임계 값)을 경계로 출력 값을 변경하는 함수
- Perceptron은 Activation Function으로 Step Function(계단 함수 : 0보다 작으면 0, 크면 1) 사용
- **Sigmoid 함수** : 뉴럴 네트워크에서 자주 사용되는 활성화 함수

> ##### Step vs Sigmoid
>
> 공통점
>
> - 0~1사이의 값을 반환
> - 입력이 중요하면 큰 값을, 중요하지 않으면 작은 값을 출력
> - 비선형함수 <u>???</u>
>
> 차이점
>
> - 

- **\* ReLU \* **
  - 최근에 가장많이 사용하는 활성화 함수
  - 입력이 0 초과이면 입력을 그대로 반환
  - 0 이하이면 0을 반환
- **Softmax**





#### Matrix Dot Product

- 행렬의 연산 중 하나로 **행렬의 곱셈**

- 피연산자 행렬들의 크기가 중요

- 딥러닝에서 빈번하게 사용되는 연산 기법

  <img src="C:\Users\kbeey\Documents\workspace-git\machine-learning\codepresso\img\matrix.png" style="zoom:70%;" alt="https://www.javatpoint.com/matrix-multiplication"/>

---



### Keras

파이썬으로 작성된 오픈 소스 신경망 라이브러리

직관적인 추상화 API를 통해 딥러닝 모델을 쉽게 만들 수 있음

NXNet, Deeplearning4j, tensorflow, CNTK, Theano 등 다양한 프레임워크 위에서 수행

동일한 코드로 CPU, GPU에서 실행 가능





##### 텐서 (Tensor)

- 머신 러닝의 기본 구성 요소
- 숫자 데이터를 위한 컨테이너
- 임의의 차원 개수를 가짐
- 텐서에서의 차원을 축이라고 부름
- **핵심 속성**
  - 개수 
  - 크기 
  - 데이터 타입



##### Keras 작업 흐름

- 입력 텐서와 타깃 텐서로 이루어진 훈련 데이터를 정의
- 입력과 타깃을 매핑하는 층으로 이루어진 네트워크(모델)을 정의
- 손실 함수, 옵티마이저, 모니터링을 위한 성능 지표 선택
- 훈력 데이터에 대해 모델의 fit() 메서드를 실행





순서

1. 데이터셋 준비

   - train/test 데이터 분리
   - feature, class 정의

2. 데이터 전처리

   - DNN 모델에 입력 가능한 형태로 Input Tensor의 shape 변환
   - reshape() 함수 사용해서 flatten하게 변환

3. DNN(MLP) 모델 디자인

   - Dense : 조밀하게 모여 있는 집합
   - Dense 층을 쌓을 때 중요한 결정사항
     - 얼마나 많은 층을 사용할 것인가
     - 각 층에 얼마나 많은 은닉 유닛(퍼셉트론)을 둘것인가
     - 출력층 설계

4. 모델 학습 정보 설정

   - optimizer : 오차를 기반으로 weight와 bias를 효율적으로 업데이트하는 함수 지정
   - loss : 오차 값을 측정하는 손실 함수 지정
   - metrics : 모델의 목표, 무엇을 측정할 것인지

5. 모델에 데이터 연결 및 학습

   - model.fit()을 이용하여 데이터 연결 및 학습
   - validation dataset은 20% 지정하여 epoch마다 성능 검증

6. 학습 과정 시각화

7. 테스트 데이터 셋을 통한 모델의 성능 평가

   - model.evaluate() 을 이용하여 성능 평가
   - 모델의 성능 평가를 학습 전 검증 데이터를 훈련 데이터와 분리
     - 학습에 사용된 훈련 데이터 셋이 검증 데이터를 포함될 경우 모델 성능 평가 왜곡

8. 학습된 모델을 이용한 예측

   - model.predict를 이용한 모델 예측

   



















