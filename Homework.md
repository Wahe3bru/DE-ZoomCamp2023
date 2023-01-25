# Homework Week1

### Question 1. Knowing docker tags
--iidfile string

### Question 2. Understanding docker first run
3

### Question 3. Count records
```sql
Select count(*) from green_taxi_trips
where DATE(lpep_pickup_datetime) = date('2019-01-15')
and date(lpep_dropoff_datetime) = date('2019-01-15');
```
20530

### Question 4. Largest trip for each day
```sql
select DATE(lpep_pickup_datetime), trip_distance
from green_taxi_trips
where trip_distance = (select MAX(trip_distance) from green_taxi_trips);
```
2019-01-15

### Question 5. The number of passengers
```sql
select COUNT(*)
from green_taxi_trips
where date(lpep_pickup_datetime) = date('2019-01-01')
and passenger_count = 2; --3
```
2: 1282 ; 3: 254


### Question 6. Largest tip
```sql
select Zone from zones
where LocationID = (
  select DOLocationID from green_taxi_trips
	where tip_amount = max(tip_amount)
	and PULocationID = 7
  );
```
### 