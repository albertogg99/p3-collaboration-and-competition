[//]: # (Image References)

[image1]: resources/640px-Udacity_logo.svg.png
[image2]: resources/tennis.gif
[image3]: resources/config.png
[image4]: resources/training.png


### ![image1]
### Deep Reinforcement Learning Nanodegree
### Multi-Agent Reinforcement Learning | Project: *Collaboration and Competition*
### Author : Alberto García García

#

#### Introduction


The problem to be solved in this project consists in training two agents bouncing a ball over a net using rackets. 
The agents need to keep the ball in play, obtaining a positive reward of **+0.1** for every time they pass the ball over the 
net and a negative reward of **-0.01** when the ball hits the ground or goes out of bounds.

![image2]

The state space consists of 8 variables including information about the
velocity and the position of both, the ball and the racket of each agent. Notice that each agent receives its own local
observation. Furthermore, there are 2 continuous actions, corresponding to the horizontal movement of the racket (toward 
or away from the net) and jumping. 

#### Guidelines

The whole training of the agent is implemented in the [CollaborationAndCompetition.ipynb notebook](solution/CollaborationAndCompetition.ipynb). You can either visualize the last
execution or run it by yourself in a Jupyter server. To do so, you can take the following steps to fulfill the requirements:

1. Create (and activate) a new environment with Python 3.6.

   - Linux or Mac: 
	```bash
	conda create --name drlnd python=3.6
	source activate drlnd
	```
	- Windows: 
	```bash
	conda create --name drlnd python=3.6 
	activate drlnd
	```

2. Follow the instructions in [this repository](https://github.com/openai/gym) to perform a minimal install of 
OpenAI gym.
3. Install the dependencies in the `python/` folder.
   ```bash
   cd ./python/
   pip install .
   ```
4. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the `drlnd`
environment.  
   ```bash
   python -m ipykernel install --user --name drlnd --display-name "drlnd"
   ```
5. Download the Unity Environment and unzip it inside the `solution/` directory. If you are using Windows 64 bits, you can skip this step since the repository already contains the environment files. Otherwise, delete the environment files and place the ones matching your OS.
	- [Linux](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
	- [Mac OSX](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
	- [Windows (32-bits)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
	- [Windows (64 bits)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)   
6. Before running the notebook, change the kernel to match the `drlnd` environment by using the drop-down `Kernel` menu. 

   ![image3]


#### Results

The agent is able to solve the problem in 3395 episodes (averaging 0.5 points from episode 3395 to episode 3495). The weights 
of the actor networks of the agents are stored in [actor1.pth](solution/actor1.pth) and [actor2.pth](solution/actor2.pth), 
while the weights of the critic networks are stored in [critic1.pth](solution/critic1.pth) and [critic2.pth](solution/critic2.pth). 
A detailed description of the implemented algorithm can be found in [report.pdf](report.pdf). Here's the multi-agent's score history:

![image4]
