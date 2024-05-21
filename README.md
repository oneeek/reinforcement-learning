# Reinforcement Learning (강화학습)

- Machine Learning는 크게 Supervised Learning, Unsupervised Learning, 그리고 Reinforcement Learning의 3가지로 분류.

- **`Reinforcement learning`** 은 행동심리학의 시행착오를 통해 학습하는 '강화' 개념에서 영감을 받은 **순차적 의사결정 문제를 해결하기 위한 방법론**.

<br/>

> ### **강화학습의 구성 요소**

 **`Environment`**　⇄　**`Agent`** : 강화학습은 특정 **Environment**에서 정의된 **Agnet**가 현재의 **State**에서 선택 가능한 **Action** 중 **Reward**를 **최대화**하는 방향으로 **Action을 선택**하도록 스스로 학습한다. 이때 Reward(기대 보상)는 미래에 받게 될 모든 Reward들의 합에 대한 현재 값으로 정의한다.

<br/>

🤔 ##### *무슨 소리인지 이해가 안 되어도 정상입니다*

> 문제를 해결하기 위해서는 우선 문제를 정의해야한다. 강화학습은 앞서 *순차적 의사결정 문제를 해결하기 위한 방법* 이라고 정의했다. 따라서 이때 문제는 사건이 발생하는 순서가 존재한다. 

**Markov Property**는 미래에 발생할 수 있는 사건의 순서를 표현할때 사용되는 것으로, 강화학습은 **Markov Property**를 가지는 **`Markov Decision Process`** 로 정의된 문제를 푸는 알고리즘이다.


## Markov Decision Process(MDP)

**Markov Property**란 **𝑡시점**에 어떤 사건이 발생할 확률은 오직 **𝑡−1시점**에만 영향을 받는 성질으로, 강화학습의 **State(𝑆)** 는 이를 가진다고 가정한다.

$$ **P[S_{t+1}|S_t] = P[S_{t+1}|S_1,⋯S_t]** $$

<br/>

- MDP의 구성요소 : **State(𝑆), Action(𝐴), Reward(𝑅), 전이확률(𝑃), 할인율(𝛾)**

  -  **State(𝑆)**, Agent가 Environment를 관찰(observation)하여 인식
  -  **Action(𝐴)**,
  -  **Reward(𝑅)**, Agent가 결정한 Action에 따른 피드백
  -  **전이확률(𝑃)**
  -  **할인율(𝛾)**

<br/>

## Reinforcement Learning의 분류

- 모델이 존재하는 경우 Model-based, 모델이 존재하지 않는 경우 Model-free
- 학습의 대상이 정책(policy)이라면 Policy-Based, 가치함수(value function)라면 Value-Based

