# team-pollinate-get-results
Utility script for the TeamPollinATE project (Goulson Lab, University of Sussex)

# What it does
1. Get data of all users from the project database (containig allotment recordings and results from signup surveys)
2. Turn it into a local .csv file that can be read by a spreadsheet program (Excel, Google Spreadsheets...)
3. Upload this file to Firebase Cloud Storage (so

# Requirements
This script has been tested using the following setup:
- Operating system: Ubuntu 16.04.5 64-bit
- Software
  - node v8.11.3
  - yarn v1.10.1

# Installation
1. Open a terminal emulator
2. Clone this repository to get the script: in the terminal, type `git clone https://github.com/alvarocaceresmunoz/team-pollinate-get-results` then press `Enter`
2. Go to the repository root directory: type `cd team-pollinate-get-results` then press `Enter`
3. Install the Node.js modules required by the script: type `console yarn add` then press `Enter`
4. Make the script executable: type `chmod +x ./run.js` then press `Enter`

# Usage
- To get help, type `./run --help` (or `./run -h` for short) 
- To get data from the database with real users, type `./run --database production` (or `./run -d production` for short)
- To get data from a test database, type `./run --database development` (or `./run -d development` for short)

# Scheduling this script
*Warning: in order to make this work, the script needs to be fixed so that it can exit on its own, rather than having to press Ctr-C.*

If you want to schedule data gathering from the database (i.e. executing the script at a given date periodically), you can do so by using [crontab](https://en.wikipedia.org/wiki/Cron), a job scheduler for Linux.

You will need to edit a crontab file by typing `crontab -e` on the terminal. This will open the crontab configuration file in a text editor. The crontab file specifies how often do you want the job to be executed. For example, if you want to gather data every 6th of October at 17:01, you would have to paste this into your crontab file:

```01 17 6 10 * pathToTheScript/run --database production```

(This would be read as: _"at minute 01, hour 17, day 6, month 10, of every (*) year, execute_ `run --database production` _"_)

# To-do
- Make the script send an email to researchers with the .csv file attached
- Upload the script to the cloud (eg. AWS, OpenShift, Heroku...)
- Schedule the script in the selected cloud service
