# MySQL binaries are 32-bit

## Description
Older versions of MySQL server (plus some custom compilations) might be compiled for 32-bit platforms.
However, we suggest using the new 64-bit version.


## Rule
`Select @@global.version_compile_machine as version_compile_machine == ‘i686’`


## Resolution
Binaries should be reinstalled but using the 64-bit version of the version binaries used.

## Need more support from Percona?
Subscribe to Percona Platform to get database support with guaranteed SLAs or proactive database management services from the Percona team.

[Learn more :fontawesome-solid-paper-plane:](https://per.co.na/subscribe){ .md-button }