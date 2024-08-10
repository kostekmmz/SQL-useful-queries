**query**

````sql
select 
    	min(date_taken)
    	,max(date_taken)
    	,count(*) as period_time
from
(select
    date_taken
    ,date_taken-row_number() over (order by date_taken) as delta
	from lab_samples)
	group by delta
order by 1
````
