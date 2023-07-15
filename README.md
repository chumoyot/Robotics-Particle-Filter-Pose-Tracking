# Robotics-Particle-Filter-Pose-Tracking
Implementation of a particle filter for pose tracking in 2D space.

This forms the core part of SLAM together with mapping. 

the core idea of particle filtering is Random sampling and resampling. Since we don't know where the target is, particles are scattered randomly or under a Gaussian distribution. After scattering the particles, the importance of each particle is calculated based on the similarity of the characteristics, and then more particles are scattered in highly favorable places and fewer in other areas. 

So for each LIDAR measurement, the correlation score of every particle is computed. At the start, each particle can be equally weighted, so, for 10 particles, each particle will have a weight of **0.1**. The new weight will be a product of the current weight and the correlation score. The numbers may get quite small, so we renormalize all weights after each cycle so that the sum of the weights equals **1**.

The function returns the entire path of the robot, in a 3 by n matrix. **x** is the number of iterations, and the rows represent the **x, y** coordinates of the robot and **theta**, the angular component.


