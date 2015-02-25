
NewRelic ClearClouds Plugin

Introduction

==============================================

         The New Relic ClearClouds Plugin is published and supported by ClearClouds team. This plugin provides real-time network visibility from wire data that is typically unavailable from APM solutions. Currently the following metrics are recorded:

1.         TCP

1.1          Throughput: Total, Client side, Server side, Inbound and Outbound

1.2          Latency

1.3          Close Status: FIN, TIMEOUT, RESET

1.4          New/Close connections : Requests per second

1.5          Retransmission Rate

1.6          Attack (count per second): SYN, Scan

2.         HTTP 

1.1          Traffic

1.2          Latency

1.3          Status Codes Count

1.4          Error Rate

1.5          Apdex: users' satisfaction rate on URL

 

3.         Alerts

        New Relic allows you to setup at most 5 metrics. For each of the metrics, you can set a caution threshold and a critical threshold signaled by different colors. Alert policies can be configured against those metrics. When an alert is trigged, New relic platform will not only display it on the GUI, but also inform you via an email or other ways based on your configuration. The alert frequency is once per 30 minutes. Below are the metrics:

·         Latency

·         Bytes

·         Error Rate

·         Apdex

·         Attack

 

 

Requirements

==============================================

         The iprobe_plugin need to be installed on the same appliance as the iProbe. 

1.         OS : CentOS 6.2 (64Bits) or later

2.         Disk :    more than 50G

3.         Memory : more than 1G

4.         Software : Python 2.6 or later

cx_freeze-4.3.3 or later

 

Source URL:

==============================================

iProbe:  http://www.clearclouds.com/upload/iProbe-VM-1.0-20150205.zip

plugin :  https://github.com/GitClearClouds/iprobe_plugin.git

 

Running and Installation

===============================

1.         Install virtual machine and P-100

Please refer to ISO install.txt to install 

 

2.         Install plugin

1)       download iprobe_plugin.zip from https://github.com/GitClearClouds/iprobe_plugin.git

2)       enter the download directory

3)       unzip iprobe_plugin.zip

4)       cd iprobe_plugin

5)       chmod -R 777  ./*

6)       sudo python setup.py install

3.         configuration

1)         Run the plugin only once:

                  iprobe_ plugin  -d <datadir>  -n <pluginid>  -k <newrelickey>

                   The parameters are defined as below:

                  <datadir>  :  your data directory

                  <pluginid>  :  your plugin name, generally server name

                  <newrelickey>  :  your license key from your New Relic account.

2)         e.g :

                  iprobe_plugin -d /home/juyun/datafile  -n ClearClouds -k 19e5cb7a2ec9c43a7a90cec3360fb7b5868d08d6

3)         until print message as below:

                  datadir= home/juyun/datafile

                  pluginid= ClearClouds

                  newrelickey=19e5cb7a2ec9c43a7a90cec3360fb7b5868d08d6

 

 

4.         Execute fetcher

         iprobe_plugin  -r

 

 

 
﻿
