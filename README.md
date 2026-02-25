# DEZoomcamp_HW1
data engineering course homework 1

Question 1:

> docker run -it --rm --entrypoint=bash python:3.13

> pip -V

Answer: pip 25.3

Question 2:
Answers: 
  - postgres:5432
  - db:5432

Question 3: 

> select count(*) from green_taxi_data where lpep_pickup_datetime > 2025_11_01 AND lpep_pickup_datetime < 2025_12_01 AND trip_distance <= 1.09

Answer: 8007

Question 4:

> select lpep_pickup_datetime from green_taxi_data where trip_distance = (SELECT MAX(trip_distance) from green_taxi_data where green_taxi_data.trip_distance < 100.00)

Answer: 2025-11-24

Question 5:

>create table trimmed_green as select g1.lpep_pickup_datetime, g1."PULocationID", z1."LocationID", z1."Zone" from green_taxi_data g1 LEFT JOIN zone_lookup z1 on g1."PULocationID" = z1."LocationID" where g1.lpep_pickup_datetime > '2025-11-17' and g1.lpep_pickup_datetime < '2025-11-19'

>select "LocationID" , SUM("LocationID"), "Zone"  from trimmed_green group by "LocationID", "Zone" ORDER BY SUM("LocationID") DESC

> first in the output will be the correct answer

Answer: East Harlem North

question 6:

> select g1.lpep_pickup_datetime, g1."PULocationID", g1."DOLocationID", g1.tip_amount, z1."LocationID", z1."Zone" from green_taxi_data g1 LEFT JOIN zone_lookup z1 on g1."DOLocationID" = z1."LocationID" where g1.lpep_pickup_datetime >= '2025-11-01' and g1.lpep_pickup_datetime < '2025-12-01' and g1."PULocationID" = 74 ORDER BY g1.tip_amount DESC

Answer: Yorkville West


