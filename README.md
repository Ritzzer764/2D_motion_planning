# 2D_motion_planning

## Finding Nearest Neighbour
I used two algorithms to find the nearest neighbors of points:-
* K-Nearest Neighbors Algorithm - Faster run-time but requires more number of sample points 
* Euclidean distance (cdist) - Slower run-time but requires less number of sample points

### K-Nearest Neighbors Algorithm
While utilizing the KNN algorithm (Number of Neighbours = 20, radius = 0.4), I found that I had to use more sample points (5000) than cdist to pass all test cases (more pictures are there in the test_images folder).
![Cdist 5000](https://github.com/Ritzzer764/2D_motion_planning/assets/114499776/511dc447-32d0-4505-9b77-858e1bcc39a4)
Although KNN required more points, the network was able to cover a much larger area than cdist due to the number of points as seen above. 
This is the shortest path for the test case (size_x = 10, size_y = 6, number of obstacles = 5):
Path before post processing            |  Shortest path after path shortcutting
:-------------------------:|:-------------------------:
![KNN_5000_spt](https://github.com/Ritzzer764/2D_motion_planning/assets/114499776/c9749596-9a23-4bea-b5a8-5dc0e3de8ec5)  | ![KNN_5000_opt](https://github.com/Ritzzer764/2D_motion_planning/assets/114499776/f43bdcec-84cd-4cea-9ac6-ae452c052091)


### Euclidean distance (cdist)
I found that when utilizing cdist to create the network of nearest neighbors, I only had to use a few samples of points (600) to pass all test cases. 
This is the network created using 600 points of cdist (Number of Neighbours = 20) :
![Cdist 600](https://github.com/Ritzzer764/2D_motion_planning/assets/114499776/de181525-babe-48c6-b1d9-88e6fda66a39)
Although the network does not cover the entire area as seen in the picture above, it is able to past all test cases (more pictures are there in the test_images folder)
I could solve this issue of less area coverage by increasing the number of sample points, but the run-time became significantly slower.

This is the shortest path for the test case (size_x = 10, size_y = 6, number of obstacles = 5):

#### Path before post processing
![spt_img_(10, 6, 5)](https://github.com/Ritzzer764/2D_motion_planning/assets/114499776/5d827173-8dd8-437f-9daa-3a2f4b825e2a)

#### Shortest path after path shortcutting
 ![Opt_img_(10, 6, 5)](https://github.com/Ritzzer764/2D_motion_planning/assets/114499776/e5ee4cce-2540-4a3f-9ee7-9f4adc9c6dac) 



