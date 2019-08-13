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

## Build Submarine From Source Code

- Run 'mvn install -DskipTests' from Hadoop source top level once.

- Navigate to hadoop-submarine folder and run 'mvn clean package'.

    - By default, hadoop-submarine is built based on hadoop 3.1.2 dependencies.
      Both yarn service runtime and tony runtime are built.
      You can also add a parameter of "-Phadoop-3.2" to specify the dependencies
      to hadoop 3.2.0.

    - Hadoop-submarine can support hadoop 2.9.2 and hadoop 2.7.4 as well.
      You can add "-Phadoop-2.9" to build submarine based on hadoop 2.9.2.
      For example:
      ```
      mvn clean package -Phadoop-2.9
      ```
      As yarn service is based on hadoop 3.*, so only tony runtime is built
      in this case.
