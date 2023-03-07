---
title: "Experiments in Cloud Gaming: 1/?"
date: "2020-11-25"
draft: true
---

(Initially posted [here][linkedin] on my LinkedIn [profile][profile], but I've
decided to move it to my blog, and tidy it up a bit.)

The idea is to use the cloud to play games (yes, I know - but this is a fun
application of what *could* be used in the workplace professionally - it's the
fundamental skillls in cloud tech that are important here), all controlled with
AWS Lambda functions, and using Infrastructure as Code (IaC) to deploy the
setup.

Depending on the region, these snapshots can actually be *cheaper* than a fully
EBS-backed SSD.

By a fusion technique of associating the snapshot with an AMI and launch
template, we can create snapshots when the cloud gaming VM is powered off, use
AWS EventBridge to call an AWS Lambda function to asynchronously (we do this
because a 512GB EBS volume can take a LONG time to create a initial snapshot,
and Lambda times out after 15 minutes. 

Combine that with RAM and execution time, and you've got a costly Lambda!) take
a snapshot, which EventBridge then calls yet another Lambda function to create
an AMI with the snapshot, and a Launch Template, and we then have a cloud gaming
VM, ready to be deployed.

[linkedin]: https://www.linkedin.com/posts/domrodriguezuk_cloud-aws-ec2-activity-6994059799969550336-ADI1
[profile]: https://www.linkedin.com/in/domrodriguezuk/
