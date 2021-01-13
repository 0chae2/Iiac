   
## [Robot navigation in large-scale social maps: An action recognition approach :: Konstantinos Charalampous](https://www.sciencedirect.com/science/article/pii/S0957417416305103)
```
 로봇과 사람이 공간을 공유하고 그 작업공간에 사람과의 활동을 조화롭게 할 수 있도록 만드는 로봇을 제작하는 것이 목표이다. 
 우리는 사람이 있는 환경에서 로봇이 안전한 작업궤도를 만들 수 있다는 것을 증명하였다. 
```
## 목차
1. [Introduction](#Introduction)
2. [Social mapping](#Social mapping)
    2-1. Metric maps and navigation
    2-2. Human detection
    2-3. Action recognition
3. [Robot navigation in human populated environments](Robot-navigation-in-human-populated-environments)
    3-1. planning
    3-2. Socially constrained replanning
    3-3. System integration
4. [Experimental evaluation](#Experimental-evaluation)
5. [Conclusions](#Conclusions)

------------------------------------------------------------------------------------------------------------------------------
####  1. Introduction
- [Rapidly-exploring Random Tree (RRT) algorithm](#RRT)
- [Dynamic Time Warping (DTW) module](#DTW)
- [Cognitive Adaptive Optimization (CAO)](#CAO)
- [human-robot interaction(HRI)](#HRI)
- [Dynamic Bayesian Network (DBN)](#DBN)
- [Extended Social Force Model(ESFM)](#ESFM)
- [Markov Chain Monte Carlo (MCMC)](#MCMC)
- [Hierarchical Temporal Memory (HTM)](#HTM)

  - Mitka, E. , Gasteratos, A. , Kyriakoulis, N. , & Mouroutsos, S. G. (2012). Safety certifica-
tion requirements for domestic robots. Safety Science, 50 (9), 1888–1897 . : 협동로봇 안전측정?
   - Hall, E. T. (1969). The hidden dimension : 1990. Anchor Books New York . : 활동 존...?
   - Argyle, M. (2013). Bodily communication . Routledge .
   - Argyle, M. , & Dean, J. (1965). Eye-contact, distance and affiliation. Sociometry , 289–304

- 이 페이퍼에서는 소셜매핑기능과 로봇의 나머지 작동을 분리하는 대부분의 연구와는 달리 제안된 작업의 통합과 관련하여 연구한다. 본 연구에서는 로봇의 목표위치에 도달하는 동시에 사회적 상호작용을 하며 이동하는 것을 목표로 한다.
- Section 2. 제안된 시스템의 모듈과 맵을 추출하는 방법에 대한 설명
- Section 3. 
------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### 2. Social mapping
      - social mapping framework within an existing robot navigationsystems.
        1) The computation of the metric map of the surroundings offline fashion : 오프라인 지도 만들기?
        2) The detection of humans within the scene : 현장내 인간 감지
        3) the recognition of the actions performed by individuals during the operational phase : 작동 단계 동안 개인이 수행한 행동의 인식
      - 주행 할 수록 metric map이 정확해 진다 따라서 정적 장애물을 모델링하고 생성된 맵은 나중에 robot navigation and localization에 활용될 것이다.
      - robot navigation 은 이전에 구성된 지도를 사용
      - 예를 들어 대화하면서 지나가는 두명 사이에 지나갈까 말까 그런것도 판단을 한다 ~~~htm으로~
      
##### (1) Metric maps and navigation
         - 소셜 맵을 구축하기위한 첫 번째 단계는 로봇이 관리하는 동안 로봇의 환경을 정확하게 모델링하는 것이므로 메트릭 맵이 직접 요구됩니다. 미터법지도의 구성은이 백서의 목표를 벗어 났지만,이 논문은 여기에 거주자와 내비게이션 간의 차이점을 강조하는 채택 된 방법에 대한 세부 정보를 제공하고, 무인 환경을 제오갛ㅂ니다. 
         - RGB-D bashed > 3D metric map 환경을 만드는 것에 따르면 by Learning spatially semantic representations for cognitive robot navigation:: Kostavelis & Gasteratos
         1) SIFT feature detect
         2) 획득한 각각의 point cloud 값을 3D 점에 일치시킵니다.
            강체를 point clouds로 전환 시키기 위하여 SVD와 최적화 문제를 해결합니다. point cloud에서 RANSAC 알고리즘을 사용하여 우세한 평면을 감지하고 반복적으로 ICP를 통해 이를 등록함으로 로봇모션을 대략적으로 추정한 것이다.??
         로봇

##### (2) Human detection
##### (3) Action recognition
    
    
    
#### 3. Robot navigation in human populated environments
##### (1) planning
##### (2) Socially constrained replanning
##### (3) System integration
    
    
    
    
  4. Experimental evaluation
  
  
  
  5. Conclusions
  
  
  
  
  -------------------------------------------------------------------------------------------------
#### 어디에 쓰이는지, 어떤게 개선 된 것인지? 가 중요 한계는 무엇인지?! >> 찾아보면 나오니깐 자세한건 필요할 때 찾아쓰면 되는 것

#### [RRT](https://en.wikipedia.org/wiki/Rapidly-exploring_random_tree)
  - [RRT는 샘플링 기반 경로계획법](https://blog.naver.com/pasus/221982416404)
  - [RRT*](https://blog.naver.com/pasus/221985468898)
  - [video](https://www.youtube.com/watch?v=Ao7p_xiUu4s)
  - 자율차, 로봇, 무인항공기, 우주탐사 등과 같은 분야에서 사용
  - 샘플링 기반 경로계획법 : 형상공간을 격자(grid)로 분활하지 않고, 랜덤하게 샘플점을 여러개 생성하여 점점이 공간을 탐색하여 경로를 찾는 방법
                        격자생성방법으로 탐색이 불가능한 고차원(high dimension) 공간에서 유리함 
                        
#### [DTW](https://medium.com/@Aaron__Kim/dynamic-time-warping-%EB%8F%99%EC%A0%81-%EC%8B%9C%EA%B0%84-%EC%9B%8C%ED%95%91-ac80777f49a)
   - 시계열 데이터 간 비교를 위한 최적의 index 매칭을 추정하는 알고리즘 
   - 그래픽, 비디오, 오디오 분야에서 자주 사용 의료 보행의 유사성, 생체 신호 분석 >> 자동음성 인식기술 분야에서 가장 두각을 나타냄
   - 시계열 데이터 간의 유사한 정도를 알기 위해서 사용
      euclidean distance 대신 DTW 사용하는 경우
      1) time series 길이가 서로 달라서
      2) [어떤 이유로 shift가 발생하였을 때](https://blog.naver.com/PostView.nhn?blogId=plasticcode&logNo=221430090062&parentCategoryNo=&categoryNo=6&viewDate=&isShowPopularPosts=false&from=postView)
   - 일반적인 시계열 분석 like euclidean
      - 장) 계산쉽고, 연산속도 빠름
      - 단) 신호의 떨림과 움직임이 심해질 수록 결과가 어긋나는 현상 발생, 길이가 다른 시계열 분석 불가
   - DTW
      - 장) 서로 다른 길이의 시계열 유사도 분석 가능
            GPS 데이터 등 다차원 시계열 데이터 분석가능
      - 단) 알고리즘 구현 어렵고 연산량 많음
```python
from scipy.spatial.distance import euclidean
A = [1, 3, 5, 7, 6, 8, 9, 10, 8, 7]
B = [1, 2, 6, 5, 7, 8]
print("distance: ", euclidean(A[:len(B)], B))
#distance : 2.64 
# euclidean distance
# p = (p1,p2,,,,p_n), q = (q1,q2,,,,q_n)
# ||p-q|| = sqrt((p-q)*(p-q)) = sqrt(|p|^2+|q|^2-2p*q)
#=======================================================#
!pip install fastdtw 
#https://pypi.org/project/fastdtw/#id2
# FastDTW
from fastdtw import fastdtw
path = fastdtw(A, B)[1]
B_ = []
for i in range(len(A)):
    B_.append(A[path[i][1]])
print("distance: ", euclidean(A, B_))
# distance : 3.1622,,.
#=======================================================#
import numpy as np
from scipy.spatial.distance import euclidean

from fastdtw import fastdtw

x = np.array([[1,1], [2,2], [3,3], [4,4], [5,5]])
y = np.array([[2,2], [3,3], [4,4]])
distance, path = fastdtw(x, y, dist=euclidean)
print(distance)
## 2.828327,...
```
#### [Cognitive Adaptive Optimization (CAO)](https://medium.com/@Aaron__Kim/dynamic-time-warping-%EB%8F%99%EC%A0%81-%EC%8B%9C%EA%B0%84-%EC%9B%8C%ED%95%91-ac80777f49a)
- human-robot interaction(HRI)
- Dynamic Bayesian Network (DBN)
- Extended Social Force Model(ESFM)
- Markov Chain Monte Carlo (MCMC)
- Hierarchical Temporal Memory (HTM)

 
 ##### HTM
  - "Hierarchical Temporal Memory (HTM)은 neocortex의 structural and algorithmic properties를 모방하고자 하는 machine learning 기술이다. neocortex는 영장류의 뇌의 지능적 생각의 중심지이다. High level vision, hearing, touch, movement, language, and planning은 모두 neocortex에서 수행된다. 이러한 수많은 cognitive function을 보고 당신은 아마 각각 specialized neural algorithm을 구현하고 할 수 있을 것이다. 하지만 그렇지 않다. neocortex는 uniform pattern of neural circuitry를 보인다. 이러한 biological evidence는 neocortex가 여러 다른 intelligence function을 가질 수 있는 동일한 알고리즘으로 구현되었음을 알 수 있다." (https://enginius.tistory.com/236)
  
 ##### [LSM(Least Squared Method)](https://darkpgmr.tistory.com/56)
 - 어떤 모델의 파라미터를 구하는 한 방법으로서, 데이터와의 residual^2의 합 또는 평균을 최소화하도록 모델의 파라미터를 구하는 방법
 - residual = 추정오차, 근사오차, 잔차를 뜻함
 1) 대수적 방법 : 행렬을 활요하는 것
 2) 해석적 방법
 3) 비선형 최소자승법 : 뉴턴법/뉴턴-랩슨법
 
 * 활용되어 지는 곳
 - 영상의 밝기 보정
 - 원, 타원 근사
 - 모션 추정
 
 ##### [RANSAC_random sample consensus](https://darkpgmr.tistory.com/61?category=460965)
 [video](https://www.youtube.com/watch?v=Cu1f6vpEilg)
 - 포물선을 근사시키는?
 - 최소자승법은 residual^2을 최소화하도록 모델을 찾지만 RANSAC은 컨센서스가 최대인, 즉 가장 많은 수의 데이터들로부터 지지를 받는 모델을 선택하는 방법 > 무엇을 기준으로 모델의 파라미터를 찾는가의 차이임
 
 
 ##### [SVD](https://darkpgmr.tistory.com/106)
 ##### [ICP(interative closest point)](https://www.youtube.com/watch?v=djnd502836w)
 
 ##### topological graph
 ##### [ontology](https://ko.wikipedia.org/wiki/%EC%98%A8%ED%86%A8%EB%A1%9C%EC%A7%80)
 - 개체 간의 관계를 나타낸 것!
 - 비정형 데이터를 표현하는 방법 중 하나
 - 철학적 "사물의 기본적인 범주나 세상을 구성하는 구성요소들을 상징하는 일반적인 개념을 다루는 학문"
 - 정보화시대 "정보 자원을 컴퓨터가 해석할 수 있는 시맨틱으로 표현한 특정 영역의 메타데이터"
 - IT 온톨로지란? 컴퓨터가 사람처럼 어떤 객체를 이해할 수 있도록 다른 객체와의 관계나 객체만의 의미를 표현한 자료
   - 온톨로지 조건
   1) formal : 일단 온톨로지는 formal(형식적인)해야 합니다. 사람의 개입없이 기계가 읽을 수 있는 언어로 작성되야 합니다.
   2) explicit : 온톨로지는 explicit(명백한)해야 합니다. 여러가지 뜻을 가진 단어를 상황에 맞는 뜻으로 해석할 수 있어야 합니다.
   3) shared : 가장 중요한 조건중에 하나입니다. 온톨로지를 만들었다고 해도 모든 사람들이 그 온톨로지를 사용하지 않는다면 쓸모가 없습니다. 온톨로지는 모든 사람(혹은 사물)들에게 shared(공유)되어야 합니다.
   4) conceptualization : 온톨로지는 표현하고자 하는 대상 세계의 개념들을 특정 모델로 추상화해야 합니다.
   5) domain : 온톨로지는 표현하고자하는 특정 영역이 존제합니다. 다른 영역의 객체까지는 표현하지 못합니다. 
   [출처](https://cholol.tistory.com/97)
   [https://lans.tistory.com/1062)
 
 ##### [SIFT](https://ballentain.tistory.com/47)
 
 
  
  
  
  -------------------------------------------------------------------------------------------------
  #### 단어!좀 공부해라!
  ```
  - Abstract
  establish 설립하다
  presence 있음, 참석, 존재
  attain 달성하다 
  acceptable 용인되는, 받아들일 수 있는 
  sine qua non 필수 불가결한
  Consequently 그 결과 ,따라서
  react 반응하다, 반응을 보이다
  appropriately 어울리게
  reconcile 가라앉히다. 중재하다
  
  - Intro
  incorporation 합동
  cruise 자) 순항하다, 돌아다니다
  establishment 설립
  wider 광범위한
  interpretation 설명, 해석
  facilitate ~을 수월하게 하다 <행동, 조치> 촉진(조성)하다
  coexistence 공존
  raise 위로 들어올리다, 일으키다
  in terms of ~ 면에서 
  accomplish 수행, 완성
  
  incorporation 법인격 부여, 결합, 합동
  impose 도입하다 시행하다 
  establishment 기관 시설
  cruise
  secure
  appropriate 적절한, 도용하다
  coexistence 공존
  accomplish
  maneuvering
  presence
  anthropologist
  associate
  proxemics 근접학, 공간학??? >> 인간의 공간 사용과 인구 밀도가 행동, 의사소통 및 사회적 상호 작용에 미치는 영향에 관한 연구
  - 햅틱, 운동학 등등,,,
  mutual 상호간의
  In a nutshell 아주 간결하게
  excessively
  instinctually
  stance
  allege
  ordinary
  
  
  
  interlaced 섞어 짜여진, 꼬다, 꼬이다, 엮이다 얽히다
  repeatedly 
  
  
  recognition
  
  ```
  
  ### 자주가는 링크
  - [텐진대 컴퓨터비전](https://bskyvision.com)
  - [장형기님 git](https://changh95.github.io/)
  - [다크프로그래머](https://darkpgmr.tistory.com)
  - [멈춘보다 천천히라도](https://webnautes.tistory.com/)
  - [OpenCV Tutorial](https://pysource.com/2018/03/16/image-pyramids-blending-and-reconstruction-opencv-3-4-with-python-3-tutorial-24/)
 
