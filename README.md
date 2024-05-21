# Reinforcement Learning (강화학습)

- Machine Learning는 크게 Supervised Learning, Unsupervised Learning, 그리고 Reinforcement Learning의 3가지 방법으로 분류.

- ***Reinforcement learning*** 은 행동심리학의 시행착오를 통해 학습하는 '강화' 개념에서 영감을 받은 순차적 의사결정 문제를 해결하기 위한 방법론.


<br/>

👻 강화학습의 구성 요소 👻

 **Environment  ⇄  Agent**   : 강화학습은 특정 Environment에서 정의된 Agnet가 현재의 State에서 선택 가능한 Action 중 Reward를 최대화하는 방향으로 Action을 선택하도록 스스로 학습한다. 이때 Reward(기대 보상)는 미래에 받게 될 모든 Reward들의 합에 대한 현재 값으로 정의한다.

<br/>

👻 Markov Decision Process 👻

 **State(𝑆 ), Action(𝐴), Reward(𝑅), 전이확률(𝑃), 할인율(𝛾)**

: 특정 


## Reinforcement Learning의 분류

- 모델이 존재하는 경우 Model-based, 모델이 존재하지 않는 경우 Model-free
- 학습의 대상이 정책(policy)이라면 Policy-Based, 가치함수(value function)라면 Value-Based

