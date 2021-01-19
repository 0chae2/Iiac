   
## [Robot navigation in large-scale social maps: An action recognition approach :: Konstantinos Charalampous](https://www.sciencedirect.com/science/article/pii/S0957417416305103)
```
 로봇과 사람이 공간을 공유하고 그 작업공간에 사람과의 활동을 조화롭게 할 수 있도록 만드는 로봇을 제작하는 것이 목표이다. 
 우리는 사람이 있는 환경에서 로봇이 안전한 작업궤도를 만들 수 있다는 것을 증명하였다. 
```
## 목차
1. [Introduction](#introduction)
2. [Social mapping](#social-mapping)
    - Metric maps and navigation
    - Human detection
    - Action recognition
3. [Robot navigation in human populated environments](#robot-navigation-in-human-populated-environments)
    - planning
    - Socially constrained replanning
    - System integration
4. [Experimental evaluation](#experimental-evaluation)
5. [Conclusions](#conclusions)

------------------------------------------------------------------------------------------------------------------------------
### Introduction
- [Rapidly-exploring Random Tree (RRT) algorithm](#RRT)
- [Dynamic Time Warping (DTW) module](#DTW)
- [Cognitive Adaptive Optimization (CAO)](#CAO)
- [human-robot interaction(HRI)](#HRI)
- [Dynamic Bayesian Network (DBN)](#DBN)
- [Extended Social Force Model(ESFM)](#ESFM)
- [Markov Chain Monte Carlo (MCMC)](#MCMC)
- [Hierarchical Temporal Memory (HTM)](#HTM)
- 이 페이퍼에서는 소셜매핑기능과 로봇의 나머지 작동을 분리하는 대부분의 연구와는 달리 제안된 작업의 통합과 관련하여 연구한다. 본 연구에서는 로봇의 목표위치에 도달하는 동시에 사회적 상호작용을 하며 이동하는 것을 목표로 한다.
```
   Section 2. 제안된 시스템의 모듈과 맵을 추출하는 방법에 대한 설명
   Section 3. 로봇탐색 메커니즘과 구성요소를 잘 연결하는 방식 설명
   Section 4. 시스템 평가
```

  - Mitka, E. , Gasteratos, A. , Kyriakoulis, N. , & Mouroutsos, S. G. (2012). Safety certifica-
tion requirements for domestic robots. Safety Science, 50 (9), 1888–1897 . : 협동로봇 안전측정?
   - Hall, E. T. (1969). The hidden dimension : 1990. Anchor Books New York . : 활동 존...?
   - Argyle, M. (2013). Bodily communication . Routledge .
   - Argyle, M. , & Dean, J. (1965). Eye-contact, distance and affiliation. Sociometry , 289–304


------------------------------------------------------------------------------------------------------------------------------------------------------------------
### Social mapping
- social mapping framework within an existing robot navigationsystems.
   1) The computation of the metric map of the surroundings offline fashion : 오프라인 지도 만들기?
   2) The detection of humans within the scene : 현장내 인간 감지
   3) the recognition of the actions performed by individuals during the operational phase : 작동 단계 동안 개인이 수행한 행동의 인식
- 주행 할 수록 metric map이 정확해 진다 따라서 정적 장애물을 모델링하고 생성된 맵은 나중에 robot navigation and localization에 활용될 것이다.
- robot navigation 은 이전에 구성된 지도를 사용
- 예를 들어 대화하면서 지나가는 두명 사이에 지나갈까 말까 그런것도 판단을 한다 ~~~htm으로~
      
##### (1) Metric maps and navigation
- 소셜 맵을 구축하기위한 첫 번째 단계는 로봇이 관리하는 동안 로봇의 환경을 정확하게 모델링하는 것이므로 메트릭 맵이 직접 요구됩니다. 미터법지도의 구성은이 백서의 목표를 벗어 났지만,이 논문은 여기에 거주자와 내비게이션 간의 차이점을 강조하는 채택 된 방법에 대한 세부 정보를 제공하고, 무인 환경을 제공합니다. 
- RGB-D bashed > 3D metric map 환경을 만드는 것에 따르면 by Learning spatially semantic representations for cognitive robot navigation:: Kostavelis & Gasteratos
   1) SIFT feature detect : 연속된 RGB frame사이에 이미지를 매치해서 추출
   2) 획득한 각각의 point cloud 값을 3D 점에 일치시킵니다. 강체이동에 대해 SVD와 최적화 문제를 해결합니다. point cloud에서 RANSAC 알고리즘을 사용하여 평면을 감지하고 반복적으로 [ICP](#icp)를 통해 이를 등록함으로 로봇모션을 대략적으로 추정합니다.
   3) 로봇포즈 초기 추정치는 로봇이 관찰한 point cloud set에 적용되어 탐색된 환경의 일관된 3D matric map 구성
   4) 특별한 거리? Tg 그래프로 각 노드로 추가된다 >> visual odmetry
   5) t^t+1~R~svd~

##### (2) [Human detection](https://darkpgmr.tistory.com/53)
- 보행자 검출 문제의 좋은 [해결책](https://link.springer.com/article/10.1007/s11263-005-6644-8)이라고 생각하지만 빠른 검출을 하려고 하면 비싼 컴퓨터 연산 비용 발생
- [Dollar detector](https://www.researchgate.net/publication/221259170_The_Fastest_Pedestrian_Detector_in_the_West) 사용함 : Faster > [12년도](https://pubmed.ncbi.nlm.nih.gov/21808091/) 논문에는 Pedestrain detection:An evaluation of the state of the art 성능평가함
![Dollar 2012 Pedestrian detection: an evaluation of the state of the art](https://github.com/0chae2/reference/blob/master/210115/dollar12.png)(reference)

##### (3) Action recognition
- [space time feature detectors and descriptors](https://hal.inria.fr/inria-00439769)

 
-------------------------------------
    
### Robot navigation in human populated environments
#### (1) planning
- GPP(global path planner) : 현재위치에서 목표위치까지 경로를 관리해주기 때문에 매우 중요 
- D* lite
- SVMLP
- LPA*
#### (2) Socially constrained replanning
#### (3) System integration
- 대상이 위치에 도달하면
    
    
-------------------------    
    
### Experimental evaluation
  
  
  
### Conclusions
  
  
  
  
  -------------------------------------------------------------------------------------------------

#### 어디에 쓰이는지, 어떤게 개선 된 것인지? 가 중요 한계는 무엇인지?! >> 찾아보면 나오니깐 자세한건 필요할 때 찾아쓰면 되는 것

#### [RRT](https://en.wikipedia.org/wiki/Rapidly-exploring_random_tree)
  - [RRT는 샘플링 기반 경로계획법](https://blog.naver.com/pasus/221982416404)
  - [RRT*](https://blog.naver.com/pasus/221985468898)
  - [video](https://www.youtube.com/watch?v=Ao7p_xiUu4s)
  - 자율차, 로봇, 무인항공기, 우주탐사 등과 같은 분야에서 사용
  - 샘플링 기반 경로계획법 : 형상공간을 격자(grid)로 분활하지 않고, 랜덤하게 샘플점을 여러개 생성하여 점점이 공간을 탐색하여 경로를 찾는 방법   격자생성방법으로 탐색이 불가능한 고차원(high dimension) 공간에서 유리함 


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

#### [CAO](https://medium.com/@Aaron__Kim/dynamic-time-warping-%EB%8F%99%EC%A0%81-%EC%8B%9C%EA%B0%84-%EC%9B%8C%ED%95%91-ac80777f49a)
- Cognitive Adaptive Optimization

#### [HRI]
- human-robot interaction
- Dynamic Bayesian Network (DBN)
- Extended Social Force Model(ESFM)
- Markov Chain Monte Carlo (MCMC)
- Hierarchical Temporal Memory (HTM)

 
#### [HTM](https://enginius.tistory.com/236)
  - "Hierarchical Temporal Memory (HTM)은 neocortex의 structural and algorithmic properties를 모방하고자 하는 machine learning 기술이다. neocortex는 영장류의 뇌의 지능적 생각의 중심지이다. High level vision, hearing, touch, movement, language, and planning은 모두 neocortex에서 수행된다. 이러한 수많은 cognitive function을 보고 당신은 아마 각각 specialized neural algorithm을 구현하고 할 수 있을 것이다. 하지만 그렇지 않다. neocortex는 uniform pattern of neural circuitry를 보인다. 이러한 biological evidence는 neocortex가 여러 다른 intelligence function을 가질 수 있는 동일한 알고리즘으로 구현되었음을 알 수 있다." 
  
 #### [LSM(Least Squared Method)](https://darkpgmr.tistory.com/56)
 - 어떤 모델의 파라미터를 구하는 한 방법으로서, 데이터와의 residual^2의 합 또는 평균을 최소화하도록 모델의 파라미터를 구하는 방법
 - residual = 추정오차, 근사오차, 잔차를 뜻함
 1) 대수적 방법 : 행렬을 활요하는 것
 2) 해석적 방법
 3) 비선형 최소자승법 : 뉴턴법/뉴턴-랩슨법
 
 ###### 활용되어 지는 곳
 - 영상의 밝기 보정
 - 원, 타원 근사
 - 모션 추정
 
 #### [RANSAC_random sample consensus](https://darkpgmr.tistory.com/61?category=460965)
 * [video](https://www.youtube.com/watch?v=Cu1f6vpEilg)
 * [구현](http://blog.daum.net/pg365/category/RANSAC)
 - 포물선을 근사시키는?
 - 최소자승법은 residual^2을 최소화하도록 모델을 찾지만 RANSAC은 컨센서스가 최대인, 즉 가장 많은 수의 데이터들로부터 지지를 받는 모델을 선택하는 방법 > 무엇을 기준으로 모델의 파라미터를 찾는가의 차이임
 
 
 #### [SVD](https://darkpgmr.tistory.com/106)
   - 특잇값 분해
   
 #### [ICP](http://blog.daum.net/pg365/141)
  - [[video]](https://www.youtube.com/watch?v=djnd502836w)
  - Iterative Closest Point 는 컴퓨터 그래픽스에서 주로 사용되는 것으로 어떠한 모델에 대해 측정한 데이터가 있을 때, 이 측정 데이터를 모델에 매칭하기 위해, 스케일 변환, 회전, 이동을 계산하는 방법에 관한 것
  - 기존의 데이터셋에 현재 데이터를 Registration 시키는 방법, 각 데이터들이 가장 가까운 점을 이용하여 연관성을 찾고 그에 맞게 현재데이터를 이동 및 회전을 시켜 기존 데이터셋에 추가하는 방법
  - Robot : 현 레이저스캔데이터를 기존 맵에 Registration 할 때 사용, odometry 측정 값 활용하여 현재 데이터가 모델에 대해 얼마나 이동, 회전 되었는지 알 수 있지만, odometry 값에도 오차가 존재하기 때문에 ICP를 통해 보정해서 Registration함
  - ICP Algorithm
    1) sample points p<sub>i</sub>
    2) find closest point q<sup>i</sup>
    3) reject bad pairs (pi,qi)
    4) find optimal transformation R t
    5) update scan alignment
  
  - [ICP 성능에 영향을 주는 요인](https://m.blog.naver.com/PostView.nhn?blogId=tlaja&logNo=220666876033&proxyReferer=https:%2F%2Fwww.google.com%2F) :: 일반적 속도, 정확성
    1) Sampling
    2) Matching
    3) Weighting
    4) Rejecting
    
 #### topological graph
 #### [ontology](https://ko.wikipedia.org/wiki/%EC%98%A8%ED%86%A8%EB%A1%9C%EC%A7%80)
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
   [https://lans.tistory.com/1062]
 
 #### [SIFT](https://ballentain.tistory.com/47)
 1) [Scale space](https://darkpgmr.tistory.com/137)<br>
   (1) scale 이 크다! or 작다!<br>
    - 스케일이 크다는 것 : 어떤 사물을 넓은 시야에서 본다
       ex) 이미지 피라미드에서 축소된 이미지들은 원본 이미지에 비해 스케일이 크다!
           즉, 이미지 축소 --> scale 반비례로 큰 값을 가짐 (축소 : 숲, 확대: 나뭇잎)
           
 
 
 #### [A* algolithm](https://medium.com/@dev.kimji1/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-a-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-f373683f168a)
 - [그래프 탐색 알고리즘](https://ko.wikipedia.org/wiki/A*_%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)
 - [다익스트라 알고리즘](https://namu.wiki/w/%EB%8B%A4%EC%9D%B5%EC%8A%A4%ED%8A%B8%EB%9D%BC%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)을 확장하여 만들어진 출발 꼭짓점에서부터 목표 꼭짓점까지 가는 최단 경로를 찾아내는 그래프 경로 탐색알고리즘 중 하나이다.
 - heuristics 추정 값의 순서로 꼭짓점 방문 
 - [다른 알고리즘과 차이점](https://deliorange.tistory.com/110)
   1) BFS(Breadth First search) : 완적 탐색 알고리즘, 우선 순위 없이 모든 노드를 탐색
   2) 다익스트라 : 일반적인 최단거리 알고리즘, 한 노드를 기준으로 모든 노드의 최단 경로를 찾기 때문에 시간 비용이 많이 듬
   3) 플로이드 : 모든 노드의 최단경로를 찾는 알고리즘, 일반적인 시간 복잡도 O(N^3)
 - [A*](https://namu.wiki/w/A*%20%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)를 사용하는 이유는 다익스트라의 현실 적용이 매우 어렵기 때문이다. 당장에 네트워크 같은 디지털적인 공간이 아닌, 현실의, 사람이 사는 공간을 생각해보자. 사람이 다닐 수 있는 "거리"는 명백히 아날로그하다. 이것들을 전부 노드화시키기에는 그 수가 엄청나게 많아질 수 있다. 그렇다면 탐색해야 하는 공간도 그만큼 커지게 되고, 시간 복잡도 역시 아득히 커질 것이다. 또한 어찌어찌 잘 노드화시켜서 다익스트라를 사용할 수 있는 상황을 만들어서 경로를 발견했다고 치자. 그렇게 탐색한 경로가 자동차 정체 구간, 출근길 등 다양한 변수로 인해 오히려 더 느려질 수 있는 경우도 발생하기 마련이다. 이러한 변수 때문에 A* 알고리즘을 사용하는 것이다. 그리고 A*를 발전시킨 형태가 D*(Dynamic A*)알고리즘인데, 현세대의 대부분의 차량 내비게이션은 이를 활용한다고 보면 된다.
             
 
  
  
  
  -------------------------------------------------------------------------------------------------
  
  
  ### 자주가는 링크
  - [텐진대 컴퓨터비전](https://bskyvision.com)
  - [장형기님 git](https://changh95.github.io/)
  - [다크프로그래머](https://darkpgmr.tistory.com)
  - [멈춘보다 천천히라도](https://webnautes.tistory.com/)
  - [OpenCV Tutorial](https://pysource.com/2018/03/16/image-pyramids-blending-and-reconstruction-opencv-3-4-with-python-3-tutorial-24/)
  - [Markdown문법](https://velog.io/@yuuuye/velog-%EB%A7%88%ED%81%AC%EB%8B%A4%EC%9A%B4MarkDown-%EC%9E%91%EC%84%B1%EB%B2%95)
  - [Markdown문법2](https://steemit.com/kr/@nand/markdown)
  - [kitech](http://blog.daum.net/pg365/)
  - [slam core](https://careers.slamcore.com/#section-jobs)
  - [jinyong slam](http://jinyongjeong.github.io/tag/SLAM/)
 
