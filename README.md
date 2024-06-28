

#Alphabet Soup

You have been contracted from a newspaper tasked with the job of providing an answer key to their word search for the Sunday print. The newspaper's word search is a traditional game consisting of a grid of characters in which a selection of words have been hidden. You are provided with the list of words that have been hidden and must find the words within the grid of characters.


Requirements
Load a character grid with scrambled words embedded within it and a words list of the words to find.  The following conditions apply:

Within the grid of characters, the words may appear vertical, horizontal or diagonal.
Within the grid of characters, the words may appear forwards or backwards.
Words that have spaces in them will not include spaces when hidden in the grid of characters.


Input Format
The program is to accept a file as input. The file is an ASCII text file containing the word search board along with the words that need to be found.
The file contains three parts. The first part is the first line, and specifies the number of rows and columns in the grid of characters, separated by an 'x'. The second part provides the grid of characters in the word search. The third part in the file specifies the words to be found.
The first line indicates how many following lines in the file contain the rows of characters that make up the word search grid. Each row in the word search grid will have the specified number of columns of characters, each separated with a space. The remaining lines in the file specify the words to be found.

The file format is as follows:

3x3
A B C
D E F
G H I
ABC
AEI
ABC 0:0 0:2
ABC 0:0 0:2
AEI 0:0 2:2
5x5
H A S D F
G E Y B H
J K L Z X
C V B L N
G O O D O
HELLO
GOOD
BYE


# Paging-Mission
Paging Mission Control

You are tasked with assisting satellite ground operations for an earth science mission that monitors magnetic field variations at the Earth's poles. A pair of satellites fly in tandem orbit such that at least one will have line of sight with a pole to take accurate readings. The satellite’s science instruments are sensitive to changes in temperature and must be monitored closely. Onboard thermostats take several temperature readings every minute to ensure that the precision magnetometers do not overheat. Battery systems voltage levels are also monitored to ensure that power is available to cooling coils. Design a monitoring and alert application that processes status telemetry from the satellites and generates alert messages in cases of certain limit violation scenarios.

Requirements
Ingest status telemetry data and create alert messages for the following violation conditions:

If for the same satellite there are three battery voltage readings that are under the red low limit within a five minute interval.
If for the same satellite there are three thermostat readings that exceed the red high limit within a five minute interval.


Input Format
The program is to accept a file as input. The file is an ASCII text file containing pipe delimited records.
The ingest of status telemetry data has the format:

<timestamp>|<satellite-id>|<red-high-limit>|<yellow-high-limit>|<yellow-low-limit>|<red-low-limit>|<raw-value>|<component>
You may assume that the input files are correctly formatted. Error handling for invalid input files may be ommitted.

Output Format
The output will specify alert messages.  The alert messages should be valid JSON with the following properties:

{
    "satelliteId": 1234,
    "severity": "severity",
    "component": "component",
    "timestamp": "timestamp"
}

Sample Data
The following may be used as sample input and output datasets.

Input

20180101 23:01:05.001|1001|101|98|25|20|99.9|TSTAT
20180101 23:01:09.521|1000|17|15|9|8|7.8|BATT
20180101 23:01:26.011|1001|101|98|25|20|99.8|TSTAT
20180101 23:01:38.001|1000|101|98|25|20|102.9|TSTAT
20180101 23:01:49.021|1000|101|98|25|20|87.9|TSTAT
20180101 23:02:09.014|1001|101|98|25|20|89.3|TSTAT
20180101 23:02:10.021|1001|101|98|25|20|89.4|TSTAT
20180101 23:02:11.302|1000|17|15|9|8|7.7|BATT
20180101 23:03:03.008|1000|101|98|25|20|102.7|TSTAT
20180101 23:03:05.009|1000|101|98|25|20|101.2|TSTAT
20180101 23:04:06.017|1001|101|98|25|20|89.9|TSTAT
20180101 23:04:11.531|1000|17|15|9|8|7.9|BATT
20180101 23:05:05.021|1001|101|98|25|20|89.9|TSTAT
20180101 23:05:07.421|1001|17|15|9|8|7.9|BATT


Ouput

[
    {
        "satelliteId": 1000,
        "severity": "RED HIGH",
        "component": "TSTAT",
        "timestamp": "2018-01-01T23:01:38.001Z"
    },
    {
        "satelliteId": 1000,
        "severity": "RED LOW",
        "component": "BATT",
        "timestamp": "2018-01-01T23:01:09.521Z"
    }
]


OUTPUT
HELLO 0:0 4:4
GOOD 4:0 4:3
BYE 1:3 1:1
