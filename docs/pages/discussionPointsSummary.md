# Discussion Points and Notes

#### Updated: 13 Sep 2022

## A Potential Approach to Lower Susceptibility in Adults

### Start a Percentage of the Adult Population as Recovered

- To model a large portion of the adult population having immunity through childhood infections, we can divide the population based on expected childhood disease rates
- If the adult susceptibility is expected to be 30% as a proportion of the population *not* infected as children, then 70% of the adult population can be set to recovered as an initial condition

### Very Low Recovery-to-Susceptible Transition Rates

- To mimic a decades long immunity we can set the recovery rate to 10, 25, or 50 years (or any other abitrary length of time)
- This would still allow for the possibility of very rare second infections (with the rarity inversely proportional to the length of expected recovery to susceptible transition)
- As the game length is quite short in comparison, I don't expect the number to matter much beyond a certain point
- A working minimum is probably at least 2-4 times the length of the simulation duration, though it can easily be adjusted if the number of reinfections is considered too high
- Long expected recory periods equate to lower transition rates from recovered to susceptible, generally ensuring a mostly immune adult population, but allowing for some variability in each model run

### Reset Susceptibility to 1.0 for the remaining population

- With the remaining population expected to be children and adults who have no immunity, the susceptibility can be factored back to 1.0 for all transmission opportunities

### Benefits of Approach

- This approach greatly eases modeling complexity
- Much easier to reason about, both in initial configuration settings, but also through the post-simulation data analysis
- We do not need to split populations and create an interaction/mixing matrix
- I think it is a nice approximation of the natural problem

## Disease Transmission and Susceptible Availability

### Limitations of Current Approach

- Currently if a transmission is calculated and there is a susceptible person available then a transmission always occurs
- This is irregardless of how rare susceptible persons are within the population
- This strikes me as a flawed approach for multiple reasons

### Possible Flaws in the Availability Model

- For every potential transmission contact event, it stands to reason that the probability of the event recipient being susceptible would be proportional to the number of susceptible persons within the total population
- The disease should have an easier time spreading within a largely susceptible population and a harder time as the target pool shrinks
- The current model does not do this, it provides a uniform degree of spreading difficulty to the model at all ratios of susceptible-to-non-susceptible
- Currently there is no difficulty change after the initial beta value is set

### Potential Approaches

- The transmission rate probability could be modified by a factor of the proportion of susceptible persons within the total population
- To begin with, we could test a linear model of susceptible availability to apply against the transmission opportunities
- This number could have an exponential parameter that would further allow for modeling population density factors
- An exponential paramater > 0 and < 1 for higher density populations, and > 1 for lower density (that might be backwards - it needs to be tested)

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
- This is, naturally, creating results with zero critical cases

### No Possiblity of Fatalities in Current Model

- Case fatalities are channeled through the critical case pathway in the Markov process model
- With a 0% probability for critical cases there will be no elements of the population transitioned to critical
- No critical cases result in no transition tests for fatality transitions
- This then makes any of the current parameters (and associated game info) for fatality rates incorrect (the actual percentage is 0)

### Recommendation

- If fatality rate is not meant to be a 'red herring' then we should consider introducing a critical case rate

## Expected Contact Counts Missing and Unclear

- What are the expected contact rates (per infection period)?
- Currently the simulation is using the household size as the expected contact rate
- I do not believe this makes sense, though, given the expectation that the majority of adults are immune, as at least 1 person per household is then likely to be immune

### Parameter Needed

- What are the expected internal and external transimission-capable contact counts? (per infection period)

## Taking Advantage of Markov Processes

### Defining Probabilities at Each Step

- Breaking up the problem into discrete and distinct Markov chain elements allows us to design and define probabilities in a more meaningful manner
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


## Scale Across the Game Parameters and Data

### Some Numbers Are Too Small To Effectively Model

- Take for example the number of travelers to Blue Land
- If we have 22,000 travelers from a population of 18,000,000 that is about 122 in 100,000 traveling, or 0.12% of the population
- In the current model we could have an asymptomatic load of perhaps 300 per 100,000 on day 70
- That leaves a likelihood of being asymptomatic of about 0.3%
- Assuming a similar traveler to non-traveler ratio for both asymptomatic and non-asymptomatic populations, this then indicates the probability of an asymptomatic traveler of about 0.000367% (per traveler)
- This number is per traveler *per week* (traveler numbers given per week)
- If we then transform this probability per day we are left with a 0.000052% chance of a traveler being asymptomatic

> Overall, we can expect 0.0807 asymptomatic travelers per week, or 0.012 asymptomatic travelers per day

### Small Fluxuations in Traveler Numbers

- With such a small probability of sick travelers -- around .0002% -- a relatively small change in traveler numbers is unlikely to change the problem
- If the number of travelers increases to 25,000 per week (though the number changed in the card is smaller as it only accounts for a four day change) the final expected probability does not change
- The final change to the probability calculation is less than the value of the rounding error

### Low Testing Capacity

- A testing capacity maximum of 200 per population results in only 1 test *possible* per 100,000
- The positive test results will never be higher than 1 in the simulation as a combination for *all* testing (if running the simulation at 100,000)
- This does not allow for meaningful simulation
