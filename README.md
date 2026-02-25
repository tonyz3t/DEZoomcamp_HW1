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



