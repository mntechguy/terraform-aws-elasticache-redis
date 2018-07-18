<!-- This file was automatically generated by the `build-harness`. Make all changes to `README.yaml` and run `make readme` to rebuild this file. -->

[![Cloud Posse](https://cloudposse.com/logo-300x69.svg)](https://cloudposse.com)

# terraform-aws-elasticache-redis [![Build Status](https://travis-ci.org/cloudposse/terraform-aws-elasticache-redis.svg?branch=master)](https://travis-ci.org/cloudposse/terraform-aws-elasticache-redis) [![Latest Release](https://img.shields.io/github/release/cloudposse/terraform-aws-elasticache-redis.svg)](https://github.com/cloudposse/terraform-aws-elastic-beanstalk-environment/releases/latest) [![Slack Community](https://slack.cloudposse.com/badge.svg)](https://slack.cloudposse.com)


Terraform module to provision an [`ElastiCache`](https://aws.amazon.com/elasticache/) Redis Cluster


---

This project is part of our comprehensive ["SweetOps"](https://docs.cloudposse.com) approach towards DevOps. 


It's 100% Open Source and licensed under the [APACHE2](LICENSE).





## Usage

Include this repository as a module in your existing terraform code:

```hcl
module "example_redis" {
  source          = "git::https://github.com/cloudposse/terraform-aws-elasticache-redis.git?ref=master"
  namespace       = "general"
  name            = "redis"
  stage           = "prod"
  zone_id         = "${var.route53_zone_id}"
  security_groups = ["${var.security_group_id}"]

  vpc_id                       = "${var.vpc_id}"
  subnets                      = "${var.private_subnets}"
  maintenance_window           = "wed:03:00-wed:04:00"
  cluster_size                 = "2"
  instance_type                = "cache.t2.micro"
  engine_version               = "3.2.4"
  alarm_cpu_threshold_percent  = "${var.cache_alarm_cpu_threshold_percent}"
  alarm_memory_threshold_bytes = "${var.cache_alarm_memory_threshold_bytes}"
  apply_immediately            = "true"
  availability_zones           = "${var.availability_zones}"

  automatic_failover = "false"
}
```






## Makefile Targets
```
Available targets:

  help                                This help screen
  help/all                            Display help for all targets
  lint                                Lint terraform code

```

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|:----:|:-----:|:-----:|
| at_rest_encryption_enabled | Enable encryption at rest | string | `false` | no |
| alarm_actions | Alarm action list | list | `<list>` | no |
| alarm_cpu_threshold_percent | CPU threshold alarm level | string | `75` | no |
| alarm_memory_threshold_bytes | Ram threshold alarm level | string | `10000000` | no |
| apply_immediately | Apply changes immediately | string | `true` | no |
| attributes | Additional attributes (_e.g._ "1") | list | `<list>` | no |
| automatic_failover | Automatic failover (Not available for T1/T2 instances) | string | `false` | no |
| availability_zones | Availability zone ids | list | `Availability zone ids` | no |
| cluster_size | Count of nodes in cluster | string | `1` | no |
| delimiter | Delimiter between `name`, `namespace`, `stage` and `attributes` | string | `-` | no |
| enabled | Set to false to prevent the module from creating any resources | string | `true` | no |
| engine_version | Redis engine version | string | `4.0.10` | no |
| family | Redis family | string | `redis4.0` | no |
| instance_type | Elastic cache instance type | string | `cache.t2.micro` | no |
| maintenance_window | Maintenance window | string | `wed:03:00-wed:04:00` | no |
| name | Name | string | `redis` | no |
| namespace | Namespace | string | `global` | no |
| notification_topic_arn | Notification topic arn | string | `10000000` | no |
| port | Redis port | string | `6379` | no |
| security_groups | AWS security group ids | list | `<list>` | no |
| stage | Stage | string | `default` | no |
| subnets | AWS subnet ids | list | `<list>` | no |
| tags | Additional tags (_e.g._ map("BusinessUnit","ABC") | map | `<map>` | no |
| transit_encryption_enabled | Enable TLS | string | `false` | no |
| vpc_id | AWS VPC id | string | `REQUIRED` | no |
| zone_id | Route53 DNS Zone id | string | `false` | no |

## Outputs

| Name | Description |
|------|-------------|
| host | Redis host |
| id | Redis cluster id |
| port | Redis port |
| security_group_id | Security group id |




## Help

**Got a question?**

File a GitHub [issue](https://github.com/cloudposse/terraform-aws-elasticache-redis/issues), send us an [email][email] or join our [Slack Community][slack].

## Commerical Support

Work directly with our team of DevOps experts via email, slack, and video conferencing. 

We provide *commercial support* for all of our [Open Source][github] projects. As a *Dedicated Support* customer, you have access to our team of subject matter experts at a fraction of the cost of a fulltime engineer. 

[![E-Mail](https://img.shields.io/badge/email-hello@cloudposse.com-blue.svg)](mailto:hello@cloudposse.com)

- **Questions.** We'll use a Shared Slack channel between your team and ours.
- **Troubleshooting.** We'll help you triage why things aren't working.
- **Code Reviews.** We'll review your Pull Requests and provide constructive feedback.
- **Bug Fixes.** We'll rapidly work to fix any bugs in our projects.
- **Build New Terraform Modules.** We'll develop original modules to provision infrastructure.
- **Cloud Architecture.** We'll assist with your cloud strategy and design.
- **Implementation.** We'll provide hands on support to implement our reference architectures. 


## Community Forum

Get access to our [Open Source Community Forum][slack] on Slack. It's **FREE** to join for everyone! Our "SweetOps" community is where you get to talk with others who share a similar vision for how to rollout and manage infrastructure. This is the best place to talk shop, ask questions, solicit feedback, and work together as a community to build *sweet* infrastructure.

## Contributing

### Bug Reports & Feature Requests

Please use the [issue tracker](https://github.com/cloudposse/terraform-aws-elasticache-redis/issues) to report any bugs or file feature requests.

### Developing

If you are interested in being a contributor and want to get involved in developing this project or [help out](https://github.com/orgs/cloudposse/projects/3) with our other projects, we would love to hear from you! Shoot us an [email](mailto:hello@cloudposse.com).

In general, PRs are welcome. We follow the typical "fork-and-pull" Git workflow.

 1. **Fork** the repo on GitHub
 2. **Clone** the project to your own machine
 3. **Commit** changes to your own branch
 4. **Push** your work back up to your fork
 5. Submit a **Pull Request** so that we can review your changes

**NOTE:** Be sure to merge the latest changes from "upstream" before making a pull request!


## Copyright

Copyright © 2017-2018 [Cloud Posse, LLC](https://cloudposse.com)



## License 

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 

See [LICENSE](LICENSE) for full details.

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

      https://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.


## Trademarks

All other trademarks referenced herein are the property of their respective owners.

## About

This project is maintained and funded by [Cloud Posse, LLC][website]. Like it? Please let us know at <hello@cloudposse.com>

[![Cloud Posse](https://cloudposse.com/logo-300x69.svg)](https://cloudposse.com)

We're a [DevOps Professional Services][hire] company based in Los Angeles, CA. We love [Open Source Software](https://github.com/cloudposse/)!

We offer paid support on all of our projects.  

Check out [our other projects][github], [apply for a job][jobs], or [hire us][hire] to help with your cloud strategy and implementation.

  [docs]: https://docs.cloudposse.com/
  [website]: https://cloudposse.com/
  [github]: https://github.com/cloudposse/
  [jobs]: https://cloudposse.com/jobs/
  [hire]: https://cloudposse.com/contact/
  [slack]: https://slack.cloudposse.com/
  [linkedin]: https://www.linkedin.com/company/cloudposse
  [twitter]: https://twitter.com/cloudposse/
  [email]: mailto:hello@cloudposse.com


### Contributors

|  [![Erik Osterman][osterman_avatar]][osterman_homepage]<br/>[Erik Osterman][osterman_homepage] | [![Igor Rodionov][goruha_avatar]][goruha_homepage]<br/>[Igor Rodionov][goruha_homepage] | [![Andriy Knysh][aknysh_avatar]][aknysh_homepage]<br/>[Andriy Knysh][aknysh_homepage] | [![Daren Desjardins][darend_avatar]][darend_homepage]<br/>[Daren Desjardins][darend_homepage] | [![Max Moon][MoonMoon1919_avatar]][MoonMoon1919_homepage]<br/>[Max Moon][MoonMoon1919_homepage] | [![Christopher Riley][christopherriley_avatar]][christopherriley_homepage]<br/>[Christopher Riley][christopherriley_homepage] |

|---|---|---|---|---|---|

  [osterman_homepage]: https://github.com/osterman
  [osterman_avatar]: https://github.com/osterman.png?size=150
  [goruha_homepage]: https://github.com/goruha
  [goruha_avatar]: https://github.com/goruha.png?size=150
  [aknysh_homepage]: https://github.com/aknysh
  [aknysh_avatar]: https://github.com/aknysh.png?size=150
  [darend_homepage]: https://github.com/darend
  [darend_avatar]: https://github.com/darend.png?size=150
  [MoonMoon1919_homepage]: https://github.com/MoonMoon1919
  [MoonMoon1919_avatar]: https://github.com/MoonMoon1919.png?size=150
  [christopherriley_homepage]: https://github.com/christopherriley
  [christopherriley_avatar]: https://github.com/christopherriley.png?size=150
