# Vio.com Coding Challenge

## Geolocation Service

### Overview

You are provided with a CSV file (`data_dump.csv`) that contains raw geolocation data. The goal is to develop a service that imports such data and exposes it via an API.

Sample data:

```
ip_address,country_code,country,city,latitude,longitude,mystery_value
200.106.141.15,SI,Nepal,DuBuquemouth,-84.87503094689836,7.206435933364332,7823011346
160.103.7.140,CZ,Nicaragua,New Neva,-68.31023296602508,-37.62435199624531,7301823115
70.95.73.73,TL,Saudi Arabia,Gradymouth,-49.16675918861615,-86.05920084416894,2559997162
,PY,Falkland Islands (Malvinas),,75.41685191518815,-144.6943217219469,0
125.159.20.54,LI,Guyana,Port Karson,-78.2274228596799,-163.26218895343357,1337885276
```

### Requirements

1. Develop a library/component with two main features:
   - A service that parses the CSV file containing the raw data and persists it in a database;
   - An interface to provide access to the geolocation data (model layer);
1. Develop a REST API that uses the library above to expose the geolocation data.

In doing so:

- Define a data format suitable for the data contained in the CSV file.
- Sanitise the entries: the CSV file comes from an unreliable source, which means that the entries can be duplicated, may miss some value, the value can not be in the correct format, or maybe completely bogus.
- At the end of the import process, return some statistics about the time elapsed, as well as the number of entries accepted/discarded.
- The library should be configurable by an external configuration (particularly with regards to the DB configuration).
- The API layer should implement a single HTTP endpoint that, given an IP address, returns information about the IP address location (e.g. country, city).

### Output

1. We expect to see the code for the following, available in one or multiple Git repositories (ex. GitHub, GitLab, Bitbucket, ...):

   - A library/component that packages the import service and the interface for accessing the geolocation data.
   - A REST API application that uses the library above.

2. We also expect to see the application running. To do that, the code should be deployed on a Cloud Platform of your choice (e.g. [Gigalixir](https://www.gigalixir.com/), [Heroku](https://www.heroku.com/), [Fly.io](https://fly.io/), [Digital Ocean](https://www.digitalocean.com/), AWS, Google Cloud or Azure), and the sample data, should be imported into the deployed application (according to the cloud platform limits). Please use `cloud_data_dump.csv` as the file to import into the deployed application.
3. We would like to see your train of thought and trade-offs written down. To do so, please include a README file in the root folder of the API repo.

#### Bonus

The following items can add extra points to your evaluation, but you are not expected to work on them:

- The API application is Dockerised.
- The API application is deployed as a container.

### Notes

- The file's contents are fake, you do not have to worry about data correctness.
- The import service would run as part of a scheduled/cron job in production. **We don't want that part implemented as part of this exercise**, but you can think of an interface or script to trigger the importing process.
- For running the application locally (development) a DB container can be included.
- You can structure the repository as you see fit.

### Evaluation

The following are the criteria we will use to evaluate your work:

- Code quality;
- Well-tested solution;
- Best code practices in general;
- Architectural design skills;
- API design and data structure skills (i.e. correctness of the API responses, etc.);
- Communication and writing skills (i.e. documentation on how the apps work, setup, and tradeoffs).
