# How many people are in Heathrow terminal 5 now?
I'm not aware of any footfall counting source, but I think the best way to determine this will be understanding the capacity of flights leaving and arriving, relative to the time now.

### Logic:
The number of people in Heathrow T5 right now is equal to: 
1. The capacity of flights leaving now and for the next 90 minutes __plus__ 
2. the capacity of flights which have landed in the last half an hour, as people don't tend to wait in the airport as long after they have landed.

### Steps:
1. Calculate number of seats on flights leaving t5 at __the present time + 90 minutes__
2. Calculate number of seats on flights which have __landed in the last 30 minutes__ as they don't tend to wait in the airport once they have arrived
3. Understanding the capacity of the planes from the plane type. Will need to match the flight # and plane type the flight number corresponds to

### Assumptions:
1. multiple plane types aren't assigned to the same plane number. i.e. BAW952 will always be an A380


### Blockers:
__Head count in each plane__  
presently I haven't found a source of information that tells you the capacity of a flight. This historical data could be bought from the airlines themselves and predicted
this script uses local UTC time within its filters on an updating datasource so it can be run at any time of day to get the most accurate answer

- Maybe i could go to an aggregator to source flight fullness. Data sources aren't great/free.

- I have found a dataset with many plane capacities in the seatcapacity.ipynb file but the seat capacity seems wrong. 

__Terminal 5 issue__  
- We could determine the t5 population by filtering by the gates A1-A23, B32 - B48,  c52 - C66
- I think the data provided by the API is able to tell us the terminal. 

__change of datasource__
This project has changed datasources from scraping from the Heathrow page to an API called flight aware
- datasource is scraped from the live JSON that feeds the tables on https://www.heathrow.com/departures and https://www.heathrow.com/arrivals
- since I last looked at this, Heathrow have banned get requests to their server that feeds the website. Very annoying. 
- I've found something at https://flightaware.com/ that looks like it can deliver the same deal. 

Pausing this project until I can find a better source of information for number of seats on a plane, or plane capacity. 

I could 
