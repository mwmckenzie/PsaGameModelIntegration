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

`Conversion Rate = Step / Mean Duration`

### Example

To calculate the conversion rate for the transition from exposed to infectious with an expected mean duration of 6 days:

```
Step = 1
Mean Duration = 6
Conversion Rate = 0.1666667
```

### Simulated State Conversion Rates

- Exposed To Infectious Rate 
- Symptomatic Recovery Rate 
- Asymptomatic Recovery Rate 
- Hospitalization Recovery Rate 
- Critical Recovery Rate 
- Recovered To Susceptible Rate 
- Vaccinated To Susceptible Rate

## Type Ratios

### Discussion

- The probability of a member being assigned to a distinct type.
- The ratio should only represent the expected distribution of the values being compared, not universal or global distrubtions or ratios.
- Simply, how many of type A do you expect per type B?

### Method

`Type Ratio = Expected Value Type A / Expected Value Type B`

### Example

To calculate and asymptomatic To symptomatic ratio with expected values of 1 to 9:

```
Step = 1
Mean Duration = 6
Conversion Rate = 0.1666667
```

### Simulated Type Ratios

- Hospitalization To Non-Hospitalization Ratio 
- Asymptomatic To Symptomatic Ratio 
- Critical To Non-Critical Hospitalization Ratio 
- Deceased To Critical Case Recovery Ratio 

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
