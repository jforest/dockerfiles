dockerfiles
===========

# TAGS
## base
Just updated the os, and updated the apt sources

## smoketcp
To use this image `docker run jforest/testing:smoketcp --help`
By default, `targetFile=/etc/smoketcp_targets` and `--debug=true` are set.

```
Usage of /usr/local/bin/smoketcp:
  -bucket="smoketcp": Graphite bucket prefix
  -debug=false: if true, turn on debugging output
  -interval=10: How often to run the tests
  -statsdHost="localhost": Statsd Hostname
  -statsdPort="8125": Statsd port
  -targetFile="targets": File containing the list of targets, ex: server1:80
```

Obviously, you may want to set your targets file, which is a file of `<host>:<port>` one per line

```
google.com:80
google.com:443
example.com:8080
localhost:8125
```

`docker run -v /path/to/mytargetsfile:/etc/smoketcp_targets jforest/testing:smoketcp` 
