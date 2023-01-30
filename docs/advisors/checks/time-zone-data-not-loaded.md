# Time zone data not loaded

## Description

Checks if the MySQL time zone data is loaded or not.
For more information, see [MySQL Server Time Zone Support](https://dev.mysql.com/doc/refman/8.0/en/time-zone-support.html) in the MySQL documentation.

## Rule

 count(*) as timezonecount from mysql.time_zone_name

## Resolution

Consider loading time zone data.

## Need help with this?

[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact?utm_source=pmm&utm_medium=banner&utm_campaign=advisors_readmore){ .md-button }