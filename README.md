# 1. What is the minimum number of cases in this table where the value is not null?
- SELECT
  - MIN(value) AS minimum_cases
- FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
- WHERE
  - value IS NOT NULL;
# 2. List the years where limit is 10
- SELECT
  - year
- FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
- WHERE
  - year IS NOT NULL
- LIMIT
  - 10
# 3. Select the entire table
- SELECT
  - *
- From
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
# 4. Count the country_name
  - SELECT
    - Count (country_name)
  - FROM
   `bigquery-public-data.world_bank_health_population.health_nutrition_population`
# 5. List the country_name from the table
- SELECT
  - Distinct (country_name)
- FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
# 6. Find average of values and limit to 10
- SELECT
  - AVG(value) AS average_value
- FROM
   `bigquery-public-data.world_bank_health_population.health_nutrition_population`
- GROUP BY
  - country_name
- LIMIT
  - 10
# 7. Find the countries with Highest Population, limit it to 10 and arrange it in descending order
- SELECT
  - country_name,
  MAX(value) as Highest_Population
- FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
- GROUP BY
  - country_name
- ORDER BY
  - Highest_Population DESC
- LIMIT
  - 10
# 8. Find the country with lowest life expectancy, limit it to 10 and arrange in ascending order
- SELECT
  - MIN(value) as Lowest_LifeExpectancy
- FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
- GROUP BY
  - country_name
- ORDER BY
  - Lowest_LifeExpectancy ASC
- LIMIT
  - 10
# 9. Find, where related indicators and country code are equal by left joining the world bank series summary
- SELECT
  - related_indicators,
   country_code
- FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
- LEFT JOIN
  `bigquery-public-data.world_bank_health_population.series_summary` AS additional_data
- ON
  - country_code = additional_data.related_indicators
- LIMIT
   - 10
# 10. Find the health data and the additional data for country_code by left joining the country summary between the years 1970 and 2000
- SELECT
  - health_data.*,
    additional_data.*
- FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population` AS health_data
- LEFT JOIN
  `bigquery-public-data.world_bank_health_population.country_summary` AS additional_data
- ON
  - health_data.country_code = additional_data.country_code
- WHERE 
  - YEAR BETWEEN 1970 AND 2000
