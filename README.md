--1. What is the minimum number of cases in this table where the value is not null?
SELECT
  --MIN(value) AS minimum_cases
  --2. List the years where limit is 10
  --year
  --3. Select the entire table
  --*
  --4. Count the country_name 
  --Count (country_name)
  --5. List the country_name from the table
  --Distinct (country_name)
  --6. Find avearge of values and limit to 10
  --AVG(value) AS average_value
  --7. Find the country with Highest population
  country_name,
  --MAX(value) as Highest_Population
  --8. Find the country with lowest life expectancy and limit to 10
  MIN(value) as Lowest_LifeExpectancy
FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
--WHERE
  --value IS NOT NULL;
  --year IS NOT NULL
GROUP BY
  country_name
ORDER BY
  --Highest_Population DESC
  Lowest_LifeExpectancy ASC
LIMIT
  10


