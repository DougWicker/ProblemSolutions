# Page With No Likes
### SQL - datalemur.com

#### Description
Assume you're given two tables containing data about Facebook Pages and their respective likes (as in "Like a Facebook Page").
Write a query to return the IDs of the Facebook pages that have zero likes. The output should be sorted in ascending order based on the page IDs.

#### Solution
```SQL
SELECT pages.page_id
FROM pages
FULL OUTER JOIN page_likes
ON pages.page_id = page_likes.page_id
WHERE liked_date IS NULL
ORDER BY pages.page_id ASC;
```

#### Output
|  page_id  |
|:------:|
| 20701 |       
| 32728 |       
    
