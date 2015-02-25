
Clearclouds iProbe Plugin for Newrelic

1           Introduction:

The iProbe plugin published and supported by Clearclouds team

The iProbe plugin enables integrated monitoring of network performance and traffic abnormally inside New Relic.

2           The iProbe plugin monitor items include:

● TCP Throughput: Inbound and Outbound

● TCP latency: Client side and Server side

● TCP establishing status: Syn and Scan

● TCP Close Status: by FIN, TIMEOUT, or RESET

● TCP Connections: Requests per second, newly created and past closed

● TCP Retransmission Rate

● HTTP Latency: Server response time per transaction

● HTTP Status Code: 3XX, 4XX, and 5XX and their Error Rates

● HTTP Apdex: user satisfied degree

● Alert includes at most 5 alerting items from the above

 

3           Requirement

         OS : CentOS 6.2 (64Bits) or later

         Disk :    more than 50G

         Memory : more than 1G

         Software : Python 2.6 or later

                             cx_freeze-4.3.3 or later

 

4           Source URL : 

4.1          iProbe:  http://www.clearclouds.com/upload/iProbe-VM-1.0-20150205.zip

4.2          plugin :  https://github.com/GitClearClouds/iprobe_newrelic_plugin.git

 

5           Install virtual machine and P-100

Please refer to ISO install.txt to install 

         

6           Install source plugin(if python and cx_freeze installed in your server,or go to next step)

6.1          after download the file iprobe_newrelic_plugin.zip from https://github.com/GitClearClouds/iprobe_newrelic_plugin.git

6.2          enter download directory

6.3          unzip  iprobe_newrelic_plugin.zip

6.4          cd  iprobe_newrelic_plugin

6.5          chmod -R 777  ./*

6.6          sudo python setup.py install

 

7           Install  binary plugin(if previous step failed)

7.1          after download the file iprobe_newrelic_plugin.zip from https://github.com/GitClearClouds/iprobe_newrelic_plugin.git

7.2          enter download directory

7.3          unzip  iprobe_newrelic_plugin.zip

7.4          cd  iprobe_newrelic_plugin/dist

7.5          tar -zxvf fetcher-0.1.linux-x86_64.tar.gz

7.6          cd fetcher-0.1.linux-x86_64

7.7          chmod -R 777  ./*

7.8          cp -R ./*  /

 

 

8           configuration

8.1          run the iprobe_newrelic_fetcher plugin only once:

                  iprobe_newrelic_fetcher  -d datdir  -n pluginid  -k newrelickey

                   the parameter is as follows :

                  datadir  :  your data directory

                  pluginid  :  your plugin name, generally server name

                  newrelickey  :  your license key from your New Relic account.

8.2          e.g :

                  iprobe_newrelic_fetcher -d /home/juyun/datafile  -n ClearClouds -k 19e5cb7a2ec9c43a7a90cec3360fb7b5868d08d6

         until print message as below:

                  datadir= home/juyun/datafile

                  pluginid= ClearClouds

                  newrelickey=19e5cb7a2ec9c43a7a90cec3360fb7b5868d08d6

 

9           Execute fetcher

         iprobe_newrelic_fetcher  -r

