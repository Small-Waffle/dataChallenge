# Group 11: Transit Data

## Data
---
The raw data contained, 1300 entries of transit routes. The table follows the schema:
| Trip ID | Date (yyyy-mm-dd) | Route | Vehicle Type | Time of Day | Passenger Count | Delay (minutes) | Fare Type | Payment Method | Day Type |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | ----------- |

The table was found to contain missing data in the "Passenger Count" and "Delay" columns. Entries for a "Date" has been represented as a String instead of a datetime Object. These inconsistencies have been fixed, by removing entries with null data, and casting the String containing the initial date into a datetime Object using a panda function.

After cleaning, the number of rows decrease down to 1188 entries. 
- 3.77% "Delays (minutes)" were null.
- 4.85% "Passenger Count" were null.
## Analysis
---
#### Question1:  Which route has the highest average delay?
| Route | A | B | C | D | E |
| ----------- | ----------- | ----------- | ----------- | ----------- | ----------- | 
| Avg.Delay (minutes) | 2.69 | 2.38 | 2.46 | 2.87 | 2.35 | 

Route D has the longest delay.
- passengers: 17 - 47 (avg. 30)
- longest delay: 19 minutes

#### Question2: How does passenger count differ between peak and off-peak hours?
#### Question3: What percentage of trips use each fare type?
#### Question4: How does usage differ between weekdays and weekends?
#### Question5: Which vehicle type is most reliable (least delays)?
#### Question6: What is the relationship between passenger count and delays?
