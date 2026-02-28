# Group 11: Transit Data

## Reading Data + Cleaning
---
The raw data contained, 1300 entries of transit routes. The table follows the schema:
| Trip ID | Date (yyyy-mm-dd) | Route | Vehicle Type | Time of Day | Passenger Count | Delay (minutes) | Fare Type | Payment Method | Day Type |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |

The table was found to contain missing data in the "Passenger Count" and "Delay" columns. Entries for a "Date" has been represented as a String instead of a datetime Object. These inconsistencies have been fixed, by removing entries with null data, and casting the String containing the initial date into a datetime Object using a panda function.

After cleaning, the number of rows decrease down to 1188 entries. 
- 3.77% "Delays (minutes)" were null.
- 4.85% "Passenger Count" were null.
## Data Analytics
---

| Fare Type | # |
| ----------- | ----------- |
| Senior | 184 |
| Adult | 666 |
| Student | 295 |
| Child | 155 |

| Payment Method | # |
| ----------- | ----------- |
| Card | 793 |
| Mobile App | 271 |
| Cash | 236 |

| Day Type | # |
| ----------- | ----------- |
| Weekday | 898 |
| Weekend | 402 |

| Vehicle Type | # |
| ----------- | ----------- |
| Bus | 662 |
| Train | 445 |
| Tram | 193 |

| Routes | # |
| ----------- | ----------- |
| B | 276 |
| E | 268 | 
| D | 259 |
| A | 258 |
| C | 239 |


| Time of Day | # |
| ----------- | ----------- |
| Evening Rush | 449 |
| Morning Rush | 442
| Midday | 292 |
| Night | 117 |


---
#### Question1:  Which route has the highest average delay?
| Route | A | B | C | D | E |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | 
| Avg.Delay (minutes) | 2.69 | 2.38 | 2.46 | 2.87 | 2.35 | 

Route D has the longest delay.
- passengers: 17 - 47 (avg. 30)
- longest delay: 19 minutes

<img width="567" height="458" alt="average delay by route" src="https://github.com/user-attachments/assets/ebeb3bde-d17e-42aa-9f71-d1d88bd81802" />

- Allows us to compare the average delay in correspondence to route chosen.

#### Question2: How does passenger count differ between peak and off-peak hours?
| count | mean | median | std |
| ----------- | ----------- | ----------- | ----------- |
| Off-Peak | 367 | 30.065395 | 30.0 | 5.383752 |
| Peak | 821 | 30.163216|30.0|5.557475 |

- On-Peak sees 454 additional passengers than Off-Peak.  On-peak is categorized as Morning and After Rushes, while Off-Peak is Midday and Midnight times

<img width="578" height="445" alt="passenger count on vs off peak" src="https://github.com/user-attachments/assets/8c9200f7-28bd-42a5-971f-c05ef86d40ee" />

- According to this boxplot graph, we can observe that the passenger count is very similar in variability and has the same median. Which doesn't show the number of passengers aren't much affected whether its peak or not.

#### Question3: What percentage of trips use each fare type?
| fare_type | % |
| ----------- | ----------- |
|Adult|50.84|
|Student|22.90|
|Senior|14.14|
|Child|12.12|

- Given the data, we find that adults and students passengers are the two most common users of Transit.

<img width="390" height="411" alt="fare distribution" src="https://github.com/user-attachments/assets/6a3bf592-036a-4975-b0c8-1d10a9b3e902" />
<img width="390" height="411" alt="percentage of trips by fare type" src="https://github.com/user-attachments/assets/01441ce7-4697-4ad6-b8e2-b64493a79977" />

- These graphs allow us to see the fare type distirbution.

#### Question4: How does usage differ between weekdays and weekends?
| day_type | trips | total_passengers | avg_passengers | avg_delay |  
| ----------- | ----------- | ----------- | ----------- | ----------- |                                        
| Weekday | 827 | 24920.0 | 30.13 | 2.65 |
| Weekend | 361 | 10878.0 | 30.13 | 2.32 |

- The usage of transit between weekday and weekends, share the same passenger and delay average. Unsurprisingly, the weekday sees about twice the amount of transit users than weekends.



(Notice the cosistent avg. passengers and avg. delays)

#### Question5: Which vehicle type is most reliable (least delays)?
| vehicle_type | trips | avg_delay | median_delay | on_time_rate |                                              
|  ----------- |  ----------- |  ----------- |  ----------- | ----------- |
|Tram|181|2.25|1.0|30.94|
|Bus|605|2.55|2.0|28.93|
|Train|402|2.69|2.0|28.86|

All Vehicles in general appear to have similar on-time frequencies. Statistically, Trams are more likely to be on time than other vehicle types, albeit by a minor margin.

#### Question6: What is the relationship between passenger count and delays?
By calculating the correlation between the number of passengers and delays, find that the two columns has a relation of 0.0096.

- Inferring that there is little indication that the data between the number of passengers and delays are directly related.

<img width="576" height="455" alt="passenger count vs delay" src="https://github.com/user-attachments/assets/557c11d5-b3e0-4ef9-83b6-b94a2772f1f8" />

- We can also observe here that overall the delay time isn't very correlated to the passenger count. The data points show a spread or evened-out representation. Which backs our result earlier with the pearson correlation being as low as 0.0096

## Analysis
---
- Delays and Passengers surprisingly do not correlate. The number of passengers the transit take on does not appear to impact the delays a route will gain.
- Given the data, Transit System is made out of:

| Vehicle | Distribution(%) | Passengers(min) | Passengers(max) | Passenger(avg) | Worst Delay(minutes) | Avg. Delay(minutes) |
| ----------- | ----------- | ----------- | ----------- | ----------- |  ----------- |   ----------- |
| Bus | 50.9 | 15 | 48 | 30.12 | 16 | 2.54 | 
| Tram| 33.8 | 15 | 49 | 30.22 | 19 | 2.25 |
|Train| 15.2 | 15 | 47 | 30.10 | 17 | 2.68 |

- For each vehicle type, the average quantity of passengers surprisingly remains similiar. 
- All transit vehicles share the same minimum number of passengers. Maximum number of passengers varying by a single passenger.
- Regardless of vehicle type and passenger quantity, the delay remains the same. Implying 
- The passenger counts are about double during on-Peak hours veruses off-Peak than during
- The passenger count are more than doubled during Weekdays veruses Weeklimit
