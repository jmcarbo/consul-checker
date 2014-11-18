sudo weave run 192.168.1.100/24 -d --net none --name webtestpod01 -h webtestpod01 jmcarbo/webtestpod
sudo docker run -d --net container:webtestpod01 --name webtestpod01-checker jmcarbo/consul-checker
sudo docker run -d --net container:webtestpod01 --name webtestpod01-checker jmcarbo/consul-checker /usr/local/bin/start  webtestpod  192.168.1.3 'curl -sIL http://localhost:8080' 8080


start <service name> <consul join ip> <optional command> <service port>
```
/usr/local/bin/start  webtestpod  192.168.1.3 'curl -sIL http://localhost:8080' 8080
```
