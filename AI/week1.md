### what is AI?

- Thinking 
  - like a human
    - Turing test, but not reproducible, constructive or amenable to mathematical analysis
  - rationally
    - If A $\implies$ B, and B $\implies$ C, then A $\implies$ C
- Acting
  - Like a human
  - rationally





### Intelligent Agents

> **<u>Percepts/observations</u>** of the environment, made by sensors
>
> **<u>Actions</u>** which may affect the environment, made by actuators
>
> **<u>Environment</u>** in which the agent exists
>
> **<u>Performance measure</u>** of the desirability of environment states



- Agent as functions
  - Agent is a function from percept sequences to actions
  - Ideal rational agent would pick actions which are expected to maximise its **<u>performance measure</u>**
    - Based on the percept sequence and its build-in knowledge



### Agent type

- Simple reflex agents
  - ![image-20190619102459841](assets/image-20190619102459841.png)
  - These agents select actions on the basis of the **<u>current percept</u>**, ignoring the rest of the percept history.
  - It is simple but very useful in some cases.
  - pseudocode translation
    1. Find the current state
    2. Find the matched rule
    3. Return the action defined by the matched rule
  - Limitations
    - Works on if the environment is fully observable.
    - Since it does not have memory, it is very hard to tell, for example, the car is turning right or left.
- Model-based reflex agents
  - ![image-20190619112916296](assets/image-20190619112916296.png)
  - Keep track of the part of the world it can't see now.
    - Agent should maintain some sort of internal state that depends on the percept history reflects at least some of the unobserved aspects of the current state.
  - We need
    1. Some information about how the world evolves independently of the agent
    2. Some information about how the agent's own actions affect the world
  - Pseudocode translation
    1. Use the most recent state info and action it does, combining with the current percept and model it has to determine the current state.
    2. Find the rule based on current state
    3. Return the action defined by the current rule
  - Limitations
    - Uncertainty about the current state may be unavoidable but the agent still has to make a decision

- Goal-based agents
  - ![image-20190619113028741](assets/image-20190619113028741.png)
  - Knowing the current state is not enough, the agent needs some sort of goal information that describes situations that are desirable.
  - It involves the consideration of future.
  - Although it is less efficient, it is more flexible because the knowledge that supports its decisions is represented explicitly and can be modified.
    - We don't need to rewrite the model if the outside world shifted.
- Utility-based agents
  - ![image-20190619113007408](assets/image-20190619113007408.png)
  - Goals alone are not enough to generate high-quality behavior in most environments.
    - We want to measure how happy is our customer.
    - Traving in a much longer router could also make our customers reach the destination, but they might not be vary happy.
  - Also useful when,
    - There are conflicting goals, only some of which can be achieved (for example, speed and safety), the utility function specifies the appropriate tradeoff.
    - Thereare several goals that the agent can aim for, none of which can be achieved with certainty, utility provides a way in which the likelihood of success can be weighed against the importance of the goals.
      - It guarantee that it will choose the way that most likely leads us to success.



### Environment Types

|   Positive    |              Negative               |
| :-----------: | :---------------------------------: |
|  Observable   | Partially Observable/Non-observable |
| Deterministic |    Non-deterministic/Stochastic     |
|   Episodic    |             Sequential              |
|    Static     |               Dynamic               |
|   Discrete    |             Continuous              |

- Observable
  - Percept contains all relevant information about the world
- Deterministic
  - Current state of the world uniquely determines the next
- Episodic
  - Only the current or recent percept is relevant
- Static
  - Environment doesn't change while the agent is deliberating
- Discrete
  - Finite number of possible percepts/actions