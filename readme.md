# overview

content
[link to Lab 5](#lab5)

## lab 6 & 7
### training
After training and everything the test pose 
```MATLAB
home = [45 45 0 45 -45]*deg;
```
gave an error of only `0.0105` which is I assume in meters.

![ final error](/lab7/images/final.png)

The training had 
```MATLAB
imageInputLayer([1 1 nFeatures]);
fullyConnectedLayer(512)
leakyReluLayer
leakyReluLayer
tanhLayer
reluLayer
fullyConnectedLayer(numClasses)  
regressionLayer
```

and 
```MATLAB
maxEpochs = 500;
miniBatchSize = 100;
```

which took about 4 min and 57 sec on
* i7-4870HQ at stock speeds with -60mV and disabled turbo boost
* AMD radeon R9 M370X

even though GPU was not doing the computation it is worth noting that not using igpu does reduce thermal output of the intel chip and gives more headroom for the CPU.

![ training](/lab7/images/training.jpeg)

Previously shown error is only a special case. The testing using `demo_fk` gave a score of `0.0203`

## LAB5
### PART 2
This is a 2 second movement of a robot
![ video](/Lab5p2.gif)
that was executed in 3 minutes by this model:
![ video](/lab5p2sim.png)
Here is how it tracks:
![ video](/pidhighgain.png)

### Moving video
![Moving video](/CleanShot%202020-10-20%20at%2002.08.58.gif)

### Code screenshot
![Code screenshot](/code%20screenshot.png)