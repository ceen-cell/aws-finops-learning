# EC2 Pricing Models - The FinOps Goldmine

## The Four Pricing Models
1. On Demand  -->  (No discount)
2. Reserved (Standard & Convertible) -- > Discpunt of up to ~70% of On demand whth Convertible ~60% due to flexibility
3. Savings - About ~70% of Of on demand 
4. On Spot - ~90% of On Demand 

### 1. ON-DEMAND - Pay By The Second
- Pay for the compute capacity you use by the second or hour (min 60 sec)
- Linux and Windows servers billed per second after first minute
- All other OS's are billed per hour

#### Pricing Example
t3.medium = $0.0416/hour
Run for 1 month (730 hours) = $30.37/month
Run for 1 year = $364.42/year

#### When to Use
- When you can't commit to long term. i.e shortterm unpredictable workloads
- Aplications with Spiky traffic
- Testing and development

#### Pros
- Has the most maximum flexibility
- No commitment and as such I can start and stop at anytime
- No upfront cost 

#### Cons
- Most expensive option
- Has no cost saving for steady work loads 

Business scenario:
We're launching a new feature and don't know if it'll be popular. Let's start with On-Demand and monitor usage for 3 months before committing.




### 2. RESERVED INSTANCES - Commit & Save

#### What It Is: 
- Commit to using a specific instance tyepe in a specific region for 1-3 years
  

#### Commitment Options
- Satndard Reserved
- Convertible Reserved


##### Standard Reserved Instances
- ~40% discount - 1 year
- ~ 60% discount - 3 years
- CANNOT chnage instance type
- CANNOT change instance region
  

##### Convertible Reserved Instances
- ~ 30% discount - 1 year
- ~ 50% discount - 3 years
- CAN change instance type, size, OS
- CAN change instance region

#### Payment Options
1. All Upfront - most discount 
2. Partial Upfront:  Pay 50% upfront , then rest monthy  -- good discount
3. No Upfront - least discount 

#### Pricing Example
On-Demand: $364/year
1yr Reserved (Standard, No Upfront): ~$220/year (40% savings = $144 saved)
3yr Reserved (Standard, All Upfront): ~$145/year (60% savings = $219 saved)

#### When to Use
- Steady workloads
- Production databases that run 24/7
- Core application servers
- Any workload that I can predict 1-3 years of usage 

#### FinOps Decision Framework
Is my workload running 24/7? YES
Will it run for at least 1 year? YES
Is it in production (not going away)? YES
--> USE RESERVED INSTANCES

#### Real-World Calculation: In my finOps framework 
---

### 3. SPOT INSTANCES - Bid for Unused Capacity

#### What It Is:
- It is using AWS compute capacity at up to about 90% off. The catch here is that AWS can terminate my service when they need that compute back.
- I pay for a max price and when their current spot price exceeds my max price, I will loose my compute capacity. It kind of works like an auction
- I would have a very short notice about termination. As low as 2 minutes. 

#### Pricing Example
- t3.medium On-Demand: $0.0416/hour
- t3.medium Spot: $0.0125/hour (70% off)
- Savings: $0.0291/hour

#### When to Use
- Work that can be insterrupted and resumed
- batch processing jobs
- Vido/image rendering
- Dev/Test environments
- Data analysis
- CI/CD build servers 

#### When NOT to Use:
- Anything that can't tolerate interruption.
- Web servers
- Production databases
- Real-time applications 

#### How Spot Pricing Works
- I set a maximum price I'll pay
- When Spot price is below my max → instance runs
- When demand increases and price exceeds my max --> AWS gives 2-minute warning --> instance terminates

#### Advanced Tip: Spot Fleets:
- With this I request multiple instance types across multiple availability zones. If one type gets interrupted, another starts. This helps to Increases reliability.

#### Real-World Scenario:
Say the Data science team of my company runs ML model training
- Takes 10 hours to complete
- Can checkpoint and resume if interrupted
- On-Demand cost: 10 hours × $3.06/hour (p3.2xlarge) = $30.60
- Spot cost: 10 hours × $0.92/hour = $9.20
- SAVINGS: I save $21.40 per training run (70% off)

Running 100 training runs/month:
- On-Demand: $3,060/month
- Spot: $920/month
- ANNUAL SAVINGS: $25,680


### 4. SAVINGS PLANS - Flexible Commitment

#### What It Is

#### Two Types

##### Compute Savings Plans

##### EC2 Instance Savings Plans

#### Example

#### When to Use

#### Reserved Instances vs. Savings Plans



