# MySQL InnoDB strict mode not correct

## Description
When InnoDB strict mode is disabled, it's possible to have incompatible settings for 
KEY_BLOCK_SIZE, ROW_FORMAT, DATA DIRECTORY, TEMPORARY, and TABLESPACE table options.  Enabling it will force InnoDB to make sure these create options are compatible with each other and other settings.

In addition, enabling Strict mode checks row size when creating or altering a table. This prevents INSERT or UPDATE from failing due to the record being too large for the selected page size.




## Rule
```
        SELECT @@global.innodb_strict_mode;
```

## Resolution
The **innodb_strict_mode** setting is enabled by default. Percona strongly recommends leaving this setting enabled.  
This is an online change that you can apply with:

`SET GLOBAL innodb_strict_mode=ON;`


## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }
