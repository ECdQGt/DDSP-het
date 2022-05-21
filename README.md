# DDSP-het
Instance data for DDSP-het, used in the working paper "Point-to-point and milk run delivery scheduling: models, complexity results, and algorithms based on Benders decomposition" by Simon Emde, Shohre Zehtabian, and Yann Disser

## Description of the file format
The instance data are spread over two text files containing comma-separated values (CSV). The first file ('DDSP-het_trip_data.csv') contains the basic instance data like number of trips etc. as well as information about the individual trips. The second file ('DDSP-het_milk_run_data.csv') contains details about which trips can be combined into milk runs. A complete instance can only be reconstructed by reading both files. The files contain a table each, where individual columns are separated by semicolons (";").

### TRIP DATA
The first table contains the following information about each instance:
- Column IDENTIFIER contains the name string identifying the instance, corresponding to the instance names in the result tables of the paper.
- Column NUMBER_OF_TRIPS contains the number n of trips.
- Column NUMBER_OF_CLASSES contains the number |C| of different truck classes.
- Column PROCESSING_TIMES contains the processing times of each trip. Note that each trip is associated with |C| different processing times, separated by dashes ("-"), because the trucks may not operated at the same speed. The trips are separated by a vertical bar ("|"). Hence, "|1-2|3-4|..." would denote that the first trip takes 1 time unit to process on a truck of class 1 and 2 time units on a truck of class 2. The processing time of trip 2 is 3 and 4 time units for truck classes 1 and 2, respectively, and so on.
- Column RELEASE_DATES gives the release dates for every trip, separated by dashes ("-").
- Column DUE_DATES gives the due dates for every trip, separated by dashes ("-").
- Column TRIPS_WEIGHTS gives the weight in the objective function for every trip, separated by dashes ("-").
- Column GAMMA denotes number of trucks available for each class, separated by dashes ("-").

### MILK RUNS
The second table lists the information about possible trip combinations into milk runs. It contains the following fields:
- IDENTIFIER refers back to the instance for which the milk run is defined. The name string is equivalent to one of the identifiers in the "TRIP DATA" table.
- PROCESSING_TIMES contains the processing time of the milk run for each truck class, separated by dashes ("-").
- TRIPS lists the set of trips contained in this milk run, where the individual trip numbers are separated by a vertical bar ("|").
- RELEASE_DATE contains the release date of the milk run.
- DUE_DATE contains the due date of the milk run.
- WEIGHT contains the weight in the objective function of the milk run.
