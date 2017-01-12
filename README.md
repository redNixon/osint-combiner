# vulnerabilityfinder
Combining OSINT sources in Elastic Stack

This project contains: 
+ various Python3 scripts which gather data from OSINT sources, convert them so they fit into Elasticsearch and write the results to outputfiles/*; 
+ logstash config files which use the outputfiles as input for Elasticsearch.

Currently supported OSINT sources:
+ [Shodan.io](https://www.shodan.io/ "Shodan's Homepage")
+ [Censys.io](https://censys.io/ "Censys' Homepage")
+ [IpInfo by DutchSec](http://dutchsec.nl/ "DutchSec's Homepage")

\- [Zoomeye](http://dutchsec.nl/ "Zoomeye's Homepage") is not yet supported because of limitations on their API. They don't respond on e-mails.

## Requirements

Project needs a text file named "config.ini" with the following content:

```
[SectionOne]

ELASTICSEARCH_IP: *{IP of Elasticsearch cluster here}*

SHODANAPIKEY: *{Shodan API key here}*

CENSYS_API_ID: *{Censys API ID here}* 

CENSYS_API_KEY: *{Censys Secret here}*
```

The Python3 scripts need the following modules (can be installed with easy_install3 or pip3): 
+ Shodan
+ Censys
+ Elasticsearch
+ Netaddr
