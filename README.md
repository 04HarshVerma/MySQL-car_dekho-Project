# MySQL-car_dekho-Project
create schema cars;
use cars;
-- READ DATA--
select*from car_dekho;
-- Total Cars: To get a count of total records--
select count(*) from car_dekho;
-- how many cars will be avaliable in 2023?--
select count(*) from car_dekho where year = 2023;
-- how many cars is available in 2020,2021,2022--
select count(*) from car_dekho where year = 2020; #74
select count(*) from car_dekho where year = 2021; #7
select count(*) from car_dekho where year = 2022; #7
-- Group by--
select count(*) from car_dekho where year in (2020,2021,2022) group by year;
-- Clint asked me to print the total of all cars by years. I don't see all the details--
select year, count(*) from car_dekho group by year;
-- Clint asked to car dealer agent how many diesel Cars will there be in 2020?--
select count(*) from car_dekho where year = 2020 and fuel = "Diesel";

-- Clint requested a car dealer agent how many petrol cars will there be in 2020?--
select count(*) from car_dekho where year = 2020 and fuel = "petrol"; #51


-- Print all the cars (petrol, diesel, and CNG) come by all year.--alter
select year, count(*) from car_dekho where fuel = "Petrol" group by year;
select year, count(*) from car_dekho where fuel = "Diesel" group by year;
select year, count(*) from car_dekho where fuel = "CNG" group by year;


-- There were more than 100 cars in a given year, which year had more than 100 cars?--
select year, count(*) from car_dekho group by year having count(*)>100;
select year, count(*) from car_dekho group by year having count(*)<50;

-- All car count details between 2015 and 2023; we need a complete list.--
select count(*) from car_dekho where year between 2015 and 2023;

-- All cars details between 2015 to 2023 we need complete list--
select*from car_dekho where year between 2015 and 2023;

-- END --
