# MongoDB Version check 

## Description
This advisor check rolls through a list of available versions and warns if MongoDB or Percona Server for MongoDB version is not the latest one.

The goal is to follow updated and optimal upgrade plans and paths. This avoids possible bugs and security issues. 

For Production systems: We recommend upgrading to the latest patch release for major or minor stable versions. 


## Rule
```MONGODB_BUILDINFO

version = parse_version(info["version"])
          print("version =", repr(version))

if is_percona:
              latest = LATEST_VERSIONS["percona"][mm]
              if latest > num:


          if True:  # MongoDB
              latest = LATEST_VERSIONS["mongodb"][mm]
              if latest > num:ity": "warning",
              })
          return results
```

## Resolution
Upgrade to the latest patch release for major or minor stable versions as soon as possible.

For example, if  you are currently running version major version 4.4.x, upgrade to version 4.4.16.

## Need help with this?

[Ask a Percona Expert :fontawesome-solid-paper-plane:](https://www.percona.com/about-percona/contact?utm_source=pmm&utm_medium=banner&utm_campaign=advisors_readmore){ .md-button }