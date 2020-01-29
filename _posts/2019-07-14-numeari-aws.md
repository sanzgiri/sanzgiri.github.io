---
title: Numerai Compute on AWS
date: 2019-07-14 00:00:00 Z
permalink: "/numerai-aws"
layout: post
excerpt: Numerai AWS
---
### Train Numerai models and submit predictions from AWS

* Use numerai-cli from https://github.com/numerai/numerai-cli

* Code is installed on mac laptop in ~/example-numerai

```angular2
Install python 3.x form www.python.org
curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py
python get-pip.py
pip3 install -U numerai-cli

# latest aws configs
numerai setup -c 2048 -m 16384

# update example code
numerai docker copy-example

# build container, deploy on aws
numerai docker deploy

# Run locally and submit predictions
numerai docker run

# Test remote webhook
numerai compute test-webhook
numerai compute status
numerai compute logs
```

* AWS job is scheduled to run daily at 15:35 UTC: <https://console.aws.amazon.com/ecs/home?region=us-east-1#/clusters/numerai-submission-ecs-cluster/scheduledTasks/numerai-daily>
 
* Check AWS logs here: <https://console.aws.amazon.com/cloudwatch/home?region=us-east-1#logStream:group=/fargate/service/numerai-submission;streamFilter=typeLogStreamPrefix>

* Link to forums: <https://community.numer.ai/channel/compute?utm_source=sendgrid.com&utm_medium=email&utm_campaign=website>

