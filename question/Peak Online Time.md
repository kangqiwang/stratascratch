
You are given a dataset from Amazon that tracks and aggregates user activity on their platform in certain time periods. For each device type, find the time period with the highest number of active users.


The output should contain 'user_count', 'time_period', and 'device_type', where 'time_period' is a concatenation of 'start_timestamp' and 'end_timestamp', like ; "start_timestamp to end_timestamp".

user_activity


start_timestamp:
datetime
end_timestamp:
datetime
user_count:
int
device_type:
varchar
time_difference:
float


```sql
select 
    user_count,
    concat(start_timestamp, ' to ', end_timestamp) as time_period,
    device_type
from user_activity
where user_count = (select max(user_count) from user_activity)


```