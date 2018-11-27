---
title: Hadoop CVE List
menu:
   main:
      name: "Published CVEs"
      parent: "community"
---
<!---
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->

This page lists security fixes that the Hadoop PMC felt warranted a CVE. If you think something is missing from this list or if you think the set of impacted or fixed versions is incomplete then please [ask on the Security list](mailing_lists.html#Security).

CVEs are presented in most-recent-first order of announcement.

<!-- These should be sorted as most-recent-first. Please copy this template and fill in as needed.

## [CVE-YYYY-XXXX](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-YYYY-XXXX) Short Description

One paragraph summary goes here. Don't need nuts-and-bolts detail, just enough for a reader to guage applicability to their deployment.

- **Versions affected**:
- **Fixed versions**:
- **Impact**:
- **Reporter**:
- **Reported Date**:
- **Issue Announced**:
-->


## [CVE-2018-11766](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-11766) Apache Hadoop privilege escalation vulnerability

In Apache Hadoop 2.7.4 to 2.7.6, the security fix for CVE-2016-6811 is
incomplete. A user who can escalate to yarn user can possibly run arbitrary
commands as root user.

- **Versions affected**: 2.7.4 to 2.7.6
- **Fixed versions**: 2.7.7
- **Impact**: privilege escalation
- **Reporter**: Wilfred Spiegelenburg
- **Reported Date**: 2018/05/04
- **Issue Announced**: 2018/11/27 ([general@hadoop](https://lists.apache.org/thread.html/ff37bbbe09d5f03090e2dd2c3dea95de16ef4249e731f19b8959ce4c@%3Cgeneral.hadoop.apache.org%3E))

## [CVE-2018-8009](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-8009) Apache Hadoop distributed cache archive vulnerability

Vulnerability allows a cluster user to publish a public
archive that can affect other files owned by the user running the YARN
NodeManager daemon. If the impacted files belong to another already
localized, public archive on the node then code can be injected into
the jobs of other cluster users using the public archive.

- **Versions affected**: 3.1.0, 3.0.0-alpha to 3.0.2, 2.9.0 to 2.9.1, 2.8.0 to 2.8.4, 2.0.0-alpha to 2.7.6, 0.23.0 to 0.23.11
- **Fixed versions**: 3.1.1, 3.0.3, 2.9.2, 2.8.5, 2.7.7
- **Impact**: injection attack
- **Credit**: Snyk Security Research Team
- **Reported Date**: 2018/04/19
- **Issue Announced**: 2018/11/22 ([user@hadoop](https://lists.apache.org/thread.html/a1c227745ce30acbcf388c5b0cc8423e8bf495d619cd0fa973f7f38d@%3Cuser.hadoop.apache.org%3E))

## [CVE-2016-6811](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2016-6811) Apache Hadoop Privilege escalation vulnerability

A user who can escalate to yarn user can possibly run arbitrary commands as root user.

- **Versions affected**: 2.2.0 to 2.7.3
- **Fixed versions**: 2.7.4 or newer
- **Impact**: privilege escalation
- **Reporter**: Freddie Rice
- **Reported Date**: 2016/07/06
- **Issue Announced**: 2018/05/01 ([user@hadoop](https://lists.apache.org/thread.html/ff3859a2188c3662240311acddba9cf97992b839792ec0a14d61b4e5@%3Cuser.hadoop.apache.org%3E))

Note: The fix for this vulnerability is incomplete in Apache Hadoop 2.7.4 to 2.7.6 (CVE-2018-11766).

## [CVE-2017-15718](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-15718) Apache Hadoop YARN NodeManager vulnerability

In Apache Hadoop 2.7.3 and 2.7.4, the security fix for CVE-2016-3086 is incomplete.
The YARN NodeManager can leak the password for credential store provider
used by the NodeManager to YARN Applications.

If you use the CredentialProvider feature to encrypt passwords used in
NodeManager configs, it may be possible for any Container launched
by that NodeManager to gain access to the encryption password.
The other passwords themselves are not directly exposed.

- **Versions affected**: 2.7.3, 2.7.4
- **Fixed versions**: 2.7.5
- **Impact**: privilege escalation
- **Reporter**: Vinayakumar B.
- **Reported Date**: 2017/09/18
- **Issue Announced**: 2018/01/24 ([user@hadoop](https://lists.apache.org/thread.html/23a277506bc0d85c1bbe5c0766ffe55e8c3923c8d6f58893b6966957@%3Cuser.hadoop.apache.org%3E))

## [CVE-2017-15713](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-15713) Apache Hadoop MapReduce job history server vulnerability

Vulnerability allows a cluster user to expose private files
owned by the user running the MapReduce job history server process.
The malicious user can construct a configuration file containing XML
directives that reference sensitive files on the MapReduce job history
server host.

- **Versions affected**: 3.0.0-alpha to 3.0.0-beta1, 2.8.0 to 2.8.2, 2.0.0-alpha to 2.7.4, 0.23.0 to 0.23.11
- **Fixed versions**: 3.0.0, 2.9.0, 2.8.3, 2.7.5
- **Impact**: privilege escalation
- **Reporter**: Man Yue Mo of lgtm.com
- **Reported Date**: 2017/06/30
- **Issue Announced**: 2018/01/19 ([user@hadoop](https://lists.apache.org/thread.html/9e5d86d5792d04f8a3b458f735e63fa9bdfe28ff454de257a2e02f18@%3Cuser.hadoop.apache.org%3E))

## [CVE-2017-3166](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2017-3166) Apache Hadoop Privilege escalation vulnerability

In a cluster where the YARN user has been granted access to all HDFS
encryption keys, if a file in an encryption zone with access permissions
that make it world readable is localized via YARN's localization mechanism,
e.g. via the MapReduce distributed cache, that file will be stored
in a world-readable location and shared freely with any application
that requests to localize that file, no matter who the application owner
is or whether that user should be allowed to access files from the
target encryption zone.

- **Versions affected**: 3.0.0-alpha1 - 3.0.0-alpha3 , 2.7.0 to 2.7.3, 2.6.1-2.6.5
- **Fixed versions**: 3.0.0-alpha4, 2.8.0, 2.7.4
- **Impact**: privilege escalation
- **Reporter**: Luke Herbert
- **Reported Date**: 2016/11/18
- **Issue Announced**: 2017/11/08 ([general@hadoop](https://lists.apache.org/thread.html/2e16689b44bdd1976b6368c143a4017fc7159d1f2d02a5d54fe9310f@%3Cgeneral.hadoop.apache.org%3E))

