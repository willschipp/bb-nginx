## The script

### Prerequisites

- Docker

### Installation

1. install weave

sudo curl -L git.io/weave -o /usr/local/bin/weave
sudo chmod +x /usr/local/bin/weave
weave launch

2. install elasticsearch

weave run --name elasticsearch -d elasticsearch

3. install kibana

weave run --name kibana -d kibana

4. build app

docker build . -t bb-app

5. run app

weave run --name app -d bb-app

6. build nginx

docker build . -t proxy

7. run nginx

weave run --name gateway -p 80:80 -d proxy
