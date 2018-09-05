
# Reinforcement Learning in "Mathnglish"

### **Alphabets of RL**
 * s -  States set 
 * a -  Action set
 * $\tau$ - A trajectory i.e a sequence of states and actions in certain episode.
 * $\ r(s_t,a_t)$ 
 
### Markov Chain
Named after [Andrey Markov](https://en.wikipedia.org/wiki/Andrey_Markov) a Russian mathematician, Markov chain deals with behavior of stochastic processes where the system is continuously transitioning among the states which come from well defined state space . Now the transition which is happening  at any given time step is only dependent the state we are currently in.This is called **Markov property**
At any given timestep we are intersted in knowing what is the distribution over the state space.There is a concept called transition matrix which is a square matrix where $a_{ij}$ represents the probaility of transitioning to state **i** **given** we are in state **j**. 
Hence to calculate the current distribution over states we can multiply our current  state distribution vector with the transition matrix i.e
			$\mu_{t+1} = T\mu_t$ .

 (For more detailed explanation - 
[Dissecting RL-1](https://mpatacchiola.github.io/blog/2016/12/09/dissecting-reinforcement-learning.html))

### Objective of Reinforcement Learning ?
Maximizing the expected sum of rewards , we will choose to represent rewards as       **r($s_t,a_t$)**  which denotes the reward we will get by executing action **a** while in state **s** at a certain timestep **t**.
A return  (sum of rewards) of trajectory is defined as  - 
							$r_{\tau  = }\sum_{t=1}^{n} r_t$	
								

$J(\theta)$   =   $E_{\tau \sim\pi}[r_{\tau}]$
read this as **expectation of the returns of trajectory when it has the distribution which is governed by our policy $\pi(\theta)$.**  If you think of it different preference over actions given some state will have different probabilities of the same trajectories, but return of a particular trajectory remains the same ,hence a good policy would be having maximum probabilities for good trajectories(the ones with maximum returns)!!

Acting greedily in the state you encounter on the go when following a certain policy is however tempting it is might  not be optimal because what if  a certain state which was to come after less optimal action(which we didn't choose) could have been our route to higher rewarding states ,hence we might also have preference of choosing some less optimal action (in terms of instant reward) which can actually lead us to states with higher rewards in future.This is called exploration -exploitation tradeoff and hence we always include a factor of exploration during the learning process to take random actions too. 

For this very same we need a better metric this is where Q(s,a) comes into the picture.



