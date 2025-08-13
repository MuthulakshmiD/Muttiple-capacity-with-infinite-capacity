# Multiple server with infinite capacity - (M/M/c):(oo/FIFO)
## Name : Muthulakshmi D 
## Reg : 212223040122

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
![277116563-34666112-8674-4e80-b62d-50ee0a454a36](https://github.com/user-attachments/assets/18122afe-8d1c-49d8-a3d4-d6e714e7f8e8)

## Program
```
## exp 5 ---------!
# 10 ,1 ,7 ,2
import math

arr = float(input("Arrival time (sec): "))
ser = float(input("Service time (sec): "))
rob = float(input("Robot time (sec): "))
c = int(input("No. of service centres: "))

lam = 1 / arr
mu = 1 / (ser + rob)
rho = lam / (c * mu)

print("\n--- M/M/c Queue Model ---\n")
print("The mean arrival rate per second : %0.2f "%lam)
print("The mean service rate per second : %0.2f "%mu)
sum=(lam/mu)**c*(1/(1-rho))/math.factorial(c)
for i in range(0,c):
    sum=sum+(lam/mu)**i/math.factorial(i)
P0=1/sum
if (rho<1):
    Lq=(P0/math.factorial(c))*(1/c)*(lam/mu)**(c+1)/(1-rho)**2
    Ls=Lq+lam/mu
    Ws=Ls/lam
    Wq=Lq/lam
    print("Average number of objects in the system : %0.2f "%Ls)
    print("Average number of objects in the conveyor :  %0.2f "%Lq)
    print("Average waiting time of an object in the system : %0.2f secs"%Ws)
    print("Average waiting time of an object in the conveyor : %0.2f secs"%Wq)
    print("Probability that the system is busy : %0.2f "%(rho))
    print("Probability that the system is empty : %0.2f "%(1-rho))
else:
    print("Warning! Objects Over flow will happen in the conveyor")
print("--------------------------------------------------------------")
print(f"Arrival rate: {lam:.2f}\n2Service rate: {mu:.2f}")


```

## Output :
![image](https://github.com/user-attachments/assets/6291096c-7362-4848-bafb-aed65f83e928)

## Result : 
Thus the average number of materials in the system and conveyor, waiting time of each material in the system and conveyor is found successfully.
