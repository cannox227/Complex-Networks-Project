# Complex-Networks-Project
Final course project - Aalto University CS-E5740 Complex Networks, Autumn 2023

# About the project

## Preface
The topic of this project work that we have been running for a long time has, unfortunately, become all too real in the recent years. This shows that pandemics are not entirely unexpected, and the way how they spread through the globe has also been foreseen for a long time. In fact, if one would use global air transport data, a more complex disease model (SEIR), and the real geographic origin of spread, one would get a timeline that eerily matches early 2020.
## Introduction
In the project work, your task is to implement a Susceptible-Infected (SI) disease spreading model and run it on top of a temporal network from air transport data, containing information on the departure and arrival times of flights. You will study the dynamics of spreading and how it depends on where the process starts as well as the infectivity of the disease, and use static network centrality measures to understand the roles that specific nodes play.
## Model specifications
In the SI model, each node is either Susceptible (S) or Infected (I). When an Infected node is in contact with a Susceptible node, the Susceptible node may become infected with some probability p ∈ [0,1], reflecting the infectivity of the disease. Infected nodes remain Infected forever.
In our model that mimics the spreading of disease through the air transport network, nodes are airports and time-stamped connections are flights between them. Initially, only one airport node (called the seed node) is set to the Infected state, while all other airports are Susceptible. Now, following the SI process, a flight from an Infected source airport infects its Susceptible destination airport with probability p ∈ [0,1]. Note that a flight can carry the infection only if its source airport is infected at the time of the flight’s departure! Infected airports remain infected for the rest of the simulation.
## Data description
The data that are used in the project are available on the course MyCourses page in one .zip file as well as at /coursedata in Jupyterhub. The flight data that you will use to perform your simulation are located in the file events_US_air_traffic_GMT.txt, where each row contains the following fields:

    1st column -> Source [0-278]
    2nd column -> Destination [0-278]
    3rd column -> Start Time (GMT) [seconds after Unix epoch time]
    4th column -> End Time (GMT)
    5th column -> Duration [Same as (EndTime-StartTime)]

You can find the information about the airports in file `US_airport_id_info.csv`. `US_air_bg.png` is an image of the USA map used as a background image in some visualizations.

# Run 
## Use the current virtual env
1. Activate the virtual env
```
source complex-net/bon/activate
```

## Use another virtual env
1. Create a virtual env
```
python3 -m venv <env_name>
```
2. Activate the virtual env
``` 
source <env_name>/bin/activate
```
## Run the notebook
The whole project is contained in the file `project.ipynb`