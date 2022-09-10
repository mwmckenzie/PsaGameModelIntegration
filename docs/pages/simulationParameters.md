# Simulation Parameters

> Note: Currently all probability calculations sample from a uniform distribution

## Index
- [Conversion Rate](#conversion-rate)
- [Split Type Proportion](#Split-Type-Proportion)
- [Transmission Rate](#transmission-rate)
- 

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

> Current Value: 1

- Integer
- Increments by 1 for every step of the simulation

### StepDuration

> Current Value: 1.0

- Float/Double/Decimal
- Generally represents a parcel of time
- Proportional to 1 day

#### Common values

| Value | Duration |
|-------|----------|
| 1.0   | 1 day    |
| 0.25  | 6 hours  |
| 0.5   | 12 hours |
| 7.0   | 1 week   |
| 365.0 | 1 year   |

## Conversion Rate

| Type  | Min | Max |
|-------|-----|-----|
| Float | 0.0 | 1.0 |

### Discussion

- The probability for each element of a population to undergo the associated state change. 
- Probability is calculated per simulation step.
- A lower value generally indicates a slower conversion rate, as there is a lower probability for transition at each step.
- A value of 1 indicates an instant conversion.

### Method

`Conversion Rate = Step Duration / Mean Duration`

### Example

To calculate the conversion rate for the transition from exposed to infectious with an expected mean duration of 6 days:

```
Step Duration = 1.0
Mean Duration = 6.0
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

## Split Type Proportion

| Type  | Min | Max |
|-------|-----|-----|
| Float | 0.0 | 1.0 |

### Discussion

- The probability of a member being assigned to a distinct type at a split junction.
- The proportion should only represent the expected distribution of the values being compared, not universal or global distrubtions or proportions.
- Can be calculated via one of two input methods:
  - Ratio
  - Proportion

### Ratio

- Simply, how many of type A do you expect per type B?

### Proportion

- Percentage or number of type A per total of type A and type B
- Type B can be an aggregate of other types of the group/set

### Method

```
Per = Expected Value Type A + Expected Value Type B
Type Proportion = Expected Value Type A / Per
```

### Example

#### Ratio

To calculate asymptomatic proportion with an expected ratio of 1:3 asymptomatic to symptomatic:

```
Value A = 1
Value B = 3
Per = 4
Type Proportion = 0.25
```

#### Proportion

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

## Transmission Rate

| Type  | Min | Max |
|-------|-----|-----|
| Float | 0.0 | 1.0 |

### Discussion

- Equivalent to the 'beta' value
- Susecptibility per contact multiplied by the expected contact count per step
- Expected contact count per step calculated by the total expected close contacts per infectious period divided by the length of the period of infectiousness

### Method

```
Expected Contact Count Per Step = Expected Contact Count Per Period / Avg Infectious Period
Transmission Rate = Susceptibility * Expected Contact Count Per Step
```

### Example

```
Expected Contact Count Per Step = 2.14 contacts / 1.61 days
Susceptibility = 0.38
Transmission Rate = 0.505
```

### UI Calculation Tool

![image](https://user-images.githubusercontent.com/57882845/189477245-57ccdd6f-dd5b-4970-a05c-478c29897909.png)

### Simulated Transmission Rates

- Symptomatic Transmission Rate 
- Asymptomatic Transmission Rate 
- Hospital Transmission Rate 
- Critical Transmission Rate 
- Visitor Transmission Rate 

## Testing Rates

| Type  | Min | Max |
|-------|-----|-----|
| Float | 0.0 | 1.0 |

- Susceptible Testing Rate 
- Exposed Testing Rate 
- Symptomatic Testing Rate 
- Asymptomatic Testing Rate 
- Hospitalization Testing Rate 
- Critical Testing Rate 
- Recovered Testing Rate 
- Vaccinated Testing Rate 

## False Test Result Rates

| Type  | Min | Max |
|-------|-----|-----|
| Float | 0.0 | 1.0 |

- False Pos Rate 
- False Neg Rate 
