---
title: Questions and Answers
---

### How can I contribute

The contribution process is the same as for any other [Hadoop subproject][1]. The Ozone Contribution Guidelines is available from the [wiki][2].

### Does it mean a new Hadoop server component?

Both Ozone and HDDS requires one additional master component - Ozone Manager and Storage Container Manger, respectively. 
The worker parts of Ozone/HDDS can be started as a HDFS Datanode plugin or standalone.

### How can I try it out?
There is a [katacoda example][3] which can be used to try out Ozone without download.

You can also [download](/downloads/) it and [try it out](/docs/latest/runningviadocker.html)

[1]: https://wiki.apache.org/hadoop/HowToContribute
[2]: https://cwiki.apache.org/confluence/display/HADOOP/Ozone+Contributor+Guide
[3]: https://www.katacoda.com/elek/scenarios/ozone101
