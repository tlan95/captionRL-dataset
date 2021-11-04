# A New Dataset for Intrinsically Motivated Goal-Conditioned Language Reinforcement Learning

## Environment
You can find the environment [here](https://github.com/tlan95/captionRL-env).

## Introduction
Among all the 1469 trajectories, there are 1344 training goal trajectories with all its training descriptions in the TRAINING DATASET and 125 test goal trajectories with all its training descriptions and test descriptions separately in the TEST DATASET.

As for the autonomous agent in the future, we would like to see if it can generate: (1) known descriptions from unknown trajectories (the training descriptions in the TEST DATASET) and (2) unknown descriptions from unknown trajectories (the test descriptions in the TEST DATASET). Besides, the way I separated the training and test dataset will not let one recorded trajectory exist in both TRAINING DATASET and TEST DATASET.

We would like to build a "curious" captioner implemented in the autonomous agent in the future, which means the "curious" captioner can bias the generation towards "interesting" descriptions (e.g. difficult interactions). For now we try to create the datasets with this purpose. Our goal is to make the agent describe the trajectory correctly and diversely. Therefore, the input is the initial and final image of a trajectory, and the output is the descriptions (caption). 

For each trajectory data (npz file), there are:
* 'obs_init': 
* 'obs_final'
* 'obj_stuff_data'
* 'joint_poses_init'
* 'joint_poses_final'
* 'img_arr_init'
* 'img_arr_final'
* 'goal'
* 'train_des'
* 'test_des'


In order to let the user know the initial and final scene of each trajectory more easily, we also created another dataset with same training and test trajectories but including only the initial and final images (PNG format) for each trajectory instead.
