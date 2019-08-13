---
title: "Apache Hadoop Submarine Documentation"
layout: default
type: custompage
---
<!--
   Licensed to the Apache Software Foundation (ASF) under one or more
   contributor license agreements.  See the NOTICE file distributed with
   this work for additional information regarding copyright ownership.
   The ASF licenses this file to You under the Apache License, Version 2.0
   (the "License"); you may not use this file except in compliance with
   the License.  You may obtain a copy of the License at
   https://www.apache.org/licenses/LICENSE-2.0
   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.
-->

# How to Install Dependencies

Submarine project may uses YARN Service (When Submarine YARN service runtime is being used, see [QuickStart](docs/0.2.0/QuickStart)), Docker container, and GPU (when GPU hardware available and properly configured).

That means as an admin, you may have to properly setup YARN Service related dependencies, including:
- YARN Registry DNS

Docker related dependencies, including:
- Docker binary with expected versions.
- Docker network which allows Docker container can talk to each other across different nodes.

And when GPU plan to be used:
- GPU Driver.
- Nvidia-docker.

For your convenience, we provided installation documents to help you to setup your environment. You can always choose to have them installed in your own way.

Use Submarine installer to install dependencies: [EN](https://github.com/hadoopsubmarine/hadoop-submarine-ecosystem/tree/master/submarine-installer) [CN](https://github.com/hadoopsubmarine/submarine-installer/blob/master/README-CN.md)

Alternatively, you can follow manual install dependencies: [EN](docs/0.2.0/InstallationGuide) [CN](docs/0.2.0//InstallationGuideChineseVersion)

Once you have installed dependencies, please follow following guide to [TestAndTroubleshooting](docs/0.2.0/TestAndTroubleshooting).
