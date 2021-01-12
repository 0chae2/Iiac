   
### [Robot navigation in large-scale social maps: An action recognition approach :: Konstantinos Charalampous](https://www.sciencedirect.com/science/article/pii/S0957417416305103)
```
 로봇과 사람이 공간을 공유하고 그 작업공간에 사람과의 활동을 조화롭게 할 수 있도록 만드는 로봇을 제작하는 것이 목표이다. 우리는 사람이 있는 환경에서 로봇이 안전한 작업궤도를 만들 수 있다는 것을 증명하였다. 
```
####  1. Introduction
#####  (1) 인간과 협동하는 로봇에 
  - Mitka, E. , Gasteratos, A. , Kyriakoulis, N. , & Mouroutsos, S. G. (2012). Safety certifica-
tion requirements for domestic robots. Safety Science, 50 (9), 1888–1897 . : 협동로봇 안전측정?
   - Hall, E. T. (1969). The hidden dimension : 1990. Anchor Books New York . : 활동 존...?
   - Argyle, M. (2013). Bodily communication . Routledge .
   - Argyle, M. , & Dean, J. (1965). Eye-contact, distance and affiliation. Sociometry , 289–304
   
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
 
