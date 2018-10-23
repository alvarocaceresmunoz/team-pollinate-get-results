# team-pollinate-get-results
Utility script for the TeamPollinATE project (Goulson Lab, University of Sussex)

# What it does
This small script
1. Gets data of all users from the project database (containig allotment recordings and results from signup surveys)
2. turns it into a local .csv file that can be read by a spreadsheet program (Excel, Google Spreadsheets...)
3. Uploads this file to Firebase Cloud Storage (so

# Requirements
This script has been tested using the following setup:
- Operating system: Ubuntu 16.04.5 64-bit
- Software
  - node v8.11.3
  - yarn v1.10.1

# Usage
Clone this repository. Using the terminal, go to the root directory of this project and type
```console
$ yarn add
```
then press `Enter`. This will add all the Node modules required by the script.

# To-do
- Email researchers with the .csv file attached
- Store this script in a 
