# Elasticsearch with Kibana
[![](https://img.shields.io/badge/Documantation-1.0-brightgreen)]()

<img src="https://user-images.githubusercontent.com/37136204/150631954-fc532e29-834a-41a2-a137-c6da8bb015bc.png" width="700" height="300">


If you did not install ***Elasticsearch*** , let's take you to the previous repository [Elasticsearch Cluster](https://github.com/feyzullahertan/elastic-search-cluster)


## Installation

### Create VM Instances

**CentOS** image is used as Linux on **Google Cloud**

Requirements before creating VM Instance

**>> The instances we will install must be in the same region and zone.**

**>> The instance will be E2 Series and machine type is e2 medium(2 vCPU, 4GB Memory).**

**>> Change boot disk with CentOS. Version is CentOS 7. Size is 20 GB.**

**>> Check is Allow HTTP Trafic and Allow HTTPS Trafic in Firewall settings.**

### Installation Elasticsearch

[Download Elasticsearch](https://www.elastic.co/downloads/elasticsearch)

**Choose Linuxx86_64**

**>> Get link at 'Download Linux86_64'.**

### Installation Kibana


[Download Kibana](https://www.elastic.co/guide/en/kibana/current/rpm.html)

```bash
  wget https://artifacts.elastic.co/downloads/kibana/kibana-7.16.3-x86_64.rpm
  sudo rpm --install kibana-7.16.3-x86_64.rpm
```


### Configuration

```bash
  cd /etc/kibana/
  nano kibana.yml
```

You can see everthing is comment mode. We need to delete "#" and configuration some lines. Btw we need change some lines for configuration:
```bash
  server.port: 5601
  server.host: "0.0.0.0" / You can write external IP.
  elasticsearch.host: ["http://localhost:9200"]
```

### Starting Kibana

```bash
  service start elasticsearch /See "OK"
  service start kibana
```
Finally:

![image](https://user-images.githubusercontent.com/37136204/150700222-a20520fa-3b72-4df4-9826-947a35f86717.png)








