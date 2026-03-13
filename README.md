# Multiple server with infinite capacity - (M/M/c):(oo/FIFO)

# date : 25/02/2026

## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 10 seconds, serivice time of two lathe machine follow exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](https://user-images.githubusercontent.com/103921593/203238035-1c8109bc-cbf2-4c77-baea-c5b682a752ef.png)

## Procedure :

![image](https://user-images.githubusercontent.com/103921593/203238265-176740b0-eae2-4772-90be-5449869ac9b0.png)




## Experiment:

![ss](vs5_1.png)

![ss](vs5_2.png)

## Program

```
developed by : naveen jaisanker
reg. no. : 212224110039

import math

arrival_time = float(input("Enter mean interarrival time: "))
service_time = float(input("Enter mean service time: "))
c = int(input("Enter number of servers: "))

lam = 1/arrival_time
mu = 1/service_time
rho = lam/(c*mu)

sum1 = sum((lam/mu)**n / math.factorial(n) for n in range(c))
sum2 = (lam/mu)**c / (math.factorial(c)*(1-rho))
P0 = 1/(sum1 + sum2)

Lq = (P0 * (lam/mu)**c * rho) / (math.factorial(c)*(1-rho)**2)
L = Lq + lam/mu
Wq = Lq/lam
W = Wq + 1/mu

print("Average number in system =", round(L,3))
print("Average number in queue =", round(Lq,3))
print("Waiting time in system =", round(W,3))
print("Waiting time in queue =", round(Wq,3))
```

## Output :

![SS](ss_5.png)

## Result : 

Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.
