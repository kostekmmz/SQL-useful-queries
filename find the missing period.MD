**query**

````sql
SELECT 
distinct n
,case when P is null then 'Root'
when n in (select distinct p from bst) then 'Inner'
else 'Leaf'
end as 'info'
from bst
order by n asc
````
