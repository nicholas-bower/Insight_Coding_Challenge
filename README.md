# Insight Coding Challenge


This is breif script written for the Insight Data Engineering Fellowship. I was presented with the problem of analyzing a sample pharmaseutical dataset. Input files provide the name of drugs, their prescribers and costs. Prospective fellows were tasked with creating new files that included the number of unique prescribers for each drug and their total cost. Though it was not specified by the assignment, I elected to sort the output file by cost simply to make it easier to find the most expensive drugs.

The analysis is writen in python, making use of the pandas data analysis plugin (the only library that doesn't come standard.) I have included a sample input file with 500 entries, and the resulting output that is obtained by running the script on the sample.

## Getting Started

As mentioned in the above section this is a very straight forward program to run, only requiring python, a properly formatted by input file, and the pandas package.

### Prerequisites
The Pandas package (for more inmormation visit their [website](https://pandas.pydata.org/)) is an open source data analysis tool. The latest release can be dowloaded using conda from conda-forge or the default channel: 
```
conda install pandas
```
or using PyPl
```
python3 -m pip install --upgrade pandas
```


## Running Instructions
The program is fairly straightfoward to run, taking only a few parameters. The defaults are set to run on the sample input, and save to the same location as the sample output. A full description of these parameters are displayed bellow. These defaults are written with the understanding that the code is being run from the directory containing the input and output files directories contained in this reposetory.
* -i point to the location of a properly .txt input file. If no input is specified the script will use the sample input
* -o point to the location where the output will be saved. If none is specified the script will overwrite the sample output.
* -h specify the location of the header line (aka a line in the input data file which labels each of the columns.) The sample file includes a header on the first line and presumably all inputs will be in this format, but on the offchance they aren't this argument has been included. If no header is present enter 0.
* -n how many entries from the input file to incude in the analysis. For testing it is often useful to only run over a small subset of the data. Entering a negative number or not including this argument will simply make the script run on all input entries.

An example run command looks like this
```
python Pharma_DataAnalyzer.py -i ./input/de_cc_data.txt -h 1 -n -1 -o ./output/top_cost_drug.txt
```

## My approach

Pandas is perfectly tailored to this challenge, to the extent that it almost feels like cheating. Pandas is able to use opperations which work segnificantly more efficiently than line by line analysis methods using for loops. I was able to easily subdevide that dataset by drug name, and find the number of unique prescribers for each subdevision and sum up the total amount spent on each drug using methods contained in the pandas library.
