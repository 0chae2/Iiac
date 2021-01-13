   
### [Robot navigation in large-scale social maps: An action recognition approach :: Konstantinos Charalampous](https://www.sciencedirect.com/science/article/pii/S0957417416305103)
```
 로봇과 사람이 공간을 공유하고 그 작업공간에 사람과의 활동을 조화롭게 할 수 있도록 만드는 로봇을 제작하는 것이 목표이다. 
 우리는 사람이 있는 환경에서 로봇이 안전한 작업궤도를 만들 수 있다는 것을 증명하였다. 
```
####  1. Introduction
- [Rapidly-exploring Random Tree (RRT) algorithm](#RRT)
  - [RRT는 샘플링 기반 경로계획법](https://blog.naver.com/pasus/221982416404)
  - [RRT*](https://blog.naver.com/pasus/221985468898)
  - [video](https://www.youtube.com/watch?v=Ao7p_xiUu4s)
- Dynamic Time Warping (DTW) module

- [Cognitive Adaptive Optimization (CAO)](https://medium.com/@Aaron__Kim/dynamic-time-warping-%EB%8F%99%EC%A0%81-%EC%8B%9C%EA%B0%84-%EC%9B%8C%ED%95%91-ac80777f49a)
- human-robot interaction(HRI)
- Dynamic Bayesian Network (DBN)
- Extended Social Force Model(ESFM)
- Markov Chain Monte Carlo (MCMC)
- Hierarchical Temporal Memory (HTM)

  - Mitka, E. , Gasteratos, A. , Kyriakoulis, N. , & Mouroutsos, S. G. (2012). Safety certifica-
tion requirements for domestic robots. Safety Science, 50 (9), 1888–1897 . : 협동로봇 안전측정?
   - Hall, E. T. (1969). The hidden dimension : 1990. Anchor Books New York . : 활동 존...?
   - Argyle, M. (2013). Bodily communication . Routledge .
   - Argyle, M. , & Dean, J. (1965). Eye-contact, distance and affiliation. Sociometry , 289–304
   
   
   ```
   인간이 거주하는 환경에 로봇 통합 그들이 할 수있는 방법론의 확립을 강요 사람들 사이에서 안전하고 적절하며 정상적인 방법으로 순항합니다. 이것은 안전한 항해의 개념에 대한 더 넓은 해석을 얻기위한 연구 측면에서 새로운 도전을 제기합니다. 확립 된 안전을 넘어 인간-로봇 공존 촉진 측정(Mitka, Gasteratos, Kyriakoulis, & Mouroutsos, 2012). 의 위에 모바일 로봇 공학, 매핑은 로봇에게 의미가 있습니다. 모바일 로봇 공학에서 매핑은 로봇이 주변에 대한 의미있는 설명을 구성하여 높은 수준의 목표를 달성 할 수있는 능력을 부여합니다. 새로운 주제 소셜 매핑은 인간의 존재와 활동이 알려지지 않은 복잡한 환경에서 로봇의 기동을 다룹니다. 로봇은 적절한 방식으로 모델링해야합니다. 운영 행동을 인간의 가산 성과 연관시키고 따라서 개인의 편의를 고려하여 탐색 전략을 조정하십시오. 따라서 공간 관리는 인간과 상호 작용할 때의 반응은 이해하고 모델링 할 수 있습니다. 상당한 연구가 공식화하기 위해 사회 과학 분야에서 수행 개인의 행동과 공간에서의 위치가 상호 작용의 질에 미치는 영향을 추정합니다. 문화 인류 학자 에드워드 T. Hall은 proxemics (Hall, 1969)라는 용어를 만들어 문화에 의해 형성되는 생리적 영향이 구역을 지정 함을 제안합니다. 
근접 거리의.이 작업의 대부분은 Argyle (2013)에 요약되어 있으며 친밀 성 평형 모델 (Argyle Dean, 1965), 근접 행동과 상호 시선 사이의 상호 작용을 설명합니다. 요컨대, 그들이 접근했을 때 과도하게 가까운 사람들은 본능적으로 덜 편안한 자세를 취합니다. 또한 개인은 일상적인 대화를 수행 할 수있는 특정 공간을 주장하며 참가자 만 액세스 할 수 있습니다. 이 공간은 다른 사람들이 높이 평가하지만 위반은 불편 함을 유발한다 (Hall, 1969). 근접 이론에 따르면, 사람 주변의 영역은 네 가지 기본 영역, 즉 친밀한 영역, 개인 영역, 사회적 영역, 공개 된 것. 첫 번째 영역은 반경 0.45m의 원반이며 속삭임과 같은 신체 접촉과 관련된 동작에 해당합니다. 두 번째는 내부 및 외부 반경이 0.45 인 원형 링입니다. 및 1.2m, 각각 친척과의 상호 작용 또는 혼잡 한 상황에서뿐만 아니라 친구. 세 번째 원형 구역 반경이 [1.2-3.5] m 범위 인 경우 거리를 예를 들어 쇼핑이나 박물관에서 공공. 마지막 영역 반경이 3.5m 이상이면 상호 작용이 없음을 나타냅니다. 다카야마와 판토 파루 (2009)의 작업을 바탕으로 모바일 로봇과 인간 사이에 동일한 근접 행동이 적용된다고 가정합니다. 따라서 소셜 매핑은 로봇의 소셜 인텔리전스 구현을 연구합니다. 
근접의 규칙. 로봇 내비게이션은지도로 표현 된 환경에 대한 설명을 기반으로 궤적을 결정하는 모든 경로 계획 접근 방식에 의존합니다. 기본 순항 기능에 대한 충분한 정보를 제공하는지도는 메트릭으로 특성화되고 부여 된지도는 의미 론적 특징에 관한 풍부한 지식을 가진 브랜드는 
의미 론적 맵 (Kostavelis & Gasteratos, 2015), 지난 몇 년 동안 점점 더 많은 관심을 받고 있습니다. 이 증가하는 관심은 
풍부한 정보를 제공하는지도가 인간의 인식에 더 가까운 향상된 탐색 전략으로 이어진다는 사실에 의해 정당화됩니다. 이러한 관점에서 소셜 매핑 분야는 로봇에 인접한 사회적 역량을 강화하는 것을 추구합니다. 인간에 의해 표시됩니다. 소셜 매핑 분야의 철저한 연구 최근에 Martinez (2013)와 Kirby (2010)에 설명되어 있습니다. 그러나 타도 코로, 하야시, 마나베, 나 카미의 전형적인 종이는 그리고 Takamori (1995)는 위험을 적용 할 수있는 인간과 함께 존재하는 로봇에 대한 계획 방법론을 제시했습니다. 
추정 절차, 계산 시간 및 위험 정도. 그 후 계산 된 위험은 다음과 함께 입력으로 제공됩니다. 나머지 경로의 길이, 각각의 선형성 및 
평가 함수로의 에너지 변화. 로봇의 경로는 유전자 프로그래밍 방법론을 통해 평가 기능을 최적화하여 파생됩니다. Pacchierotti, Christensen 및 
Jensfelt (2006)는 로봇에 통합 된 제어 전략을 제안합니다. 인간이있는 복도에서 허용되는 행동. 
첫째, 로봇이 개인의 개인 공간에 침투하면 그 존재가 감지되었음을 알린다. 그후, 로봇은 사람이 지나갈 때까지 가능한 한 오른쪽으로 (그의 프레임없이) 움직입니다. 완료되면 로봇은 일반으로 전환됩니다. 탐색하고 여행을 계속합니다. Sisbot, MarinUrias, Alami 및 Simeon (2007)의 작업은 다음과 같은 모션 플래너를 제안합니다. 시야 측면에서 인간의 존재를 고려하고 인간 로봇 배치에 대한 접근성 및 개인적 선택. 이 시스템은 개인을 정적 모듈의 계산 시간이 충분히 짧습니다. 경로의 온라인 재 계산을 허용합니다. 사람의 역동적 인 존재감을 고려한 모션 플래너를 선보입니다.Svenstrup, Bak 및 Andersen (2010)에서 위치와 인간의 움직임은 잠재적 인 분야로 모델링되고 실현 가능한 궤도는 Rapidly-exploring Random을 사용하여 계산됩니다. 트리 (RRT) 알고리즘. 또한 예측 제어 메커니즘은 악용되고 전체 경로를 완료하는 대신 후속 반복을 계산할 때까지 일부만 추적됩니다. 
RRT의. 유사한 방식으로 동적 플로어 필드가 활용됩니다. Boukas, Kostavelis, Gasteratos 및 Sirakoulis (2015)에서 홀의 붐비는 공간에서 로봇이 균형을 잡을 수 있도록 혼잡 및 대피를 용이하게합니다. Torta, Cuijpers, Juola 및 van der Pol (2011)은 다음을 제공하는 계획 아키텍처를 제안합니다. 사회적으로 허용되는 개념과 이러한 이유로 개인 공간 개인의 거리와 방향을 모두 고려하여 모델링됩니다. 로봇의 다음 위치는 베이지안 필터링 절차를 기반으로 온라인 방식으로 계산 된 다음 탐색 모듈로 전달됩니다. 작업O’Callaghan, Singh, Alempijevic, Ramos (2011) 보행자의 움직임 패턴 검사를 기반으로 한 내비게이션 방법을 제시합니다. 가우시안 학습 절차는 위치에 따라 로봇의 방향을 결정하는 확률 함수를 계산합니다. 또한 필터링 절차를 통해 더 부드러운 기능으로 이어지는 초기 데이터 더 자연스러운 궤적. 후자는 이전의 일반적인 계획 접근 방식과 결합되며 점점 더 많은 데이터를 집계하여 개선 할 수 있습니다. Luber, Spinello, Silva 및 Arras (2012)는 비지도 학습 문제를 해결하기 위해 사용 가능한 데이터 세트에서 걷는 사람의 측정치를 활용하는 학습 방법론을 설명했습니다. 특히, 상대적인 모션 프로토 타입을 공식적으로 정의하고 계층 적 기술을 통해 클러스터링합니다.이 기술은 수정 된 동적 시간 왜곡 (DTW) 모듈에 의존하는 거리 함수를 사용합니다. 그 후, 상대적인 모션 프로토 타입을 모델 선택에 사용하여 사회적 맥락을 추출합니다. 이것은 차례로 다음과 같은 역할을하는 비용 맵의 형성에 활용됩니다. 
경로 플래너에 대한 입력. Rios-Martinez, Renzaglia, Spalanzani, Martinelli 및 Laugier (2012)의 작업은 사람들의 움직임에 대한 예측과 다음과 같은 불편 함 수준을 기반으로 인구 밀집 환경에서 탐색 전략을 제시합니다. 
근사 이론. 이 두 가지를 통합하는 기능 용어는 CAO (Cognitive Adaptive Optimization)를 통해 최적화됩니다. 접근 (Kosmatopoulos & Kouvelas, 2009), 최적화 작업에 적합한 확률 적 방법 결석. 결과적으로 최적의 결과는 전적으로 센서의 상태 구성에 대한 입력으로 측정. 또한이 
접근 방식은 다음에 대한 기준의 확장을 촉진합니다. 동적 또는 환경 적 제약. 방해받지 않고 효율적인 인간-로봇 상호 작용에 관하여 (HRI), 로봇은 근접을 인식하고 채택 할 수 있어야합니다. 그에 따른 행동. 이를 위해 Mead (2012)는 전체 포즈, 음성 및 제스처 데이터를 고려한 방법론을 제안하며, 그 분포와 상호 의존성은 DBN (Dynamic Bayesian Network)으로 모델링됩니다. 그 후 로봇은 사회적 자극의 생성과 인식을 촉진하는 가능한 포즈를 추론합니다. 또 다른 연구 (Mead, Atrash, & Mataric, 2011)는 사회적 행동에 기여하는 요인, 즉 주의력, 대인 관계, 생리적, 조직적 요인을 분석합니다. 이 분석은 인식 할 수있는 실시간 시스템에서 악용됩니다. 사람이 거주하는 환경에서 이러한 행동에 주석을 달 수 있습니다. Papadakis, Spalanzani 및 Laugier (2013)의 작품은 암시적 함수의 등고선 측면에서 소셜 영역 복잡한 사회적 상호 작용을 설명 할 수 있습니다. 이러한 영역은 다음과 같이 도출되는 비선형 확률 함수를 통해 형성됩니다. 커널 공간의 학습 문제에 대한 해결책. 또한 다카야마와 판토 파루에서의 작업 (2009)은 근위부와 관련하여 HRI에 영향을 미치는 요인. 특별히, 통제 된 형태로 세 가지 다른 가설을 조사합니다. 
실험 : 첫 번째는 개인이 로봇에 접근하는 것을 고려하고 두 번째와 세 번째는 자율적이고 사람들에게 다가가는 원격 조종 로봇. 루버와 Arras (2013)는 사람들 사이의 사회적 연결을 감지하고 인식하는 것은 물론 그들이 속한 클러스터를 추적하는 문제를 다룹니다. 형태 이 작업의 대부분은 Argyle (2013)에 요약되어 있으며 친밀 성 평형 모델 (Argyle & Dean, 1965), 근접 행동과 상호 시선 사이의 상호 작용을 설명합니다. 요컨대, 그들이 접근했을 때 과도하게 가까운 사람들은 본능적으로 덜 편안한 자세를 취합니다. 또한 개인은 일상적인 대화를 수행 할 수있는 특정 공간을 주장하며 참가자 만 액세스 할 수 있습니다. 이 공간은 다른 사람들이 높이 평가하지만 위반은 불편 함을 유발한다 (Hall, 1969). 근접 이론에 따르면, 사람 주변의 영역은 네 가지 기본 영역, 즉 친밀한 영역, 개인 영역, 사회적 영역,공개 된 것. 첫 번째 영역은 반경 0.45m의 원반이며 속삭임과 같은 신체 접촉과 관련된 동작에 해당합니다. 두 번째는 내부 및 외부 반경이 0.45 인 원형 링입니다. 및 1.2m, 각각 친척과의 상호 작용 또는 
혼잡 한 상황에서뿐만 아니라 친구. 세 번째 원형 구역 예를 들어 쇼핑이나 박물관에서 공공. 마지막 영역 반경이 3.5m 이상이면 상호 작용이 없음을 나타냅니다. 다카야마와 판토 파루 (2009)의 작업을 바탕으로 모바일 로봇과 인간 사이에 동일한 근접 행동이 적용된다고 가정합니다. 따라서 소셜 매핑은 로봇의 소셜 인텔리전스 구현을 연구합니다. 근접의 규칙. 로봇 내비게이션은지도로 표현 된 환경에 대한 설명을 기반으로 궤적을 결정하는 모든 경로 계획 접근 방식에 의존합니다. 기본 순항 기능에 대한 충분한 정보를 제공하는지도는 메트릭으로 특성화되고 부여 된지도는 의미 론적 특징에 관한 풍부한 지식을 가진 브랜드는 의미 론적 맵 (Kostavelis & Gasteratos, 2015), 지난 몇 년 동안 점점 더 많은 관심을 받고 있습니다. 이 증가하는 관심은 풍부한 정보를 제공하는지도가 인간의 인식에 더 가까운 향상된 탐색 전략으로 이어진다는 사실에 의해 정당화됩니다. 이러한 관점에서 소셜 매핑 분야는 로봇에 인접한 사회적 역량을 강화하는 것을 추구합니다. 인간에 의해 표시됩니다. 소셜 매핑 분야의 철저한 연구 최근에 Martinez (2013)와 Kirby (2010)에 설명되어 있습니다. 그러나 타도 코로, 하야시, 마나베, 나 카미의 전형적인 종이는 그리고 Takamori (1995)는 위험을 적용 할 수있는 인간과 함께 존재하는 로봇에 대한 계획 방법론을 제시했습니다. 추정 절차, 계산 시간 및 위험 정도. 그 후 계산 된 위험은 다음과 함께 입력으로 제공됩니다. 나머지 경로의 길이, 각각의 선형성 및 평가 함수로의 에너지 변화. 로봇의 경로는 유전자 프로그래밍 방법론을 통해 평가 기능을 최적화하여 파생됩니다. Pacchierotti, Christensen 및 Jensfelt (2006)는 로봇에 통합 된 제어 전략을 제안합니다. 인간이있는 복도에서 허용되는 행동. 첫째, 로봇이 개인의 개인 공간에 침투하면 그 존재가 감지되었음을 알린다. 그후, 로봇은 사람이 지나갈 때까지 가능한 한 오른쪽으로 (그의 프레임없이) 움직입니다. 완료되면 로봇은 일반으로 전환됩니다. 탐색하고 여행을 계속합니다. Sisbot, MarinUrias, Alami 및 Simeon (2007)의 작업은 다음과 같은 모션 플래너를 제안합니다. 시야 측면에서 인간의 존재를 고려하고 인간 로봇 배치에 대한 접근성 및 개인적 선택. 이 시스템은 개인을 정적 모듈의 계산 시간이 충분히 짧습니다. 경로의 온라인 재 계산을 허용합니다. 사람의 역동적 인 존재감을 고려한 모션 플래너를 선보입니다. 
Svenstrup, Bak 및 Andersen (2010)에서 위치와 인간의 움직임은 잠재적 인 분야로 모델링되고 실현 가능한 궤도는 Rapidly-exploring Random을 사용하여 계산됩니다. 트리 (RRT) 알고리즘. 또한 예측 제어 메커니즘은 악용되고 전체 경로를 완료하는 대신 후속 반복을 계산할 때까지 일부만 추적됩니다. RRT의. 유사한 방식으로 동적 플로어 필드가 활용됩니다. Boukas, Kostavelis, Gasteratos 및 Sirakoulis (2015)에서 홀의 붐비는 공간에서 로봇이 균형을 잡을 수 있도록 혼잡 및 대피를 용이하게합니다. Torta, Cuijpers, Juola 및 van der Pol (2011)은 다음을 제공하는 계획 아키텍처를 제안합니다. 사회적으로 허용되는 개념과 이러한 이유로 개인 공간 개인의 거리와 방향을 모두 고려하여 모델링됩니다. 로봇의 다음 위치는 베이지안 필터링 절차를 기반으로 온라인 방식으로 계산 된 다음 탐색 모듈로 전달됩니다. 작업 O’Callaghan, Singh, Alempijevic, Ramos (2011) 이 작업은 2D 범위 센서에만 의존하며 온라인 방식으로 작동 할 수 있습니다. 다중 가설 추적 기술을 기반으로하며 개인의 움직임에 대한 예측을 향상시키고 데이터 연관성을 향상시킵니다. Ferrer와 Sanfeliu (2014)에서 저자는 로봇과 인간의 움직임을 모두 고려하면서 내비게이션 계획을 제시합니다. 이 방법은 로봇 동작의 영향을 예측하고 인접한 개인에게 미치는 영향을 최소화합니다. 비록 전체 장면에서 움직임을 예측하는 것은 특히 비용이 많이 드는 작업이며,이 방법은 Extended Social Force Model을 활용합니다. (ESFM) (Helbing & Molnar, 1995) 두 가지 예측 모두 촉진 모델과 내비게이션 시스템. 또 다른 접근 방식은 ESFM은 Ferrer, Garrell 및 Sanfeliu (2013a)에서 로봇 동반자 모델을 설명하고 근위에 대한 효능을 평가할 수있는 새로운 측정 항목을 설명합니다. 또한, 사용자는 응답을 개선하기 위해 접근 방식에 의해 사용되는 피드백을 제공하기 위해 다중 모드 인터페이스를 사용할 수 있습니다. ESFM은 또한 Ferrer, Garrell 및 Sanfeliu (2013b)의 Markov Chain Monte Carlo (MCMC) 변형과 결합되어 사전 정의 된 목적지와 함께 환경을 나타내는 그래프 맵을 형성했습니다. 그런 다음 로봇에 초점을 맞춘 ESFM 모델에 의존하는 탐색 알고리즘이 각 작업을 수행하고 MCMC Metropolis-Hastings 방법론은 모델의 매개 변수 값을 최적화합니다. 마지막으로 Koay, Syrdal, Ashgari-Oskoei, Walters, Dautenhahn (2014)의 저자는 로봇의 사회적 행동과 기술에 대한 사용자의 친숙도에 비례하여 발생하는 각각의 종속성. 또한 도출 된 결과는 가정 환경에 대한 HRI 연구에서 활용되었습니다. 그 목적은 로봇이 가져야하는 사회적 근접 행동에 대해 더 많은 통찰을 얻고 LED가 로봇의 의도를 표시하는 것입니다. 두 번째 연구는 로봇의 거리, 접근 방향 및 자세에 관한 흥미로운 결과를 추론했습니다. 
이 백서의 궁극적 인 목표는 인간이 거주하는 환경에서 로봇 탐색을 가능하게하는 통합 프레임 워크를 도입하는 동시에 사회적으로 전시하는 것입니다. 
수행중인 조치를 고려하여 수용 가능한 행동 개인. 이 방법은 실내 영역을보다 정확하게 과도하게 혼잡하지 않고 사람이 보통 2 ~ 3 명씩 모이는 작업 환경. 매핑 부분에 관한 한, 로봇은 미리 계산 된 3D 메트릭 맵을 불러와 알려진 환경에서 탐색합니다. 이전 작업에서 설명한 방법에 따라 빌드되었습니다. (Kostavelis & Gasteratos, 2013). 메트릭 맵은 실내 환경에서 로봇을 수동으로 운전하는 오프라인 방식으로 토폴로지 그래프로 구성됩니다. 그만큼 이 그래프의 노드는 로봇이 작동 할 때 재귀적으로 트리거됩니다. 레이블이 지정된 한 장소에서 다른 장소로 향했습니다. 
3D 메트릭 맵의 관련 부분. 인간 탐지 체계 RGB 정보를 기반으로 지속적으로 실행되고 유효한 결과를 반환하면 동작 인식 루틴이 시작됩니다. 로봇이 신속하게 대응하기 위해서는 인간 감지가 실시간으로 피드백을 제공합니다. 여기에 사용 된 것 (Dollár, Be'longie, & Perona, 2010)은 다른 최첨단 방법의 정확성을 유지하면서 이러한 문제에 대한 가장 빠른 해결책으로 입증되었습니다. 깊이 정보는 로봇의 정확한 위치를 파악하기 위해 로봇의 위치와 함께 사용됩니다. 지도에서 개인. 인식 된 동작에 따라 로봇은 근접 규칙에 따라 궤도를 수정하여 사회적 인식을 나타낼 수 있습니다. 채택 된 동작 인식 모듈은 딥 러닝 모듈이며 HTM (Hierarchical Temporal Memory) 개념을 따릅니다. 우리가 아는 한 이것은 사람들이 수행하는 행동에 의존하는 소셜 매핑을위한 첫 번째 작업입니다. 마지막으로, 도입 된 프레임 워크의 각 개별 구성 요소가 각 출판물에서 철저하게 평가되고 테스트되었음을 주목할 가치가 있습니다. 제안 된 작업의 통합과 관련하여 거주 환경에서 각각의 로봇 시스템을 사용하여 평가됩니다. 데이터 세트에서 평가되거나 각 소셜 매핑 모듈을 명시 적으로 테스트하는 대부분의 게시 된 작업과는 달리 나머지 로봇 운영 모듈의 소셜 매핑 기능. 이 작업에서 로봇은 목표를 제공받습니다. 위치를 파악하고 핵심 요소를 원활하게 조정하여 순항합니다. 목표 위치에 도달하는 동시에 모듈 
사회적으로 수용 가능한 반응을 보인다. 논문의 나머지 부분은 다음과 같이 구성됩니다. 섹션 2에서는 제안 된 시스템의 모듈과이를 추출하기 위해 활용되는 방식을 설명합니다. 
   ```
 ``` 
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
#### [RRT](https://en.wikipedia.org/wiki/Rapidly-exploring_random_tree)
  - [RRT는 샘플링 기반 경로계획법](https://blog.naver.com/pasus/221982416404)
  - [RRT*](https://blog.naver.com/pasus/221985468898)
  - [video](https://www.youtube.com/watch?v=Ao7p_xiUu4s)
#### Dynamic Time Warping (DTW) module

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
 
