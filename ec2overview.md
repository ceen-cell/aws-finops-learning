# EC2 Overview - The Foundation

## What IS EC2?
- Elastic Cloud Compute 

### The Business Problem It Solves
- Companies used to buy **physical servers** -> wait weeks for delivery -> pay $5,000-$50,000 upfront -> stuck with that capacity forever -> sadly, **servers become outdated in 3-5 years**. What a waste ! 

### EC2's Solution
- Rent virtual servers (instances) in Amazon's data centers and launch in 90 seconds
- I can scale up/down instantly based on workload
- Peck:I will always have latest hardware while paying only for what I use.

### Simple Analogy for Others
- **EC2 is like Uber for servers**. Instead of me buying a car (physical server) that sits in my garage depreciating, 
I rent exactly the ride I need, when I need it, and only pay for the minutes I use it

## Key EC2 Concepts
 
### Instance = Virtual Server
- A computer that runs in the AWS data center that I run remotely
- Just like a physical computer, it has CPU, RAM, storage and network

### AMI = Amazon Machine Image
- The blueprint/template of my Ec2 instance / virtual server just like the oprating system for my persoanl computer.
- E.g Linux AMI, Ubuntu AMI, Custom AMI, Windows Server AMI  

### Instance State (Lifecycle)
- Stopped - the instance exists but is not running as such I pay only for storage and not compute  
- Running - active and so you pay for compute per sec as it runs. (note public IP cahnges each time it is stopped and run again)
- Terminated - permannetly deleted and can't access again. 

### Elastic = Flexibility
- Almost like eleastic demand in Econ.
- You can either launch 1 or 100 instances
- **Vertical scaling (increase size)** : I think of this as growth spurts. We grow up, and we increase in size and height vertically
- **Horizontal Scaling(increase number)** : I think of this as having children they stand horizontal around me they dont climb my head 😅. 

## FinOps Perspective on EC2 Overview

### Why Companies Choose EC2
1.**CapEx → OpEx shift**
   - I no longer have upfront hardware cost

**2. Pay-as-you-go**
   - I pay for only things as I run them
     
**3. Eliminate waste**
   - I no longer pay for hardare servers whose capacity is idle 50% of the time.
     
**4. Speed**
   - I can launch infrastructure in seconds instead of weeks 

### CI 
- EC2 transforms spending from **a fixed cost** (buying servers) to a **variable cost** (renting compute).
-  This is powerful BUT dangerous. This is because teams can spin up expensive resources and forget about them without governance 
- My job is ensure that cooperations get Elasticity benefits of AWS servers while controlling costs. 
