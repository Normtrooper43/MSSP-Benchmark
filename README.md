# MSSP-Benchmark
A benchmark dataset for the movie scene scheduling problem. Includes data, function evaluator and instance generator.

This readme is meant to provide details on the structure of the instance files for this benchmark. Each file is its own instance. There are 4 problem classes, S_0 to S_3. The first is the smallest problem class and the last is the biggest.

Each class has 5 instances for a total of 20 instances in the entire benchmark. The best known values are provided in a separate file. These are just the best known values that have been found for each of the instances thus far, but these are not necessarily the absolute optimal values. All durations are given in days although it is not strictly necessary. It could also represent hours.

The file format is as follows:

cost limit: a constraint that could be imposed to limit max costs. It's currently unused from the original version of the problem

time limit: a constraint that could be imposed to limit time to schedule a movie. It's currently unused from the original version of the problem

number of actors A: Number of actors in the production.

number of scenes S: Number of scenes in the production.

number of locations L: Number of locations used for shooting each of the scenes. Every scene has a location but multiple scenes can share a location, just not at the same time.

<List of daily wages for each actor>: A comma-delimited list of each of the daily wages for every actor. The first index is the wage for the first actor and so on.

<List of scene durations in days for each scene>: A comma-delimited list of each of the scene durations for every actor. The first index is the duration for the first scene and so on.

[S][S] 2D matrix for the scene transition costs: This is a 2D matrix of SxS size. Each is the intersection of the indices is the cost to move from scene X to scene Y.

[L][L] 2D matrix for the location transfer time: This is a 2D matrix of LxL size. Each is the intersection of the indices is the time required to move from location X to location Y. It costs no time to move from location X to location X.

<List of Scene Location Assignments>: A list of where each scene is assigned to which location. The first element of the list is the location of the first scene and so on.

<List of Actor Scene Assignments>: This is list delineated on multiple lines. Each line is its own list and represents a scene. The list for each line, represents the actors assigned to that scene. 

For example:

0,1,2
1,2,4
represents two scenes. The first scene has actors 0,1,2.

