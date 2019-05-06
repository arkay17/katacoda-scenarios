
Tests can be run from command line /shell script - mostly by continuous integration tools like Jenkins 

Behave can run tests 
- one file at a time
- all files in the subdirectory
- controlled by tags (explained later)

## Execute using behave

Navigate to the features directory - single file execution

`cd features`{{execute}}

Using behave execute the feature file step containing the scenarios 

`behave weekend.feature`{{execute}}

