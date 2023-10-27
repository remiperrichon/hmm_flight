# How to reproduce the results?
### Step 1: Download raw data 

- Go the NASA DASHlink project page: https://c3.ndc.nasa.gov/dashlink/projects/85/ (last check : 2023/10/27)
- Download data "Flight Data For Tail 687" 
- Gather all Matlab files in one folder named "raw_data" (5,376 flights in total)

### Step 2: Execute the R script "00_Clean_NASA_raw.R"

For each individual file (Matlab file), a .csv file is created if the flight is valid. 
Create and specify a folder to store all the clean flights "clean_data" (2,868 flights in total)

### Step 3: Execute the several R scripts to reproduce the code 

- "01_Vizu_NASA_sample.R" (draw a flight at random and plot it)
- "02_HMM_uni_unique.R" (specify a flight and perform a HMM to segment 3 main flights phases : climb, cruise, approach)
- "03_HMM_uni_unique_missing.R" (specify a flight and perform a HMM to segment 3 main flights phases : climb, cruise, approach. 500 points are randomly taken as missing).
- "04_HMM_multi_unique.R" (specify a flight and perform a HMM to segment 6 flight phases : taxi, takeoff, climb, cruise, approach, rollout).

The "Fuzzy_logic.R" script has all the fuzzy logic functions that are needed.

To compute F1-score per phase as well as the global accuracy, just make a for loop with the above scripts to segment each flight. 
