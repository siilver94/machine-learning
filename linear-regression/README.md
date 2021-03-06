# 선형 회귀(Linear Regression) 

변수 사이의 선형적인 관계를 모델링 한 것 -&gt; 직선적이다.

ex)나는 사업가다.
열심히 일할수록 많은 돈을 얻을 것이다.
하루에 일 하는 시간과 매출은 서로 어떤 관계를 가질까?

하루 업무 시간 하루 매출

- 1시간 : 30,000원

- 2시간 : 60,000원

- 3시간 : 80,000원

- 4시간 : 115,000원

- 5시간 : 132,000원

- 6시간 : 160,000원

- 7시간 : 185,000원

- 8시간 : ?

**사업가의 업무 시간과 매출 데이터**

![Untitled](https://user-images.githubusercontent.com/57824945/77068241-9a1cbf00-6a29-11ea-8b29-7f052a4d9008.png)
데이터는 **직선**으로 표현할 수 있는 선형적인 성향을 가집니다.

일상 생활의 많은 현상들은 선형적인 성격을 가집니다.

**이러한 선형적인 관계에 적용하는 대표적인 기계 학습 이론이 선형회귀입니다.**

## 선형 회귀 모델 구축

주어진 데이터를 학습시켜서 가장 합리적인 ‘직선=식’을 찾아낸다.

따라서 데이터는 **3개 이상일 때 의미가 있습니다.**
![Untitledd](https://user-images.githubusercontent.com/57824945/77068364-cd5f4e00-6a29-11ea-9c3f-9ba720eea69d.png)

3개의 직선중 가장 합리적인 선은?
(데이터들과 가장 근접해잇는 중간이가장 합리적인 직선)

**선형회귀는 가장 합리적인 직선을 찾는것**

### 가설

H(x) = Wx+b
H = Hypothesis(가설)
- 하나의 일차 방정식을 이용해 직선을 표현합니다.
- 가설을 수정해 나가면서 ‘그나마’ 가장 합리적인 식을 찾아냅니다.

- 즉 선형 회귀란 주어진 데이터를 이용해 일차방정식을 수정해나가는 것!
학습을 거쳐서 가장 합리적인 선을 찾아내는 것입니다.
학습을 많이 해도 ‘완벽한’ 식을 찾아내지 못할 수 있습니다.
하지만 실제 사례에서는 근사값을 찾는 것 만으로도 충분할 때가 많습니다.
**알파고** 도 결과적으로는 ‘근사값’을 가정하는 프로그램에 불과합니다.
![aa](https://user-images.githubusercontent.com/57824945/77068428-f1bb2a80-6a29-11ea-9126-a84e76f62e5f.png)

원래 데이터와 먼 데이터가 있다고 가정햇을 때, 계속해서 점프(jump)를 하면 실제 데이터와 근사한 직선 발견.

## 선형회귀 실제 기계학습 적용

**비용(cost)** : 가설이 얼마나 정확한지 판단하는 기준.

![ba](https://user-images.githubusercontent.com/57824945/77068483-0dbecc00-6a2a-11ea-80d2-ff1164c33b35.png)

 ## 경사 하강(Gradietn Descent)
 
경사 하강을 이용해 합리적인 식을 도출합니다.
H(x) = Wx 로 식을 간단히 합니다.

따라서 비용 함수는 pow(Wx - y , 2)를 따릅니다.

![ca](https://user-images.githubusercontent.com/57824945/77068598-3e9f0100-6a2a-11ea-8a2e-cb896724b859.png)

계속 경사를 타고 아래로 내려가다보면(jump) 제일 하단 으로 내려가게 되는데,

![da](https://user-images.githubusercontent.com/57824945/77068605-3f379780-6a2a-11ea-90b8-8d2752c3b414.png)

**기울기를 구하기위해 사용하는 개념**
가장 골짜기, 즉 꼭지점은 기울기는 0.

- 수평이 될수 잇게 오는것이 제일 좋은 식을 세운것.
- 최대한 수평이 될 수 있게 좋은 식을 찾는것이 핵심적인 개념.
- **핵심 점프! 얼마나 뛰어야하나?(중요)**
- 곡선의 특성상 초반에 많은 폭으로 변화합니다.
- 너무 작게 점프하면 오랫동안 학습해야 합니다.
- 너무 크게 점프하면 학습 결과가 부정확할 수 있습니다.

- Tensorflow 는 경사 하강 라이브러리를 제공 합니다.
