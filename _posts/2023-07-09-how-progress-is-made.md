---
title: How Progress is Made
date: 2023-09-06
tags: [progress, AI, philosophy, science]     ## TAG names should always be lowercase
pin: true
math: true
mermaid: true
image:
  path: /assets/img/wiisports.png
  lqip: /assets/img/wiisports_lqip.png
  alt: Screenshot of the Wii Sports (Version 1.0) Nintendo Wii game
---

>This article is long. If you don't have time to read it all at once, I split it into three parts
of 10-15 minutes each. You can read them independently, but I recommend reading them in order.
{:.prompt-info }

- [Part 1: Introduction, Definition of Progress, Episodic vs Continuous Tasks](#part-1-introduction-definition-of-progress-episodic-vs-continuous-tasks): In this part, I introduce a framework for understanding progress and discuss the differences between episodic and continuous tasks.
- [Part 2: Progress by search, structure of search spaces, why induction works](#part-2-progress-by-search-structure-of-search-spaces-why-induction-works): In this part, I discuss the different search methods that lead to progress and why they work.
- [Part 3: The role of tools, collaboration, and culture in progress](#part-3-the-role-of-tools-collaboration-and-culture-in-progress)

## Part 1: Introduction, Definition of Progress, Episodic vs Continuous Tasks

### Introduction: Speedrunning as a playground to understand progress

A few weeks ago, I was lying in the couch with my girlfriend doing some pre-sleep binge-watching of YouTube videos. We were about to go to sleep when a wild 45 minutes video titled [*The History of Wii Sports World Records*](https://www.youtube.com/watch?v=NscWoJVrEfw) from the channel [*Summoning Salt*](https://www.youtube.com/channel/UCtUbO6rBht0daVIOGML3c8w) appeared in my recommendations. I decided to give it a go. My girlfriend of course fell asleep, but I stayed up late, mesmerized by the most boring topic I could imagine: **a documentary about the history of Wii Sports speedrunning**. I didn't
even know that you could speedrun Wii Sports (seriously, wtf?). Anyway, I'm not going to talk about the video here, but I must say, Summoning Salt's videos are exceptional. I believe if you check them out, you'll get a clearer picture of what I'll try to convey in this article.

>A **speedrun** is a play-through of a video game with the intention of finishing the game it as fast as possible. Speedruns are usually performed in games that have a clear end goal, like defeating the final boss or completing all the levels. It's generally a well defined task with a clear metric to measure progress: **time**.
{:.prompt-info }

The videos of Summoning Salt follow always a similar structure: 
1. He starts by introducing the game and the rules for the speedrun.
2. He then goes through the history of the speedrun, starting from the first world record and going through all the different developments that lead to the current world record: new strategies, improvements in execution, etc.

I think these videos offer a very global picture of how "how progress happens" for a complex task in a global environment with multiple optimizing agents. Often, discussions around optimization and search focus mainly on specific tools and algorithms. However, a global perspective that discusses the interplay of various elements and factors is rarely explored. Now that we are starting to see the birth of systems that have a non-trivial level of generality and agency, I think this debate is more relevant than ever. Let's dive into it and take a look at the different elements that contribute to progress:

- **Exploration of the search space**: The search space is the set of all possible solutions to a problem. In speedrunning, the search space is the set of all possible ways to complete the game. For most 
games, this is practically an infinite set. How do players explore this space? How do they find new ways of completing the game with a better time? How do they construct these complicated strategies that only work when executed in perfect synchronization? It's obviously more than just random trial and error.

- **Generally intelligent agents**: If you ever programmed any Reinforcement
Learning agent for gaming, you generally start with a blank slate: a function
with random parameters that is refined using reward signals to tweak these
parameters. In contrast, speedrunners aren't simply an array of random values
reacting to numeric scores. They're humans with pre-existing knowledge about the
world and video games. This information is stored sparsely in the neural
networks that make up their nervous systems that is a product of mainly two
things: an evolutionary process that has shaped the human brain over millions of
years, and the influence of the environment during their lifetime. Somehow, this
system is able to generalize this information to generate a model of the game
they use to make predictions about the consequences of their actions. This
enables them to construct strategies that exploit the game's mechanics to their
advantage. And these models are updated by new experiences, either from their
own play-throughs, from watching other speedrunners, or from any other source of
information they acquire through their senses. Several questions arise: How they
transform their prior knowledge into a model of the game? Why does this even
work in the first place? How do they use this model to construct strategies? How
do they update this model with experience?

> An example of generalization is the following. In the classic Montezuma's
Revenge game there are some pixels representing ladders. If you give this game
to a 7 year old kid from the 80s that never played a video game before, he will
probably identify that you can use the ladders to go between levels before even
trying to use them. This is because he has seen ladders in real life, he
identifies the similarities with the pixels in the game, and he performs an
inductive inference associating the properties of the real life ladders to the
game ladders. And this inference works because the developers of the game happen
to live in the same world as the kid and share a common understanding of what a
ladder is and how it's typically used. On the other hand, a vanilla RL agent
can't possibly infer the properties of the ladder from the pixels without
exploration, since it doesn't have any pre-existing knowledge to generalize
from. {:.prompt-info }

![Montezuma's
Revenge](/assets/img/how-progress-is-made/montezuma.png) 

- **Competition**: Speedrunners generally compete among themselves to get the best time. Speedrunners usually try to improve until they reach the world record. Once they reach it, they usually stop playing the game. The incentive is mostly honor and recognition, which sometimes is linked to monetary rewards in the form of donations or sponsorships. This competition plays a non-trivial role in accelerating progress. Why do speedrunners compete in the first place? How does competing help them get better? And why is competition so important for progress?

- **Communication and collaboration**: Speedrunners must provide a video of their play-through to validate their records. The community then reviews this video to confirm the record's legitimacy. This process is essential for fostering progress. By requiring speedrunners to share their strategies in detail for verification, it enables other speedrunners to learn and build upon this knowledge. This level of openness isn't always seen in other fields, such as when private companies, like withhold specific details about their technology (e.g., OpenAI not disclosing the details behind GPT-4). Why does this communication contribute to progress? And how crucial is this step in driving advancement?

- **Refinement**: Speedrunners spend a lot of time refining their skills. They practice specific parts of the game over and over again until they master them. They essentially fine-tune their motor skills to perfection. This is a meta-optimization process that happens on top of the optimization process of finding the best strategy. How does the nervous system adapt to improve the execution of a strategy? Is this process similar to the process of finding a strategy?

- **Tools and infrastructure**: Speedrunners use and develop tools to help them improve their performance. For example, they use software to record their play-throughs and analyze them frame by frame to identify mistakes and areas of improvement. They also use software to analyze the game's code to find glitches and exploits. This cumulative process of developing tools and infrastructure is essential for progress, since it allows agents to explore the search space more efficiently. 

In this article, I'll try to answer some of these questions and provide a framework for understanding progress. The goal is to gain insights that can be exploited to accelerate progress in targeted domains, similar to how the results of game theory can be used to design system rules that incentivize certain outcomes.
 
### Definiton of progress

**Progress must always be defined in relation to a specific task, coupled with a metric we aim to optimize**. For example, in speedrunning, progress occurs whenever a new world record is set. Without a quantifiable pair of goal and metric, *progress* becomes little more than a buzzword. Politicians often exploit this term, leaning on its shared meaning among us, even though the goals and metrics each of us optimizes for may vary significantly from one another—and likely from what a political party might consider as progress. Whenever you hear the word *progress* you must ask yourself: *progress towards what?*.

Said more formally, **progress constitutes an improvement in performance for a specific optimization task**. Many might argue that this definition of progress is somewhat unconventional. Conventionally, progress is perceived as the act of reducing the distance—in some metric space over the configuration space of a system—between a system's current configuration and a desired one. In simpler words: if you are in a race, you progress if you move closer to the finish line. However, this is just a special case of an
optimization task, aiming to minimize the distance to the goal. In many cases, the
goal is not bounded (e.g. the goal of increasing life expectancy in a society) so
the optimization frame is more appropriate. But essentially, it's the same thing.

### Episodic vs continuous tasks

Once we agree on what we mean by progress, we need to define what we mean by optimization tasks. In general, there are two types of optimization tasks: **episodic** and **continuous**. 

#### Episodic tasks

These tasks deal with **systems that can be reset to an initial configuration**. In these cases, an strategy $s\in S$  is applied to solve a task $T$, and the performance metric $M_T : S \rightarrow \mathbb{R}$ is measured at the end of the episode to estimate the performance of $s$ in $T$. For an episodic task, **progress occurs when we find a new strategy $s_{i} \in S$ that improves the performance metric over all the previously known strategies $s_{j} \in S_{\text{known}} \subset S$**. Here, $S$ is the set of all possible strategies (which might or might not be infinite).

In general, there's not a one-to-one correspondence between a strategy and the performance metric. In most cases, the performance is a probabilistic function of the strategy. For example, a deterministic strategy for playing Blackjack (e.g., ask for a card if the sum of the cards is less than 17) won't always yield the same result due to the randomness introduced by the shuffling of the deck. So, it's better to talk about the *expected performance* of a strategy. In the case of Blackjack, we can define the expected performance as the average amount of money we win or lose over a large number of games played with the same strategy. So, to be general, we should say that progress occurs when we find a new strategy $s_{i} \in S$ that improves the expected performance metric over all the previously known strategies. Nonetheless, **we can always, redefine the performance metric to be the expected value of the metric for a given strategy**, this is 
$M_T^{\text{new}}(s) = \mathbb{E}[M_T]_{s}$, and therefore keep dealing with deterministic metrics.

>Readers familiar with reinforcement learning might be used to the term "policy" and the notation $\pi$ instead of "strategy" and $s$. However, while these two terms are largely interchangeable, I prefer 'strategy' in this article. It's more intuitive for a general audience and less strongly associated with Markov decision processes, a more constrained type of optimization task.
{:.prompt-info}

##### Examples of episodic tasks

Let's look at some varied examples of episodic tasks to get a better understanding of the framework I'm trying to construct.

###### 1. Blackjack
- **Task**: Play Blackjack.
- **Strategy**: An algorithm that tells us what to do in every possible situation. For example, if we ignore splitting and the nitpicky details of the game, we can define any deterministic strategy as a function $s: \mathbb N \rightarrow \\{\text{hit}, \text{stand}\\}$, where $\mathbb N$ is the set of all possible sums of cards we can have in our hand. For instance, we can define $s$ so that $s(n < 17) = \text{hit}$ and $s(n \geq 17) = \text{stand}$, where $n$ is the total sum of our cards.
- **Performance metric**: The expected amount of money we win or lose over a large number of games played with the same strategy $s$. We can define this quantity as $\mathbb E[M]_{s}$, where $M$ is the amount of money we win or lose in a single game (assuming a fixed bet size).


###### 2. Chess

- **Task**: Play chess against a random pool of opponents.
- **Strategy**: In chess, a strategy can be conceptualized as a [Turing machine](https://en.wikipedia.org/wiki/Turing_machine) that accepts the current state of the board as input and produces a legal move as its output. The entire strategy space $S$ is practically infinite due to the many sequences of moves possible. However, in developing models or algorithms to play chess, we choose *representations* of the strategy space. These representations either cover a smaller, more manageable subset of $S$, making them more tractable from a search perspective (e.g., rule-based strategies or tree search algorithms), or they possess desirable mathematical properties like differentiability (e.g., neural networks) that enable interesting optimization methods like gradient descent.

- **Performance metric**: An example of a performance metric often used in chess is the Elo rating. The Elo rating system quantifies a player's/strategies skill level based on their past game outcomes against other players/strategies. The difference in ratings between two players/strategies is intended to serve as a predictor of the expected result of a match. The Elo rating of a strategy can be determined after a long series of games against a random pool of opponents that is assumed to be constant. It's worth noting, however, that in real-life chess, the pool of opponents isn't static; it evolves over time as new strategies emerge and newer engines are developed. In that case, the problem ceases to be episodic and becomes continuous.

>In the context of chess, one can envision a human player as a computer that processes the scattered photons from the board to reconstruct the state of the board, and through a series of synaptic connections and chemical reactions, produces a legal move. In this scenario, the complete molecular configuration of the player's brain represents the strategy.
{:.prompt-warning}

##### Progress in episodic tasks is a search problem

In episodic tasks, progress is achieved by finding a new strategy that improves the performance metric over all the previously known strategies. In other words, progress is achieved by searching for a better strategy. So talking about progress, optimization, and search in episodic tasks is essentially the same thing.

1. **What are we dealing with?** 
   - We have a big set of strategies, which we'll call $S$.
   - Each strategy has a performance score, given by $M_T(s)$.

2. **What's our goal?** 
   - We want to find the best strategy, $s^*$, which has the highest score. Mathematically, this is:
$$s^* = \arg\max_{s \in S} M_T(s)$$

3. **What's the challenge?**
   - We don't know the scores for all strategies upfront. We have to test or calculate the performance of each strategy.
   - This strategy set, $S$, can be very large, oftentimes infinite, making it impractical to check every single strategy.

4. **How do we search?** 
   - In general, it depends on the task, the structure of $S$ and the resources available. In the [Part 2](#part-2-progress-by-search-structure-of-search-spaces-why-induction-works) of this article, I discuss this topic in more detail.


#### Continuous tasks

Continuous tasks involve systems that **cannot be reset to an initial configuration**. In these tasks, the system evolves uninterruptedly over time, and actions taken can influence future states and outcomes. This poses a challenge when defining progress, since the definition of progress in episodic tasks is not applicable since we can't reset the environment to an equivalent state to compare strategies.

##### Actions over strategies

While a continuous task could technically be framed as a single episode of an episodic task, this viewpoint is not particularly insightful. In continuous tasks, it is more accurate to consider strategies as evolving processes that adapt over time. Instead of deploying an entire strategy at once, we execute a sequence of actions $a \in A$, with each action affecting the future state of the system. In this context, a strategy $\sigma$ is a rule or set of rules that determines the appropriate action $a$ at each time step $t$. Thus, our strategy $\sigma : X \rightarrow A$ is a function mapping the system's state $x_t \in X$ to actions $a_t \in A$. This mapping may be deterministic or stochastic. The system's evolution $X$ can vary widely. While it is common to model the system's evolution $X$ as a [Markov process](https://en.wikipedia.org/wiki/Markov_process) and the strategy $\sigma$ as a policy within a [Markov decision process](https://en.wikipedia.org/wiki/Markov_decision_process) (MDP), this simplifies the complexity of many real-world systems, which often exhibit non-Markovian dynamics. For instance, societal systems involve humans whose memories affect their decisions. Additionally, observations in dynamic environments are frequently time-correlated, meaning that even if the underlying system is Markovian, the observations may not be.

>Note that we are using the word *strategy* in a different sense than in episodic tasks and hence the different notation. The main difference is that the **continuous strategies** $\sigma$ can be modified during the course of the task (and often are), while the **episodic strategies** $s$ are fixed for the whole episode. The strategy $s$ of an episodic task is more general, in the sense that we could always consider episodes as singular instances and frame them as independent continuous tasks. Nonetheless, this is rarely useful since the information obtained by repeating the task is extremely valuable when choosing the strategy $s$.
{:.prompt-info}

##### Performance metric in continuous tasks

Unlike episodic tasks where performance is measured at the end of an episode, continuous tasks require ongoing optimization, as they do not offer the opportunity to reset and retry. This necessitates a performance metric that can be evaluated in real-time as the system evolves.

Typically, the performance metric is a function that considers the history of the environment up to the current point in time, denoted mathematically as $R: X^{t} \rightarrow \mathbb{R}$, where $X^{t}$ is a sequence of states $\\{x_0, x_1, \dots, x_t\\}$ up to time $t$. The objective is to influence the system's evolution through actions that bring the performance metric $R$ closer to a target value $R_\text{goal}$. Progress is made when a new measurement of $R$ is closer to $R_\text{goal}$ than the previous measurement.

For example, consider the task of controlling a room's temperature. We could
define the performance metric as the difference between the current temperature
$T(t)$ and the desired temperature $T_\text{goal}$, expressed as $R(t) =
|T_\text{goal} - T(t)|$. The goal is to achieve $R = 0$, indicating that the
current temperature matches the desired temperature. Progress is made whenever
$R$ decreases. 

However, this simple metric may lead to issues. For example, if the room is 1
degree cooler than $T_\text{goal}$ and the heater is activated, the temperature
will rise, which seems like progress. Nonetheless, t's usual that heating
systems have some delay between the activation signal and the power being
delivered to the room. So, if the heater is turned off only when the temperature
reaches $T_\text{goal}$, the temperature will continue to rise and exceed
$T_\text{goal}$, resulting in a deviation in the opposite direction. Ideally,
the heater should be turned off before the temperature reaches $T_\text{goal}$
to prevent overshooting. This illustrates a common challenge in continuous
optimization tasks: balancing immediate progress with long-term stability. To
address this, the performance metric can be refined to include not just the
current temperature difference, but also the rate of change and the cumulative
error over time. Those familiar with control theory will recognize these as the
proportional, integral, and derivative terms in a PID controller.

##### Examples of continuous tasks

###### 1. **Room temperature control**

- **Task**: Maintain the temperature of a room at a desired temperature $T_\text{goal}$.
- **Strategy**: A strategy $\sigma$ might dictate the specific conditions under
  which a heating or cooling system gets activated. For instance, when the
  temperature is below a certain threshold, the heater could be turned on, and
  when it's above another threshold, the AC might be activated. Such a strategy
  can be defined as:

    ```pseudocode
    if  T < T_goal - delta:
        Turn heater ON
    if T > T_goal + delta:
        Turn AC ON
    else:
        Do nothing
    ```

    Here, `delta` is a small margin around the desired temperature to prevent the system from toggling the AC/heater too frequently.

- **Performance metric**: A straightforward performance metric for this task
  would be the difference between the current room temperature $T(t)$ and the
  desired temperature $T^*$, expressed as $R(t) = |T_\text{goal} - T(t)|$.
  However, considering the problems of overshooting and short-term vs long-term
  optimization, a more sophisticated metric that factors in the rate of
  temperature change and the past performance (to prevent oscillation) might be
  appropriate. Such a metric might look like:

    $$ R(t) = \alpha |T_\text{goal} - T(t)| + \beta \frac{d}{dt} (T_\text{goal} - T(t)) + \gamma \int_{t-\tau}^{t} |T_\text{goal} - T(y)| dy$$
    
    where $\alpha$, $\beta$, and $\gamma$ are weighting coefficients, and $\tau$
    is a time window over which past performance is considered. We can see that
    the example strategy above would not perform optimally with this metric,
    since it doesn't consider the rate of change or past performance.

###### 2. **Portfolio management in the stock market**

- **Task**: Invest in a portfolio of stocks to maximize returns.
- **Strategy**: An strategy would dictate how to allocate funds among different assets over time. However, crafting a strategy for the stock market is complex because is the product of the interplay between countless economic entities shaped by billions of humans. Some rely on inductive reasoning, analyzing historical data for patterns, while others use world models or trust their intuition, essentially a form of brain-based pattern recognition. 

- **Performance metric**: The performance metric is usually the return on investment (ROI) over a given time window. For example, if we invest $1000$ dollars in a portfolio and after a year, we have $1200$, then the ROI is $20\%$. However, this method is not very precise since fluctuations and luck can deceive us when evaluating the performance of a strategy. As with the room temperature control, introducing an average of the ROI over the time window (essentially, the integral term) can help us get a more accurate picture of the performance of a strategy.

###### 3. **Increasing life expectancy in a society**

- **Task**: Enhance the overall health and living conditions of a society to increase life expectancy.
- **Strategy**: Strategies might encompass various public health initiatives, awareness campaigns, and investment towards the development of medical technology. The strategy space is vast and complex and cannot be defined with a computer program. Usually, institutions in charge of this task summarize ambiguous but directional principles to guide concrete actions that can be implemented by executing agencies. One of the main difficulties of this kind of tasks is that the environment is so complex and non-reproducible that it's hard to determine the impact of a particular strategy. For example, if a government invests in a new hospital, it's hard to determine how much of the increase in life expectancy is due to the hospital and how much is due to other factors, like the development of new technologies. This is a common problem in continuous tasks. 

- **Performance metric**: the primary metric would be the average life expectancy of the population over a specific time frame. However, life expectancy alone might not give a complete picture of society's health. Hence, metrics that factor in the quality of life, such as Disability-Adjusted Life Years (DALY) or Quality-Adjusted Life Years (QALY), would be more indicative. Combining these metrics can offer a more comprehensive understanding of the overall health and well-being of a society.

##### Progress in continuous tasks can't be defined as a search problem

In search problems, we assume the ability to independently test different candidate solutions or strategies. This allows valid comparisons between strategies to determine which performs best. We can isolate the effect of each strategy through replication - by resetting the system to its initial conditions and rerunning the same strategies multiple times.

However, in continuous tasks, **independent replication is not possible**. This makes it impossible to systematically search the strategy space or to verify with certainty that a given strategy leads to better results independent of other factors. Comparing strategies becomes an "apples to oranges" 
problem since their contexts continually diverge.

Also, it means the performance and outcomes of different strategies cannot truly be attributed to the strategies themselves. The effects of a strategy are not isolated but rather intertwined with the effects of other strategies and the environment itself. This makes it very difficult to attribute a causal relationship between a strategy and its outcomes.

##### Progress in continuous tasks is a prediction + search problem

If progress in continuous tasks cannot be defined as a search problem, how then
can we approach it? The key is to obtain **predictive models** of the system
that enable us to estimate the impact of our actions. This allows us to search
without actually performing the actions, and thus solve the problem of independent
replication.

Some key aspects of progress in continuous tasks are:

- We can no longer isolate the effects of individual strategies. Instead, our
  focus shifts to modeling the response of the system to our actions.

- Even though we can't apply search methods directly, we can still search using
  the estimated performance of our predictive models.

- Performance is evaluated based on how well our actions steer the online
  optimization process over time.

- Progress is made incrementally as our models continuously assimilate new
  experience to enhance predictive accuracy.

Is not a coincidence that the biggest increase in progress in all areas of human
life has happened in the last 300 years, which coincides with the development of the
scientific method. The scientific method is essentially a process of building
models of the world and using them to make predictions. The more accurate our
models, the better our predictions, and the better actions we can take to
optimize whatever we're trying to optimize.

##### Blurry lines between episodic and continuous tasks

The distinction between episodic and continuous tasks is not always clear.

Sometimes, inherently continuous tasks are framed episodically. This is often
done to simplify the problem and make it more tractable. For example, the [Car
Pole](https://gymnasium.farama.org/environments/classic_control/cart_pole/)
balancing problem is a continuous task, but it's often framed episodically by
limiting the number of steps to a fixed number or assigning a terminal state.
This allows to use powerful search methods to find the best strategy, often
requiring millions of episodes since the search space large. However, in most
situations, this is not a realistic approach. In the real world, we can't reset
the environment and try again. Or if we can, we are constrained by the number of
times we can do it.

Conversely, there are situations where episodic tasks demand adaptive
strategies. In chaotic environments, even with the capability to reset,
outcomes can fluctuate dramatically due to minor variations. Such
unpredictability can render search-based methods ineffective. In these
situations, predictive models become useful. For example, in the Wii Sports
speedrun video that I talked about at the beginning of this post, a player
discovered that by removing and then reinserting the batteries of the Wii remote
during a golf swing, the game erroneously allows the player to hit on the ball
again. Such a glitch could not be exploited through random experimentation since
the chances of concatenating the right sequence of actions by chance are
effectively zero. It requires an underlying model of the game's mechanics that
enables to estimate the outcome of unconventional, sequential hypothetical
actions. This allowed the player to plan how to use the glitch to bypass
obstacles, like a lake, in a way that would be impossible find through episodic
search.


#### Summary of Part 1

- **Speedrunning** offers a fascinating lens through which to study how progress is made, featuring a competitive environment, exploration of vast search spaces, implementation of strategies, refinement of skills, collaboration, communication, and the use of tools and infrastructure.

- **Progress** is defined in relation to a specific task and a metric that is being optimized. A clear goal and metric are essential to prevent the term "progress" from becoming ambiguous or meaningless.

- **Episodic tasks** are those in which the system can be reset to an initial configuration, allowing strategies to be independently tested and compared based on a performance metric. Progress in episodic tasks involves a search for new strategies that outperform the existing ones, and tools like models, simulations, and heuristics help navigate the large search space of potential strategies.

- **Continuous tasks** do not allow the system to reset, making it challenging to compare different strategies directly or attribute outcomes to specific actions. Progress in continuous tasks thus requires developing predictive models of the system to estimate the impacts of actions and guide decision-making. The scientific method is our best tool for creating accurate models and making informed actions in continuous tasks.

- The distinction between episodic and continuous tasks is not always clear-cut. Sometimes, continuous tasks are framed episodically for simplification, and vice versa—episodic tasks may be approached with adaptivity when faced with chaotic and complex environments.


## Part 2: Progress by search, structure of search spaces, why induction works

### Progress by search 

Now that we have a clear understanding of the different types of tasks, we can
discuss the **search methods** that lead to progress. A particularly interesting
read on this topic is [The Bitter Lesson](http://www.incompleteideas.net/IncIdeas/BitterLesson.html).
In this article, Rich Sutton argues that the most important lesson that can be 
drawn from the history of AI is that **general methods that leverage computation
are ultimately the most effective**. This is specially relevant in the context
of search based progress.

In this section, I'll present an informal classification of search methods that
lead to progress. This classification is not exhaustive, but I hope it transmits
the main ideas behind each method. There are countless books written about optimization
methods, so I won't go into the details of each method. Instead, I'll focus on
the general ideas behind each method, provide a few examples, and discuss why and
when they work.
#### Exhaustive search

This is the most straightforward search method. It consists of testing every single
strategy in the strategy space $S$ and selecting the one that performs best.

Obviously, this method is only feasible for small strategy spaces. For example, in 
a small town with few roads, we can test every possible route to find the shortest
one. However, as the number of roads increases, the number of possible routes explodes
superpolynomially, and the exhaustive search becomes infeasible (this is known as the
[traveling salesman problem](https://en.wikipedia.org/wiki/Travelling_salesman_problem)).

#### Random search

Random search involves randomly selecting candidate solutions from the strategy
space $S$ and evaluating their performance. It does not rely on any information
about previously evaluated solutions.

While this method may seem naive, it can be surprisingly effective in
high-dimensional strategy spaces where gradient information is unavailable or
unreliable. 

It's in fact optimal for problems in which the search space has no structure. But, what does it mean for a search space to have no structure? This is a term that you often hear in the context of optimization, but I've never seen it formally defined. I'm sure there are hundreds of formal papers about this topic, but I'm a physicist and don't know them. So, I'll try to define it here. What I'll present is not a formal definition, it will be sloppy math at best, but I think it will be "nice" 
to provide some intuition about the concept. If you know a formal definition of an unstructured search space, please let me know in the comments.


#### Structure of search spaces

We say that the strategy space $ S $ possesses a "structure" with respect to $ M_T $ if there exists a 
statistical dependency among the performances $ M_T(s) $ for $ s \in S $. Formally,
this can be captured by the notion of mutual information.

Let $ X $ and $ Y $ be random variables representing $ M_T(s_i) $ and $ M_T(s_j) $ for $ s_i, s_j \in S $ and $ i \neq j $. Then $ S $ is said to lack structure if and only if 

$$
I(X; Y) = 0, \quad \forall s_i, s_j \in S, i \neq j,
$$


where $ I $ is the [mutual information](https://en.wikipedia.org/wiki/Mutual_information) between two random variables.

In cases where there's no structure it's straightforward to see why random search can be an effective method, since any systematic approach that tries to infer the performance of one strategy based on another will be futile. Instead, uniformly sampling strategies from the search space is as good as any other method.

Let me illustrate the idea with the following optimization problem. We have a grid of 20x20 pixels, with values ranging from 0 to 255, 0 being black and 255 being white. We are interested in the coordinates of the brightest pixel. To get the brightness of a pixel, we can call a function $M(x, y)$ that returns the brightness of the pixel at coordinates $(x, y)$. So in this case, our strategy space is 
$S = \\{(x, y) \in \mathbb{N}^2 | 0 \leq x, y \leq 19\\}$, and our performance metric is the brightness $M(x, y)$.

Now imagine we have 3 different grids. 

- **Grid 1: Single white pixel** All pixels are black except for one, which is white.

![Grid of 20x20 pixels](/assets/img/how-progress-is-made/grayscale_grid_one.png)

- **Grid 2: Uniformly distributed pixels**
 The brightness of each pixel is randomly sampled from a uniform distribution between 0 and 255.

![Grid of 20x20 pixels](/assets/img/how-progress-is-made/grayscale_grid_uniform.png)

- **Grid 3: Normally distributed pixels** The brightness of each pixel is randomly sampled from a Gaussian distribution with the origin at a random point in the grid.


![Grid of 20x20 pixels](/assets/img/how-progress-is-made/grayscale_grid_gaussian.png)



From these grids, can you tell which one has no structure? How would you find the brightest pixel knowing that you can only call the function $M(x, y)$ to get the brightness of a pixel one at a time?  Please take a moment to think about it before continuing the article, since it's a good exercise to understand the concept of structure in search spaces.

##### Grid 1: Single white pixel

This grid possesses structure. In this case, there exists a unique $ (x_{\text{max}}, y_{\text{max}}) $ such that $ M(x_{\text{max}}, y_{\text{max}}) = 255 $, while $ M(x, y) = 0 $ for all other $ (x, y) $. Here, $ I(X; Y) \neq 0 $ because knowing $ M(x, y) $ for one $ (x, y) $ gives full information about $ M(x', y') $ for all $ x' \neq x $ and $ y' \neq y $.

Nonetheless, note that structure may not offer any advantage, since in this case no
strategy can improve the time complexity of exhaustive search.

> **Interesting fact**: [Grover's algorithm](https://en.wikipedia.org/wiki/Grover%27s_algorithm) is a quantum algorithm that can find the brightest pixel in a grid of size $N$ in $\mathcal{O}(N)$ steps, assuming we can evaluate the performance metric $M(x, y)$ with a quantum oracle (which is rarely possible). This is a quadratic speedup over the $\mathcal{O}(N^2)$ steps required by exhaustive search.
{:.prompt-info }

##### Grid 2: Uniformly distributed pixels

This grid has no structure. The value of each pixel is independently and uniformly sampled from the range $[0, 255]$. Let $X$ and $Y$ be defined as before, by definition of the grid $P(X,Y) = P(X)P(Y)$, and therefore $I(X; Y) = 0$. 

If the search space has no structure, then random or exhaustive search are as good as we can get. It doesn't matter what method we use: as long as we don't repeat strategies, all strategies are equally likely to find the brightest pixel in a given number of trials.


##### Grid 3: Normally distributed pixels 
In Grid 3, pixel brightness follows a Gaussian distribution centered at a specific point $(x_{\text{center}}, y_{\text{center}}) $ and governed by $b(x, y) \sim \mathcal{N}(\mu, \sigma^2) $, where $\mu(x, y) = A \exp\left(-\frac{(x-x_{\text{center}})^2 + (y-y_{\text{center}})^2}{2\sigma^2}\right) $. The mutual information $I(X; Y) $ between any two pixel brightness values $M(x_1, y_1) $ and $M(x_2, y_2) $ is non-zero for nearby pixels due to this Gaussian structure. Thus, the search space possesses structure, enabling optimization techniques like hill-climbing to efficiently locate the maximal brightness.

In the following figure you can see the path taken by a high-climbing method to find the brightest pixel in Grid 3. The yellow dot is the starting point, the red dots are the nodes the algorithm picked for checking the value of the pixels around, the blue dots are the explored pixels, and the green dot is the brightest pixel found.

![Grid of 20x20 pixels](/assets/img/how-progress-is-made/hill_climbing.png)
##### Structured Nature of Complex Search Spaces

Consider the Traveling Salesman Problem (TSP), which involves finding the shortest route through
$N$ cities. While the optimal path might be complex to describe—I think $\sim \log{n!}$ in terms of [Kolmogorov complexity](https://en.wikipedia.org/wiki/Kolmogorov_complexity)—the search space is not uniformly random. Instead, there's a form of 'useful redundancy' (i.e. mutual information). For instance, if two cities are geographically close, any optimal or near-optimal solution is likely to visit them consecutively. You can quantify this by observing the distribution of total distances when you swap two adjacent cities in an otherwise fixed route. Typically, such a change results in a small variation in total distance, indicating that 'nearby' solutions in the search space also yield 'nearby' outcomes.

Let's explore this in more detail with a concrete example. Below you can observe the solution provided
by a simple monotonic hill-climbing algorithm for the TSP of 300 randomly located cities. The algorithm starts with a random route and then iteratively swaps two adjacent cities and keeps the swap that results in the shortest route. The algorithm stops when it can't find a better route after a certain number of iterations.

![Traveling Salesman Problem](/assets/img/how-progress-is-made/TSP.png)

> The Hamming distance between two strings of equal length is the number of positions at which the corresponding symbols are different. In other words, it measures the minimum number of substitutions required to change one string into the other. In this case, we can express the route as a sequence of cities, where each city is represented by a number. For example, the route $[1, 2, 3, 4]$ means that the first city visited is city **1**, the second city visited is city **2**, and so on. The Hamming distance between two routes is the number of cities that are in different positions in the two routes. For example, the Hamming distance between $[1, 2, 3, 4]$ and $[1, 3, 2, 4]$ is 2, since the cities **2** and **3** are in different positions in the two routes.
{:.prompt-info }

Now, we can explicitly observe the structure of the solution space. First we need a way
to quantify the similarity between two solutions. A straightforward choice here is to use the [Hamming distance](https://en.wikipedia.org/wiki/Hamming_distance) between two sequences. Next, we sample random permutations of the optimal route and group them by their Hamming distance to our optimal solution. We then plot the average length of the routes for each group. The results are illustrated in the figure below:.

![Traveling Salesman Problem](/assets/img/how-progress-is-made/TSP_structure.png)

Interestingly, the graph shows that as the Hamming distance to the optimal solution increases, the average route length also increases until it matches the average length of a completely random route.

For a different example, an aircraft (which can be understood as the solution of
a problem that involves optimizing the distribution of atoms in space to achieve
a desired functionality). In a plane, swapping or slightly altering the position
of atoms in non-critical components like a seat cover will hardly impact the
aircraft's overall performance. In terms of search space, this means that
there's a cluster of similar, nearly-as-good solutions surrounding any optimal
configuration. Humans take advantage of this structure by using modular designs
that allow for an abstract compressed description of the aircraft. You don't
need to specify the exact position of every atom in the seat cover, you just
need to specify the type of material and the general shape. And this is possible
because the structure of the search space allows for it. If this were not the
case and you would need to specify the exact position of every atom, then it
would be impossible to design an aircraft.

In both these concrete cases, a key principle stands out: **small alterations to complex strategies often yield similarly effective results**. This isn't accidental. When a problem demands a high degree of complexity for its solution, the configuration space often manifests clusters of high-performing solutions that are closely related, thereby exhibiting high mutual information between them. **This is often needed to ensure robustness and fault tolerance that allows the strategies to perform correctly when slight alterations occur**. For example, if the layout of atoms in an aircraft were extremely sensitive to small perturbations, then the aircraft would be very fragile and prone to failure.

The innate structure of complex search spaces isn't just a mathematical curiosity; it's a key property that enables both natural and human-engineered systems to operate effectively and adaptively.

##### Exploiting Structure: Why Induction Works?

Imagine you are a toddler that never has seen an electrical stove. You touch the stove at one point and you burn. Wow. However, you are a curious kid and you touch again the stove in a different point. Burned again. You are starting to learn something. While you may not fully understand the underlying reasons, you’re intuitively picking up on a pattern: touching the stove leads to pain. This is the essence of induction: drawing general conclusions from specific observations.

The essence of inductive reasoning lies in leveraging the consistent structures present in our surrounding. This ability to recognize and learn from patterns has evolutionary advantages. In the case of our ancestors, recognizing that a particular rustle in the bushes typically led to a predator's attack helped in survival. So it's expected that the brain has evolved to use inductive reasoning.

From a Bayesian standpoint, induction stems from probabilistic reasoning. We commence with prior beliefs about the world and update these based on new evidence. Before the painful encounters with the stove, a toddler might have an equal expectation of pain or no pain upon touch. After the first and second burns, the belief that "touching the stove leads to pain" solidifies.

Now, a logical query could arise: isn't it plausible that only a few specific spots on the stove cause burns? Perhaps the toddler just happened to touch the only two points that burn. Well, this is possible, but it's not very likely. Given the multitude of
points on the stove's surface, the likelihood of coincidentally touching the only two that cause burns is quite low. Therefore, it's much more likely that a significant portion of the stove, if not all of it, burns when touched. Thus, it's a safer bet to assume that the majority, if not the entirety, of the stove's surface is hot. This rationale is a simplistic illustration of [Solomonoff's theory of inductive inference](https://en.wikipedia.org/wiki/Solomonoff%27s_theory_of_inductive_inference). It prioritizes simpler explanations over more complex ones, implying a correlation between the complexity of a hypothesis and the Bayesian probability of it being true.

Ok, but what does this have to do with exploiting structure in search spaces? The key idea is that **when a search space possesses structure, observations from one section of the space can offer insights about other sections**. This is because **we operate under the Bayesian assumption that it's more probable for the structure to be consistently spread across the entire space than for it to be confined only to the portion we've observed.**

##### Exploiting Structure: Local search



#### Zeroth order methods

#### First order methods

#### n-th order methods


## Part 3: Prediction, dynamics and combination of everything
### Progress by modeling

### The best progress is made by combining search and modeling
