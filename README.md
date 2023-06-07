# Single server with infinite capacity (M/M/1):(oo/FIFO)
## Aim :
To find (a) average number of materials in the system (b) average number of materials in the conveyor (c) waiting time of each material in the system (d) waiting time of each material in the conveyor, if the arrival  of materials follow poisson process with the mean interval time 12 seconds, serivice time of lathe machine follows exponential distribution with mean serice time 1 second and average service time of robot is 7seconds.

## Software required :
Visual components and Python

## Theory:
Queuing are the most frequently encountered problems in everyday life. For example, queue at a cafeteria, library, bank, etc. Common to all of these cases are the arrivals of objects requiring service and the attendant delays when the service mechanism is busy. Waiting lines cannot be eliminated completely, but suitable techniques can be used to reduce the waiting time of an object in the system. A long waiting line may result in loss of customers to an organization. Waiting time can be reduced by providing additional service facilities, but it may result in an increase in the idle time of the service mechanism.

![image](1.png)

This is a queuing model in which the arrival is Marcovian and departure distribution is also Marcovian,number of server is one and size of the queue is also Marcovian,no.of server is one and size of the queue is infinite and service discipline is 1st come 1st serve(FCFS) and the calling source is also finite.

## Procedure :
### 1.probability of zero units in the queue(p0)=1-arrival rate/service time
### 2.Average queue length(Lq)=
### 3.Average number of units in the system(Ls)=
### 4.Average waiting time of an arrival(Wq)=
### 5.Average waiting time of an arrival in the system(Ws)=



## Experiment:


 
## Program
```
arr_time = float(input("Enter the mean interarrival time of objects from Feeder (in secs): "))
ser_time = float(input("Enter the mean inter-service time of Lathe Machine (in secs): "))
robot_time = float(input("Enter the additional time taken for the Robot (in secs): "))

lam = 1 / arr_time
mu = 1 / (ser_time + robot_time)

print("--------------------------------------------------------------")
print("Single Server with Infinite Capacity - (M/M/1):(oo/FIFO)")
print("--------------------------------------------------------------")
print("The mean arrival rate per second: %.2f" % lam)
print("The mean service rate per second: %.2f" % mu)

if lam < mu:
    Ls = lam / (mu - lam)
    Lq = Ls - lam / mu
    Ws = Ls / lam
    Wq = Lq / lam

    print("Average number of objects in the system: %.2f" % Ls)
    print("Average number of objects in the conveyor: %.2f" % Lq)
    print("Average waiting time of an object in the system: %.2f secs" % Ws)
    print("Average waiting time of an object in the conveyor: %.2f secs" % Wq)
    print("Probability that the system is busy: %.2f" % (lam / mu))
    print("Probability that the system is empty: %.2f" % (1 - lam / mu))
else:
    print("Warning! Object overflow will happen in the conveyor")

print("---------------------------------------------------------------")
```
## Output :
![image](https://github.com/Saravana-kumar369/Single-server-infinite-capacity---Markov-Model/assets/117925254/23d8c327-f174-42e6-a767-d50c5a68f90e)

## Result :
The average number of material in the sysytem and in the conveyor and waiting time are successfully found.
