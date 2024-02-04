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
-FROM
  `bigquery-public-data.world_bank_health_population.health_nutrition_population`
# 6. Find average of values and limit to 10
- SELECT
  - AVG(value) AS average_value
- FROM
   `bigquery-public-data.world_bank_health_population.health_nutrition_population`
- GROUP BY
  - country_name
# 7. Find the countries with Highest Population and limit it to 10
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
# 8. Find the country with lowest life expectancy and limit it to 10
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
