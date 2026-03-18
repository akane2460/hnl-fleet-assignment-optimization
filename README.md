# hnl-fleet-assignment-optimization
Linear programming model for optimal Hawaiian Airlines fleet assignment under FAA air traffic control capacity constraints at Honolulu International Airport (HNL).

# Airline Fleet Assignment Optimization Under Heightened ATC Capacity Constraints

## Overview
Linear programming model optimizing fleet assignment for a simulated 
FAA air traffic control reduction scenario at Honolulu International 
Airport (HNL). Developed as part of a two-person academic project; 
responsible for problem formulation, LP model architecture,
methodology, implementation, and technical write-up.


Northwestern University Instructor feedback: "reads more like a working paper than a class 
project... the literature review is one of the strongest I've seen."


## Problem
FAA ATC staffing reductions constrain departure capacity at HNL. 
Given route demand, aircraft availability, and operational cost 
structures, how should an airline optimally reassign its fleet to 
minimize cost while satisfying demand and capacity constraints?

## Key Results
- Successfully scheduled all required inter-island HNL routes meeting full 
  demand under heightened FAA ATC departure capacity constraints
- Minimized total variable operational cost: ~$180,000
- Grey/blackout zone cost structure captures the true cost of 
  constrained departure windows — optimal schedule balances 
  peak hour limits against extended operation penalties

## Model Structure
- Decision variables: binary assignment variables (1/0) indicating whether a given aircraft
  is scheduled on a specific route during a given departure window
- Objective function: minimize total operational cost
- Constraints: route demand, plane occupancy, ATC departure limits
- Cost components: fuel (E190 aircraft burn rate proxy), staffing (BLS + FLSA overtime), 
  grey zone/blackout zone penalty structure

## Key Methods
- Linear programming
- Grey zone/blackout zone cost modeling
- Literature grounded in Abara → Hane et al. → Delta Coldstart 
  model progression
  
## In This Repo
writeup/ 
- hnl_fleet_assignment_report.pdf: contains the extended write-up of this optimization
  problem, including abstract, problem overview, literature review, methodology, experiment
  results, model analysis, appendices, and references.
model/   LP implementation
  - AppendixE_HNL_scheduling_LP.py: contains the code developed to execute this optimization      problem and develop cost-effective route scheduling across peak-hours and grey-zone
    departure times.
data/
  - AppendixData_HNL_arrivals_20250226.xlsx: contains data from the Bureau of Transportation
    Statistics detailing arrivals at HNL airport on Hawaiian Airlines on Feb 26, 2025.
  - AppendixData_HNL_departures_20250226.xlsx: contains data from the Bureau of
    Transportation Statistics detailing departures from HNL airport on Hawaiian Airlines on
    Feb 26, 2025.
  - AppendixData_hnl_flights_summary_20250226.xlsx: contains inter-island flight summary
    data, including route costs, demand, and required staffing. Derived from
    AppendixData_HNL_arrivals_20250226.xlsx and AppendixData_HNL_departures_20250226.xlsx.
  - island_flights_cleaned.csv: contains a fully cleaned dataset used to run the fleet
    assignment optimization problem, including route costs, demand, and required staffing.
    Derived from AppendixData_hnl_flights_summary_20250226.xlsx.

## Credits
Developed as part of a collaborative academic project.

**Allison Kane**
- Problem framing and introduction
- Model development and formulation
- All LP implementation and code
- Cost basis research and appendices
- Results analysis and limitations
- Literature review (substantial revision and restructuring)

**Collaborator**
- Initial project conception
- Literature review first draft and source identification
- Sensitivity analysis
