# AI-LunarLander

<h2>Research Papers for DQN and DDQN</h2>
<h3> DQN - https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf</h3>
<h3> DDQN - https://arxiv.org/abs/1509.06461</h3>

<h2>Lunar Lander</h2>
<p>Lunar landing is another classic Box2D openai gym game. The goal of this game is to land the rover inbetween the two flag poles. Every iteration, a new terrain
is spawned at random, so they won't be in the same position every single time. In order to solve this, an average score of 200 is needed, which is achieved
in just 30 episodes.</p>

<h2>Neural Network</h2>
<p> Since this game has 4 action spaces and 8 observation spaces, a bigger neural network is needed in order to compute the nodes effectively. The neural network
consists of 2 layers, 1 hidden layer and 1 output layer with each layer consisting of a size of 4 x 256, 256 x 512, 512 x 8. Another hidden layer overfits on the data and increasing / decreasing node size just increases instability.</p>

<h2>Hyperparameters</h2>
<p> Better scores can be achieved with fine tuning hyperparameters, but in this case I stuck with achieving a score of 200</p>
<p>GAMMA - 0.99<br>
Greedy Strategy - 1, 0.999 for decay - 0.01 for min<br>
Batch Size - 32<br>
Every 500 timesteps I updated my target network </p>


<h1>Lunar AI</h1>
<p> To begin, using the concept of explore vs exploit, the rover attempts different combinations of actions. Sometimes it crashes immediately or sometimes it just hovers for a while. However, after a certain amount of trial and error, the exploitation process begins since epsilon decreases to about 10%, meaning the AI
has a 10% chance of using a random action and the other 90% is calculated efforts sent by the Neural Network.</p>

![lunarStart](https://user-images.githubusercontent.com/41172710/183311620-82c386a1-ec87-403d-8051-7b1ed57c9cd7.gif)<br>

<p>As we can see in the previous gif, the rover is clumsy and crashes repeatedly for several episodes just like that, however after about 20 episodes, it starts to really pick up.</p>

![lunarEnd](https://user-images.githubusercontent.com/41172710/183311663-8af3d4cf-5630-4441-aa0d-393fdcef44e7.gif)

<br>

<h2>Analysis</h2>

<p>For this project, I decided to solely focus my efforts on double deep reinforcement learning since it's far more stable than just vanilla deep reinforcement learning. When I did use deep reinforcement learning there was far more instability after 30 episodes and the algorithm was overfitting and was extremely optimistic resulting in a lower overall score.</p>

<p>Using DDQN though, the AI achieved a far better score and much quicker as well.</p>

![lunarGraph](https://user-images.githubusercontent.com/41172710/183311746-af1ef745-bcd4-4f83-ae28-40a03434b6ec.png)
<br>

<p>In just 30 episodes the AI averages a score around 200 and hovers around it. In a regular DQN, the score would typically be around 175 at 75 episodes and go into the negatives shortly after.</p>
