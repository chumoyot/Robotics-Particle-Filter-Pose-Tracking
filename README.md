# Robotics-Particle-Filter-Pose-Tracking
Implementation of a particle filter for pose tracking in 2D space.

This is part of the Robotics Specialization by the University of Pennsylvania on Coursera.

This forms the core part of SLAM together with mapping. In mapping, the robot has no idea of its surroundings but only its position and builds a map. In localization, the problem is reversed. It only knows the map but not its position. 

The core idea of particle filtering is Random sampling and resampling. Since we don't know where the target is, particles are scattered randomly or under a Gaussian distribution. After scattering the particles, the importance of each particle is calculated based on the similarity of the characteristics, and then more particles are scattered in highly favorable places and fewer in other areas. 

So for each LIDAR measurement, the correlation score of every particle is computed. At the start, each particle can be equally weighted, so, for 10 particles, each particle will have a weight of **0.1**. The new weight will be a product of the current weight and the correlation score. The numbers may get quite small, so we renormalize all weights after each cycle so that the sum of the weights equals **1**.

The function returns the entire path of the robot, in a 3 by n matrix. **x** is the number of iterations, and the rows represent the **x, y** coordinates of the robot and **theta**, the angular component.

Here is the final output showing the robot's path in red. I only sampled 1/3 of the data so its path is not complete.

![robot path in red](https://github.com/chumoyot/Robotics-Particle-Filter-Pose-Tracking/assets/135506318/9bb693ee-c38e-4818-86fc-3bedc7b5213e)



