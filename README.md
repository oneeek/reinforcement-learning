# Reinforcement Learning (강화학습)

- Machine Learning는 크게 Supervised Learning, Unsupervised Learning, 그리고 Reinforcement Learning 3가지로 분류된다.

- **`Reinforcement learning`** 은 행동심리학의 **시행착오**를 통해 학습하는 '강화' 개념에서 영감을 받은 **순차적 의사결정 문제를 해결하기 위한 방법론**이다.

<br/>

> ### **강화학습의 구성 요소**

### **Environment**　⇄　**Agent**

**`Environment`**, **`Agent`**, **`State`**, **`Action`**, **`Reward`**

- 특정 **Environment**에서 정의된 **Agent**는 현재의 **State**에서 선택 가능한 Action 중 **Reward**를 최대화하는 방향으로 **Action**을 선택하도록 학습된다. 이때 Reward(기대 보상)는 미래에 받게 될 모든 Reward들의 합에 대한 현재 값으로 정의한다.

<br/>

> ### **Markov Decision Process(MDP)**

🤔 강화학습으로 해결하고자 하는 문제는 Markov Decision Process로 정의되는 문제이다. 따라서 우선 이에 대한 이해가 필요하다.

- **`Markov Decision Process`** 는 순차적 의사결정 문제를 풀기 위한 수학 모델이다.

- MDP의 구성요소 : **State(𝑆), Action(𝐴), Reward(𝑅), 전이확률(𝑃), 할인율(𝛾)**

- State(𝑆)는 현재 어떤 사건이 발생할 확률은 오직 이전 시점에만 영향을 받는 **`Markov Property`** 를 가진다.

$$  **P[S_{t+1}|S_t] = P[S_{t+1}|S_1,S_2,⋯S_t]**  $$

<br/>

> ### **강화학습의 학습 과정**

🤔 MDP로 강화학습의 문제를 정의하고 풀어나가는 방법을 Grid World 예시로 알아보자.

- Grid World

  - Grid World의 Environment는 2차원의 격자로 구성된다.
  - Grid World의 Agent는 주어진 시간(step) 내에 목표지점에 도달해야 한다.
  - Agent는 현재 위치에서 이웃한 격자로 1칸 이동하는 Action(상하좌우)을 취할 수 있다.
  - Agent가 목표지점에 빠르게 도착할 수 있도록 매 step마다 -0.1점의 Reward(페널티)를 준다.
  - Agent가 목표지점에 도착하면 +1점의 Reward를 준다.

<br/>

- Grid World의 학습 과정

<p align="center">
<img width="60%" src="https://github.com/oneeek/reinforcement-learning/assets/169229814/1ab0c923-618b-4b22-bf92-1d152bb0716a"/>

   1. Agent는 Environment의 현재 State <1,1>를 관측(observation)하여 인지한다.
   3. Agent는 현재 State에서 선택할 수 있는 Action 중 오른쪽으로 1칸 이동하는 Action을 선택한다.
   4. Agent의 Action으로 인해 State가 <2,1>로 변화한다.
   5. 목표지점에 도달하지 못하고 step이 지났으므로 -0.1점의 Reward를 받는다.
   6. Agent는 새로운 State <2,1>에서 새로운 Action을 선택한다.

   7. 이를 반복하다가 Agent가 목표지점에 도달하면 episode는 종료된다. 정해진 step의 수가 끝나면 목표지점에 도달하지 못해도 episode는 종료된다.

<p align="center">
<img width="58%" src="https://github.com/oneeek/reinforcement-learning/assets/169229814/bbd58c1b-ad60-4768-8795-42809b12d09c"/>

위 이미지의 episode에서 최종 Reward는 step 마다 -0.1점, 목표지점에 도달하여 +1점을 받았기 때문에 **0.3점**이 된다.

위 Agent는 특정 State에서 Action을 선택할 때 아무런 정보가 없었기 때문에 무작위로 Action을 선택했다.

그러나 위 episode를 통해 특정 State에서 선택한 Action과 그에 따른 Reward 정보가 생기게 되었다. 이 정보를 저장하고 다음 episode를 시작하면 특정 State에서 Action을 선택할 때 Reward 정보를 참조하여 Action을 선택할 수 있게 된다.



<br/>
<br/>

## Reinforcement Learning의 분류

- 모델이 존재하는 경우 Model-based, 모델이 존재하지 않는 경우 Model-free
- 학습의 대상이 정책(policy)이라면 Policy-Based, 가치함수(value function)라면 Value-Based

