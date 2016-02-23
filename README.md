# 1. Install

```sh
$ yum install -y wget java unzip lsof
$ wget http://ftp.unicamp.br/pub/apache/lucene/solr/5.4.0/solr-5.4.0.tgz
$ tar -xvzf solr-5.4.0.tgz
$ ./solr-5.4.0/bin/install_solr_service.sh
```
# 2. Configure

Create core.
```sh
$ su - solr
$ /opt/solr/bin/solr create_core -c pulsemob_core
```
Delete default settings.
```sh
$ rm -rvf /var/solr/data/pulsemob_core/conf
$ rm -rvf /var/solr/data/pulsemob_core/core.properties
```
Checkout configuration files.
```sh
$ cd /var/solr/data/pulsemob_core
$ git clone git://github.com/Infobase/pulsemob_solr.git
```

# 3. Run
```sh
$ service solr start
```
If solr service is already running, run:
```sh
$ service solr restart
```