# A New Dataset for Intrinsically Motivated Goal-Conditioned Language Reinforcement Learning

## Environment
You can find the environment [here](https://github.com/tlan95/captionRL-env).

## Introduction
Among all the 1469 trajectories, there are 1344 training goal trajectories with all its training descriptions in the TRAINING DATASET and 125 test goal trajectories with all its training descriptions and test descriptions separately in the TEST DATASET.

As for the autonomous agent in the future, we would like to see if it can generate: (1) known descriptions from unknown trajectories (the training descriptions in the TEST DATASET) and (2) unknown descriptions from unknown trajectories (the test descriptions in the TEST DATASET). Besides, the way I separated the training and test dataset will not let one recorded trajectory exist in both TRAINING DATASET and TEST DATASET.

We would like to build a "curious" captioner implemented in the autonomous agent in the future, which means the "curious" captioner can bias the generation towards "interesting" descriptions (e.g. difficult interactions). For now we try to create the datasets with this purpose. Our goal is to make the agent describe the trajectory correctly and diversely. Therefore, the input is the initial and final image of a trajectory, and the output is the descriptions (caption). 

For each trajectory data (npz file), there are:
* 'obs_init': initial observation 
* 'obs_final': final observation
* 'obj_stuff_data': list of objects {type, initial color, category} and their sizes
* 'joint_poses_init': initial joint poses
* 'joint_poses_final': final joint poses
* 'img_arr_init': initial image in RGB matrix
* 'img_arr_final': final image in RGB matrix
* 'goal': goal of the trajectory
* 'train_des': all training descriptions of the trajectory 
* 'test_des': all test descriptions of the trajectory 

## Description Distribution
As we have 1344 trajectories in the TRAINING DATASET and 125 trajectories in the TEST DATASET, we find that there are 33135 descriptions in the TRAINING DATASET, 2579 training descriptions in the TEST DATASET and 499 test descriptions in the TEST DATASET. As shown in the figures below, there are more descriptions with "Put", "Move" than descriptions with "Paint", "Hide". When we sample all descriptions of one trajectory, goals with "Paint" and "Hide" are always followed by descriptions with "Put" and "Move".

Distribution of descriptions in the TRAINING DATASET:
![TrainDataDist](https://user-images.githubusercontent.com/59849265/140507557-aaa7e431-10c7-4bb2-95ac-f327bf853427.png "Distribution of descriptions in the TRAINING DATASET")
Distribution of training descriptions in the TEST DATASET:
![TestDataTrainDist](https://user-images.githubusercontent.com/59849265/140507629-d6b651a1-08f9-4dcc-90e1-5b32467602d6.png "Distribution of training descriptions in the TEST DATASET")
Distribution of test descriptions in the TEST DATASET:
![TestDataTestDist](https://user-images.githubusercontent.com/59849265/140507714-bd6c323e-adf5-4e2f-b140-7efdaffbc6b7.png "Distribution of test descriptions in the TEST DATASET")


In order to let the user know the initial and final scene of each trajectory more easily, we also created another dataset with same training and test trajectories but including only the initial and final images (PNG format) for each trajectory instead.
