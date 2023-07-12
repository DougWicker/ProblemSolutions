# User's Third Transaction
### SQL - datalemur.com

#### Description
Assume you are given the table below on Uber transactions made by users. Write a query to obtain the third transaction of every user. Output the user id, spend and transaction date.

#### Solution
```SQL
SELECT user_id, spend, transaction_date
FROM (
  SELECT user_id, spend, transaction_date,
    ROW_NUMBER() OVER(PARTITION BY user_id ORDER BY transaction_date) AS rn
  From transactions
) As subquery
WHERE rn = 3
```

#### Output
| user_id | spend | transaction_date |
|:------:|:-------------:|:------:|
| 111 |       89.60       |02/05/2022 12:00:00|
| 121 |       67.90       |04/03/2022 12:00:00|
| 263 |       100.00       |07/12/2022 12:00:00|
