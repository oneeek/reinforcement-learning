# Reinforcement Learning (강화학습)

- Machine Learning는 크게 Supervised Learning, Unsupervised Learning, 그리고 Reinforcement Learning 3가지로 분류.

- **`Reinforcement learning`** 은 행동심리학의 시행착오를 통해 학습하는 '강화' 개념에서 영감을 받은 **순차적 의사결정 문제를 해결하기 위한 방법론**.


> ### **강화학습의 구성 요소**

 **`Environment`**　⇄　**`Agent`** : 강화학습은 특정 **Environment**에서 정의된 **Agnet**가 현재의 **State**에서 선택 가능한 **Action** 중 **Reward**를 최대화하는 방향으로 Action을 선택하도록 스스로 학습한다. 이때 Reward(기대 보상)는 미래에 받게 될 모든 Reward들의 합에 대한 현재 값으로 정의한다.


> ### **강화학습의 학습 순서**

- 예시

1. Agnet는 Environment의 State를 관측(observation)한다.
2. Agnet는 현재 State에서 Reward를 가장 많이 받을 것이라 예상되는 Action을 선택한다.
3. Agnet가 취한 Action에 의해 Environment가 변화한다.
4. Environment로부터 주어진 Reward에 대한 정보로 Agnet의 Action을 평가한다. 
5. Agnet는 변화한 Environment의 State를 바탕으로 새로운 Action을 선택한다.

위 과정을 반복하면서 Agnet는 Reward를 최대화 할 수 있는 Action을 학습한다.

<br/>

🤔 강화학습으로 해결하고자 하는 문제는 Markov Decision Process로 정의되는 문제이다. 따라서 이에 대한 이해가 필요하다.


## Markov Decision Process(MDP)

- **`Markov Decision Process`** 는 순차적 의사결정 문제를 풀기 위한 수학 모델이다.

- 이는
- **`Markov Property`** 는 **𝑡시점**에 어떤 사건이 발생할 확률은 오직 **𝑡−1시점**에만 영향을 받는 성질이다.

- 강화학습의 대상이 되는 문제는 Markov Property를 가지는 **`Markov Decision Process`** 로 정의된다.

-  Markov Property에 따라 **State(𝑆)** 는 아래 식과 같이 표현할 수 있다.

$$  **P[S_{t+1}|S_t] = P[S_{t+1}|S_1,S_2,⋯S_t]**  $$

<br/>

- MDP의 구성요소 : **State(𝑆), Action(𝐴), Reward(𝑅), 전이확률(𝑃), 할인율(𝛾)**

  -  **State(𝑆)**, 
  -  **Action(𝐴)**,
  -  **Reward(𝑅)**,
  -  **전이확률(𝑃)**
  -  **할인율(𝛾)**

<br/>

## Reinforcement Learning의 분류

- 모델이 존재하는 경우 Model-based, 모델이 존재하지 않는 경우 Model-free
- 학습의 대상이 정책(policy)이라면 Policy-Based, 가치함수(value function)라면 Value-Based

