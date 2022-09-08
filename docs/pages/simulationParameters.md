# Simulation Parameters

> Note: Currently all probability calculations sample from a uniform distribution

## Global Variables

### Population

> Current Value: 100,000

- Integer
- Count of all exisiting entities within a simulation context
- Context defined by distinct and complete simulation loop space
- Common values: 
  - 1,000
  - 10,000
  - 100,000

### Step

> Current Value: 1 day

- Integer
- Increments by 1 for every step of the simulation
- Generally represents a parcel of time
- Common values: 
  - 1 day
  - 1 hour
  - 6 hours
  - 12 hours
- Less common:
  - 1 week
  - 1 month
  - 1 year

## Conversion Rates

### Discussion

- The probability of a member to undergo state change per simulation step.
- A lower value generally indicates a slower conversion rate, as there is a lower probability for transition at each step.
- A value of 1 indicates an instant conversion.

### Method

`Conversion Rate = Step / Mean Duproportionn`

### Example

To calculate the conversion rate for the transition from exposed to infectious with an expected mean duration of 6 days:

```
Step = 1
Mean Duration = 6
Conversion Rate = 0.1666667
```

### UI Calculation Tool

<img src="https://user-images.githubusercontent.com/57882845/189082597-236c8009-a000-49a7-a292-388d4fd0ddbd.png" width="400">
</img>

### Simulated State Conversion Rates

- Exposed To Infectious Rate 
- Symptomatic Recovery Rate 
- Asymptomatic Recovery Rate 
- Hospitalization Recovery Rate 
- Critical Recovery Rate 
- Recovered To Susceptible Rate 
- Vaccinated To Susceptible Rate

## Type Proportions

### Discussion

- The probability of a member being assigned to a distinct type.
- The proportion should only represent the expected distribution of the values being compared, not universal or global distrubtions or proportions.
- Can be calculated via one of two input methods:
  - Ratio
  - Proportion

### Ratio

- Simply, how many of type A do you expect per type B?

### Proportion

- Percentage or number of type A per total of type A and type B

### Method

```
Per = Expected Value Type A + Expected Value Type B
Type Proportion = Expected Value Type A / Per
```

### Example

To calculate asymptomatic proportion with expected values of 5 per 100:

```
Value A = 5
Per = 100
Value B = 95
Type Proportion = 0.05
```

### UI Calculation Tool

<img src="https://user-images.githubusercontent.com/57882845/189080349-73174880-78c6-4cc1-8085-1b380e553bac.png" width="400">
</img>

### Simulated Type Proportions

- Hospitalization To Non-Hospitalization Proportion 
- Asymptomatic To Symptomatic Proportion 
- Critical To Non-Critical Hospitalization Proportion 
- Deceased To Critical Case Recovery Proportion 

## Transmission Rates
- Symptomatic Transmission Rate 
- Asymptomatic Transmission Rate 
- Hospital Transmission Rate 
- Critical Transmission Rate 
- Visitor Transmission Rate 

## Testing Rates
- Susceptible Testing Rate 
- Exposed Testing Rate 
- Symptomatic Testing Rate 
- Asymptomatic Testing Rate 
- Hospitalization Testing Rate 
- Critical Testing Rate 
- Recovered Testing Rate 
- Vaccinated Testing Rate 

## False Test Result Rates
- False Pos Rate 
- False Neg Rate 
