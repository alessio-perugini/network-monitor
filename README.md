# net-monitor

A GoLang script that send network usage traffic to influx stack

## Requirements

`docker` and `influxDB 2.0`

##### Running on Docker

> ```$ docker run --name influxdb -p 9999:9999 quay.io/influxdb/influxdb:2.0.0-beta```

To use `influx` cli, console into the `influxdb` Docker container:

```$ docker exec -it influxdb /bin/bash```

For more information visit: <https://v2.docs.influxdata.com/v2.0/get-started/>

##### Running on Mac OS X

> ```
> $ https://dl.influxdata.com/influxdb/releases/influxdb_2.0.0-beta.8_darwin_amd64.tar.gz
> $ tar zxvf influxdb_2.0.0-beta.8_darwin_amd64.tar.gz
> ```

##### Running on Linux Binaries (64-bit)

> ```
> $ wget https://dl.influxdata.com/influxdb/releases/influxdb_2.0.0-beta.8_linux_amd64.tar.gz
> $ tar xvfz influxdb_2.0.0-beta.8_linux_amd64.tar.gz
> ```

##### Running on Linux Binaries (ARM)

> ```
> $ wget https://dl.influxdata.com/influxdb/releases/influxdb_2.0.0-beta.8_linux_arm64.tar.gz
> $ tar xvfz influxdb_2.0.0-beta.8_linux_arm64.tar.gz
> ```

## Binaries

You can find `net-monitor` binaries on the release tag

## Compile

```
$ go build net-monitor.go
```
## How to use

```net-monitor -community [community] -host [host] -port [snmp_port] -interval [interval]```

Default values:
 - community: `public`
 - host: `127.0.0.1`
 - port: `161`
 - interval: `5s`

## Options

Type `$ net-monitor -help`

```
Usage: net-monitor [options]
  -community string
        community string for snmp (default "public")
  -host string
        hostname or ip address (default "localhost")
  -interval string
        interval in seconds before send another snmp request (default "5s")
  -port uint
        port number (default 161)
  -version
        output version
```

## Dependencies

[gosnmp](https://github.com/soniah/gosnmp) used for snmp requests
```
go get github.com/soniah/gosnmp
```# network-monitor
