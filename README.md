# Game AI: SMB

Simple AI project for Super Mario Bros.

## Table of Contents

- [Introduction](#Introduction)
- [Process](#Process)
- [Results](#technologies)
- [Technologies](#technologies)

## Introduction

Super Mario Bros. isn't the first electronic game, neither the first of it's genre, but for sure is the game that change the gaming industry forever. Released for the NES in 1985, Super Mario Bros. held the title of rank 1 best-selling game for more than 20 years and even after so much time it continues as the rank 6, this game the sole responsibility for growing the Nintendo company as one of the biggest game companies and being recognizable all around the world.

With that all in mind, this project plan is to unite the big success that revolutionized the game industry with the technology that is revolutionizing the tech industry: Artificial Intelligence.

## Process

As this was my first project working with AI, the first step was searching more about AI and how I would make a connection with the game.

Nicholas Renotte, a youtuber, released a video 2 months before the date I was first searching for this project, he was using the Python language, exactly what I was looking for, so from here on out "[Build an Mario AI Model with Python | Gaming Reinforcement Learning]()" is going to be a foundation for this project.

The AI type is called Reinforcement Learning and the base for it is the reward function included in Super Mario RL, the base game has 3 variables that composes "victory", move as far right as possible, as fast as possible and don't die, this 3 together composes the reward function, the AI job is discover what actions are needed to maximize the reward value.

PPO is the AI model that is being used, the policy network (type of neural network) is Cnn, a policy fast for processing frames. Grayscalling is a very important step to make the learning faster, as it has 3x less pixels than the normal version and frame stacking helps in the process of giving AI context, in consequence it obtains model memory for the game. 

I did run into some problems while doing the project:
 - The code wasn't working because some imports din't update to the current version of python, so I had to move back my version of python to Python 3.7.3. 
 - Pytorch refused to use CUDA and was using my CPU instead, so for better performance, I had to reinstall CUDA, update my GPU drivers, reinstall Pytorch, clean the wheel and Pytorch cache and after all of that the code was working properly.

## Results

After finishing the code and solve the problems, I started the AI learning process, the code gives a feedback each 512 steps to tell me how things are going, each feedback came around 48 to 50 seconds. Initially, I had plan to do 1 million steps to achieve great results, but my PC specs aren't that great so the base FPS were at 10, at that rate it would take around 26 hours to complete, so instead I did 1 hundred thousand steps and one save model (each one takes around 282 mb of disk space), after that I created the python code to run the game based on the model, at this point Mario could easily kill the first enemy and pass the first pipe, but was mostly stuck at the second, sometimes could pass it.

Based on results that I saw from the Nicholas Renotte AI, Mario can easily complete the first level at around 4 million steps, 40x times my total amount of steps. My future plans for this project is completing the first level by optimizing the code and upgrading my PC specs.

## Technologies

[OpenAI Gym](https://gym.openai.com/): Gym is a toolkit for developing and comparing reinforcement learning algorithms that the project works around.

[Super Mario RL](https://pypi.org/project/gym-super-mario-bros/): Library that enables Python to play Super Mario Bros.

[Nes Py](https://pypi.org/project/nes-py/): Library that enables for you to build a virtual joypad.

[PyTorch](https://pytorch.org/get-started/locally/): Open source machine learning framework.

[PPO Algorithm](https://stable-baselines3.readthedocs.io/en/master/modules/ppo.html):  Proximal Policy Optimization algorithm, the AI model for this project.
