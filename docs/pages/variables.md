# Markov Chain SEIR Model Variables

## Conversion Rates

| Description                    | Variable                    |
|--------------------------------|-----------------------------|
|   Exposed To Infectious Rate   | exposedToInfectiousRate     |
|    Symptomatic Recovery Rate   | symptomaticRecoveryRate     |
| Asymptomatic Recovery Rate     | asymptomaticRecoveryRate    |
| Hospitalization Recovery Rate  | hospitalizationRecoveryRate |
| Critical Recovery Rate         | criticalRecoveryRate        |
| Recovered To Susceptible Rate  | recoveredToSusceptibleRate  |
| Vaccinated To Susceptible Rate | vaccinatedToSusceptibleRate |

## Type Ratios

| Description                                    | Variable                     |
|------------------------------------------------|------------------------------|
|  Hospitalization To Non-Hospitalization Ratio  | hospToNonHospRatio           |
|        Asymptomatic To Symptomatic Ratio       | asympToSympRatio             |
| Critical To Non-Critical Hospitalization Ratio | criticalToHospRatio          |
| Deceased To Critical Case Recovery Ratio       | deceasedToCriticalRecovRatio |


## Transmission Rates

| Description                    | Variable                 |
|--------------------------------|--------------------------|
| Symptomatic Transmission Rate  | sympTransmissionRate     |
| Asymptomatic Transmission Rate | asympTransmissionRate    |
| Hospital Transmission Rate     | hospitalTransmissionRate |
| Critical Transmission Rate     | criticalTransmissionRate |
| Visitor Transmission Rat       | visitorTransmissionRate  |

## Testing Rates

| Description                  | Variable                   |
|------------------------------|----------------------------|
| Susceptible Testing Rate     | susceptibleTestingRate     |
| Exposed Testing Rate         | exposedTestingRate         |
| Symptomatic Testing Rate     | symptomaticTestingRate     |
| Asymptomatic Testing Rate    | asymptomaticTestingRate    |
| Hospitalization Testing Rate | hospitalizationTestingRate |
| Critical Testing Rate        | criticalTestingRate        |
| Recovered Testing Rate       | recoveredTestingRate       |
| Vaccinated Testing Rate      | vaccinatedTestingRate      |


## False Test Result Rates

| Description         | Variable     |
|---------------------|--------------|
| False Positive Rate | falsePosRate |
| False Negative Rate | falseNegRate |

## Example Parameter Set
- [PSA Game Simulation Parameters](/json/parameters/SeirModelParams_PsaGame_2022-09-06-1049.json)
