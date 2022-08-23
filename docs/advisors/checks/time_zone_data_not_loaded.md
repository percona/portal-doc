# time zone data not loaded

## Description
Checks if the mysql time zone data is loaded or not. More information: https://dev.mysql.com/doc/refman/8.0/en/time-zone-support.html

## Rule
 count(*) as timezonecount from mysql.time_zone_name

## Resolution
Please consider loading time zone data.