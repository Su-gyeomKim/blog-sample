# blog sample

[![Build Status](https://travis-ci.org/efkbook/blog-sample.svg?branch=master)](https://travis-ci.org/efkbook/blog-sample)

A kind of blog for presentating EFK stack features.

* Write, view and search blog posts.
* Sing up, Login. Session is based on cookie.
* Collect page views and search logs into Elasticsearch via fluentd in Real-Time.
* Of course, you can view and analyze user actions in Elasticsearch and Kibana.

This repository includes following.

* [fluent/fluentd](https://github.com/fluent/fluentd) v0.12 latest
* [uken/fluent-plugin-elasticsearch](https://github.com/uken/fluent-plugin-elasticsearch)
* Elastic v5 (Elasticsearch and Kibana)
* Simple blog application based on [suzuken/wiki](https://github.com/suzuken/wiki) written in Go.

## Prerequisite

* Docker

For local development,

* Go (>= 1.8)
* sqlite3

## Using Docker: make run

If you using docker, it's easy to work with Elastic stack and fluentd!
    # set GOPATH variable
    # export GOPATH=/root/go
    # make directory
    mkdir /root/go
    mkdir -p /root/go/src/github.com/efkbook
    # change directory
    cd /root/go/src/github.com/efkbook
    # git clone
    git clone https://github.com/efkbook/blog-sample
    
    /* ERROR OCCURRED
        # database migration
        make migrate/up
        # build binary
        make app/build
        # running docker containers by `docker-compose up -d`
        make run
    */
    
At the first time, `docker-compose` start creating containers. After starting containers, it's time to access Elasticsearch.

    $ curl http://localhost:9200
    {
      "name" : "o2r0AqN",
      "cluster_name" : "docker-cluster",
      "cluster_uuid" : "KoAk04RXRbSx3wgLiB_LtA",
      "version" : {
        "number" : "5.4.3",
        "build_hash" : "eed30a8",
        "build_date" : "2017-06-22T00:34:03.743Z",
        "build_snapshot" : false,
        "lucene_version" : "6.5.1"
      },
      "tagline" : "You Know, for Search"
    }

It works! And your Kibana console is also available on `http://localhost:5601`. If Elasticsearch is accecible, blog application can start up.


mkdir /root/go mkdir -p /root/go/src/github.com/efkbook
cd /root/go/src/github.com/efkbook
yum install git wget golang* docker* telnet --skip-broken
git clone https://github.com/efkbook/blog-sample
service docker start
ll
cd /root/go/src/github.com/efkbook
ll
cd blog-sample/
ll
make migrate/up
export GOPATH=/root/go
go
go env
make migrate/up
bg %1
 make app/build
bg %2
jobs
jobs
ll
jobs
docker-compose up -d
WARNING: Image for service elasticsearch was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.

Reading package lists...
Building dependency tree...
Reading state information...
The following extra packages will be installed:
  binutils bzip2 cpp cpp-4.9 dpkg-dev g++ g++-4.9 gcc gcc-4.9 libasan1
  libatomic1 libc-dev-bin libc6-dev libcilkrts5 libcloog-isl4 libcurl3
  libcurl3-gnutls libdpkg-perl libgcc-4.9-dev libgdbm3 libgomp1
  libgssapi-krb5-2 libidn11 libisl10 libitm1 libk5crypto3 libkeyutils1
  libkrb5-3 libkrb5support0 libldap-2.4-2 liblsan0 libmpc3 libmpfr4
  libquadmath0 librtmp1 libsasl2-2 libsasl2-modules-db libssh2-1 libssl1.0.0
  libstdc++-4.9-dev libtimedate-perl libtsan0 libubsan0 linux-libc-dev make
  openssl patch perl perl-modules xz-utils
Suggested packages:
  binutils-doc bzip2-doc cpp-doc gcc-4.9-locales debian-keyring g++-multilib
  g++-4.9-multilib gcc-4.9-doc libstdc++6-4.9-dbg gcc-multilib manpages-dev
  autoconf automake libtool flex bison gdb gcc-doc gcc-4.9-multilib
  libgcc1-dbg libgomp1-dbg libitm1-dbg libatomic1-dbg libasan1-dbg
  liblsan0-dbg libtsan0-dbg libubsan0-dbg libcilkrts5-dbg libquadmath0-dbg
  glibc-doc libcurl4-doc libcurl3-dbg libgnutls28-dev libidn11-dev libkrb5-dev
  libldap2-dev librtmp-dev libssh2-1-dev pkg-config zlib1g-dev krb5-doc
  krb5-user libstdc++-4.9-doc make-doc ed diffutils-doc perl-doc
  libterm-readline-gnu-perl libterm-readline-perl-perl libb-lint-perl
  libcpanplus-dist-build-perl libcpanplus-perl libfile-checktree-perl
  liblog-message-simple-perl liblog-message-perl libobject-accessor-perl
Recommended packages:
  fakeroot libalgorithm-merge-perl libfile-fcntllock-perl krb5-locales
  libsasl2-modules netbase rename libarchive-extract-perl
  libmodule-pluggable-perl libpod-latex-perl libterm-ui-perl
  libtext-soundex-perl libcgi-pm-perl libmodule-build-perl
  libpackage-constants-perl
The following NEW packages will be installed:
  binutils build-essential bzip2 ca-certificates cpp cpp-4.9 curl dpkg-dev g++
  g++-4.9 gcc gcc-4.9 libasan1 libatomic1 libc-dev-bin libc6-dev libcilkrts5
  libcloog-isl4 libcurl3 libcurl3-gnutls libcurl4-gnutls-dev libdpkg-perl
  libgcc-4.9-dev libgdbm3 libgomp1 libgssapi-krb5-2 libidn11 libisl10 libitm1
  libk5crypto3 libkeyutils1 libkrb5-3 libkrb5support0 libldap-2.4-2 liblsan0
  libmpc3 libmpfr4 libquadmath0 librtmp1 libsasl2-2 libsasl2-modules-db
  libssh2-1 libssl1.0.0 libstdc++-4.9-dev libtimedate-perl libtsan0 libubsan0
  linux-libc-dev make openssl patch perl perl-modules sudo xz-utils
0 upgraded, 55 newly installed, 0 to remove and 5 not upgraded.
Need to get 53.9 MB of archives.
After this operation, 183 MB of additional disk space will be used.

debconf: delaying package configuration, since apt-utils is not installed

Successfully built cabe78878d21
WARNING: Image for service fluentd was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.

Successfully built 4774f7ebacba
WARNING: Image for service go was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.


## For contributor

To start a blog application locally, you just `go run`

    go run main.go

To add some external packages, use `godep`. If you want to use Elasticsearch and/or Fluentd on docker container, you can specify each host via flag. When blog app running on container, Elasticsearch and Fluentd are accessed by using docker links.

## Acknowledgement

UI Template is based on [BlackrockDigital/startbootstrap-blog-post](https://github.com/BlackrockDigital/startbootstrap-blog-post).

## LICENSE

MIT

## Author

Kenta Suzuki (a.k.a. suzuken)
