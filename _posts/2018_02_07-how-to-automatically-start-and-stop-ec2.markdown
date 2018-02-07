---
layout: post
title:  "How to automatically start and stop an EC2 instance"
date:   2018-02-07 07:23:40 +0100
categories: aws, ec2, infrastructure
---
Sometimes you have a task on a machine that you just need to start sporadically, e.g. once in a day. It's a waste of money to keep an EC2 instance running all the day.

With [EC2 Scheduler](https://aws.amazon.com/de/answers/infrastructure-management/ec2-scheduler/) AWS offers a tool to schedule starting, and stopping of an instance.

This is a great starting point for its configuration: [EC2 Scheduler Documentation](https://docs.aws.amazon.com/solutions/latest/ec2-scheduler/deployment.html)
