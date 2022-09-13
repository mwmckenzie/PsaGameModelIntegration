# Discussion Points and Notes

#### Updated: 13 Sep 2022

## A Potential Approach to Lower Susceptibility in Adults

### Start a Percentage of the Adult Population as Recovered

- To model a large portion of the adult population having immunity through childhood infections, we can divide the population based on expected childhood disease rates
- If the adult susceptibility is expected to be 30% as a proportion of the population *not* infected as children, then 70% of the adult population can be set to recovered as an initial condition

### Set Recovery-to-Susceptible Transition Rates Very High

- To mimic a decades long immunity we can set the recovery rate to 10, 25, or 50 years (or any other abitrary length of time)
- This would still allow for the possibility of very rare second infections (with the rarity inversely proportional to the length of expected recovery to susceptible transition)
- As the game length is quite short in comparison, I don't expect the number to matter much beyond a certain point
- A working minimum is probably at least 2-4 times the length of the simulation duration, though it can easily be adjusted if the number of reinfections is considered too high

### Reset Susceptibility to 1.0 for the remaining population

- With the remaining population expected to be children and adults who have no immunity, the susceptibility can be factored back to 1.0 for all transmission opportunities

### Benefits of Approach

- This approach greatly eases modeling complexity
- Much easier to reason about, both in initial configuration settings, but also through the post-simulation data analysis
- We do not need to split populations and create an interaction/mixing matrix
- I think it is a nice approximation of the natural problem

## Disease Transmission and Susceptible Availability

### Limitations of Current Approach

- Currently if a transmission is caclulated to occur and there is a susceptible person available transmission occurs
- This is irregardless of how rare susceptible persons are within the population
- This strikes me as a flawed approach for multiple reasons

### Possible Flaws in the Availability Model

- For every potential transmission contact event it stands to reason that the probability of the events recipient being susceptible would be proportional to the number of susceptible persons within the total population
- The disease should have an easier time spreading within a largely susceptible population and a harder time as the target pool shrinks
- The current model does not do this, it provides a uniform degree of spreading difficulty to the model at all ratios of susceptible-to-non-susceptible (currently there is no difficulty beyond the initial beta value)

### Potential Approaches

- The transmission rate probability could be modified by a factor of the proportion of susceptible persons within the total population
- To begin with, we could test a linear model of susceptible availability to apply against the transmission opportunities
- This number could have an exponential parameter that would further allow for modeling population density factors
- An exponential paramater > 0 and < 1 for higher density populations, and > 1 for lower density (that might be backwards...)

### Comparisons of Results

- Graphs and reports to follow soon

> Check back in a few days!

## Missing or Unclear Parameter Information

### Hospitalizations and Critical Cases

- Currently we only have [hospitalized proportion by age group](https://github.com/mwmckenzie/PsaGameModelIntegration/blob/main/docs/pages/originalCharacteristics.md#hospitalized-proportion-by-age-group)
- It is unclear if these are general hospitalizations or critical cases

> The current assumption is that this is a general hospitalization rate

### 0% Probability for Critical Cases?

- Currently the probability for critical cases is set to 0%
- This is, naturally, created results with zero critical cases

### No Possiblity of Fatalities in Current Model

- Case fatalities are channeled through the critical case pathway in the Markov chain model
- With a 0% probability for critical cases there will be no elements of the population transitioned to critical and no transition tests for fatalities
- This then makes any parameters (and associated game info) for fatality rates moot/pointless

### Recommendation

- If fatality rate is not meant to be a 'red herring' then we should consider introducing a critical case rate

## Taking Advantage of Markov Processes

### Defining Probabilities at Each Step

- Breaking up the problem into discrete and distinct Markov chain element allows us to design and define probabilities in a more meaningful manner
- For instance, we can define the probability of being symptomatic purely by the split between symptomatic vs asymptomatic

### Seperation of Concerns

- Looking to the previous problem, we can deal with each issue seperately
- We can ask the questions in a natural sequence: 
  - If infectious what is the chance of being hospitalized?
  - If hospitalized what is the chance of being critical?
  - If critical what is the chance of dying?

### Easier to Address Unsatisfactory Model/Simulation Results

- With this approach, if we are unhappy with the simulation results for a particular field, we can more easily adjust towards the desired outcome
- Additionally, as we can very easily see downstream probabilities in the hierarchy, we will know what nodes will need to be counter-adjusted to offset any correction



