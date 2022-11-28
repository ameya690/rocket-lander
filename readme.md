# This Vertical Rocket Landing Simulation using OpenAI Environment for my Control Systems Class February 2020 based on work by Reuben Ferrante

The simulation was developed in Python 3.5 and written using [OpenAI's gym environment](https://gym.openai.com/docs/). 
Box2D was the physics engine of choice and the environment is similar to the [Lunar Lander](https://gym.openai.com/envs/LunarLander-v2/). [This](https://www.youtube.com/watch?v=4_igzo4qNmQ) is a video of the simulator in action.

![environment 3](https://user-images.githubusercontent.com/16338481/33860598-870fd702-ded1-11e7-8bdb-86fa01e2db47.JPG)


Code demonstrates:
* Proportional Integral Control (PID)
* Deep Deterministic Policy Gradients (DDPG)
* Modern Predictive Control (MPC)

Other sample code available:

* Evolutionary Strategy (ES)
* Function Approximation Q-Learning (FA Q-Learning)
* Linear Quadratic Regulator (LQR)

Main contributions of the project is the environment, with other scripts for controllers included for context and general reference.




![rocket model](https://user-images.githubusercontent.com/16338481/33860716-021480d8-ded2-11e7-85b4-6fffbcea0258.PNG)

### Simulation states and actions

In code, the state is defined as:
```
State = [x_pos, y_pos, x_vel, y_vel, lateral_angle, angular_velocity]
Actions = Fe, Fs, $psi$
```
* Fe = Main Engine (vertical thruster) ```[0, 1]```
* Fs = Side Nitrogen Thrusters ```[-1, 1]```
* Psi = Nozzle angle ```[-NOZZLE_LIMIT, NOZZLE_LIMIT]```

All simulation settings, limits, polygons, clouds, sea, etc. are defined as constants
in the file ```constants.py```.

### Controllers

Code for controllers exists under ```control_and_ai```, with the DDPG having a separate package.



References: https://gym.openai.com/envs/LunarLander-v2/
