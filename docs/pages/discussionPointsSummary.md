# Discussion Points Summaries and Notes

## A Potential Approach to Lower Susceptibility in Adults

### A Percentage of the Adult Population Starting as Recovered

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



## Missing or Unclear Parameter Information

### Hospitalizations and Critical Cases

- Currently we only have [hospitalized proportion by age group](https://github.com/mwmckenzie/PsaGameModelIntegration/blob/main/docs/pages/originalCharacteristics.md#hospitalized-proportion-by-age-group)
- It is unclear if these are general hospitalizations or critical cases

> The current assumption is that this is a general hospitalization rate

### 0% Probability for Critical Cases?

- Currently the probability for critical cases is set to 0%

