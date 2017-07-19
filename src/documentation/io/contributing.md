---
layout: default
title: "Contributing I/O Transforms"
permalink: /documentation/io/contributing/
---

[Pipeline I/O Table of Contents]({{site.baseurl}}/documentation/io/io-toc/)

# Contributing I/O Transforms

* If you are planning to contribute your I/O transform to the Apache Beam community, you'll be going through the normal Beam contribution life cycle - see the [Apache Beam Contribution Guide]({{ site.baseurl }}/contribute/contribution-guide/) for more details.
    * Make sure to open a JIRA issue for your I/O transform
    * Make sure to add your I/O to the list of in-progress I/Os on the [Built-in I/O Transforms]({{site.baseurl }}/documentation/io/built-in/) page.
* Talk to the community! We are excited to help - the easiest way to get engaged is to send mail to the Beam dev mailing list.
* Make sure you've implemented the appropriate tests as discussed in the [Testing I/O Transforms]({{site.baseurl }}/documentation/io/testing/) section.

## Adding a new test to the Jenkins suites

After you added your I/O transform and its integration tests to the repository, you are ready to add the integration tests to the Jenkins test suites so that they run the Beam CIs.


Steps to follow to add a new jenkins job:

1.  Add a new groovy file defining the job. The file should be named .test-infra/jenkins/job_beam_PerformanceTests_[IO name].groovy
1.  The jenkins job's name as defined in the file should be similarly named
1.  change the time in the common_job_properties.setPostCommit so that it's not run at exactly the same time as the job you're copying from. See http://www.nncron.ru/help/EN/working/cron-format.htm for info about cron time formatting.
1.  TODO more info on how to update the job contents (@jasonkuster knows this best - base it off of JDBC jenkins job)