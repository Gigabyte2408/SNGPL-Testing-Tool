# SNGPL-Testing-Tool
A script that takes in data about EVC's and computes problem spots or malfunctions in the data according to a specified list of scrutiny points.
I completed this project as part of an internship for Sui Northern Gas Pipelines Limited. The purpose was to reduce the amount of time that chemical engineers spend analysing the datasets by creating a tool that automatically runs the analysis based on user input.
All the inputs for each function may not be the best of inputs, but the point was to allow for the inputs to be changed so that the relevant users could update it as they see fit.
This file contains code for analysing and organizing datasets belonging to Sui Northern Gas Pipelines Limited. Specifically, it id designed to analyse EVC (Electronic Gas Volume Corrector) Data.

Each dataset contains thousands of rows (the data is hourly) and has 25+ columns where each column is a parameter relating to the EVCs. Example parameters include minimum pressure, maximum pressure, flow, teperature, battery volatage, time, and more.

Each of the below functions has its own purpose. Each function organizes the dataset according to some scrutiny point (e.g. any points with 0 pressure, or any points with 0 or reduced flow).

After finding all rows that satisfy that criteria, the function creates a CSV file containing rows that pertain to that scrutiny point from the larger dataset.

Each function also saves the resultant rows to a new and smaller file. So at the end of the program, each function will write to a csv file inside a folder called scrutiny files.

At the end the program compiles the results of all the scrutiny points into a table so a user may see which scrutiny points have the greatest number of concerned rows and are thus deserving of more attention.

Apart from inputting the inputs for each function through the command line interface, this program makes use of a config file using config parser to allow the user to enter the relevant inputs.
