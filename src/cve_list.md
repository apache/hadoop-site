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

## [CVE-2020-9492](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-9492) Apache Hadoop Potential privilege escalation

WebHDFS client might send SPNEGO authorization header to remote URL
without proper verification. A crafty user can trigger services to
send server credentials to a webhdfs path for capturing the service
principal.

Users of the affected versions should apply either of the following mitigations:
* Set different http signature secrets and use dedicated hosts for each privileged impersonation service (such as HiveServer2).
* Upgrade to 3.3.0, 3.2.2, 3.1.4, 2.10.1, or newer with TLS encryption enabled and configure dfs.http.policy to HTTPS\_ONLY.

- **Versions affected**: 3.2.0 to 3.2.1, 3.0.0-alpha1 to 3.1.3, 2.0.0-alpha to 2.10.0
- **Fixed versions**: 3.2.2, 3.1.4, 2.10.1
- **Impact**: privilege escalation
- **Reporter**: Kevin Risden
- **Reported Date**: 2020/03/17
- **Issue Announced**: 2021/01/26 ([general@hadoop](https://lists.apache.org/thread.html/r513758942356ccd0d14538ba18a09903fc72716d74be1cb727ea91ff%40%3Cgeneral.hadoop.apache.org%3E))

## [CVE-2018-11764](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-11764) Apache Hadoop Privilege escalation in web endpoint

Web endpoint authentication check is broken. Authenticated users may
impersonate any user even if no proxy user is configured.

- **Versions affected**: 3.0.0-alpha4, 3.0.0-beta1, 3.0.0
- **Fixed versions**: 3.0.1
- **Impact**: privilege escalation
- **Reporter**: Daryn Sharp
- **Reported Date**: 2018/03/17
- **Issue Announced**: 2020/10/21 ([general@hadoop](https://lists.apache.org/thread.html/r790ad0a049cde713b93589ecfd4dd2766fda0fc6807eedb6cf69f5c1%40%3Cgeneral.hadoop.apache.org%3E))

## [CVE-2018-11765](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-11765) Potential information disclosure in Apache Hadoop Web interfaces

When Kerberos authentication is enabled and SPNEGO through HTTP is not enabled,
any users can access some servlets without authentication.

- **Versions affected**: 3.0.0-alpha2 to 3.0.0, 2.9.0 to 2.9.2, 2.8.0 to 2.8.5
- **Fixed versions**: 3.0.1, 2.10.0
- **Impact**: information disclosure
- **Reporter**: Larry McCay (Discovered by Owen O'Malley)
- **Reported Date**: 2018/03/11
- **Issue Announced**: 2020/09/28 ([general@hadoop](https://lists.apache.org/thread.html/r2c7f899911a04164ed1707083fcd4135f8427e04778c87d83509b0da%40%3Cgeneral.hadoop.apache.org%3E))

## [CVE-2018-11768](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-11768) Apache Hadoop HDFS FSImage Corruption

There is a mismatch in the size of the fields used to store user/group
information between memory and disk representation. This causes the user/group
information to be corrupted across storing in fsimage and reading back from
fsimage.

This vulnerability fix contains a fsimage layout change, so once the image is
saved in the new layout format you cannot go back to a version that doesn’t
support the newer layout. This means that once 2.7.x users upgraded to the
fixed version, they cannot downgrade to 2.7.x because there is no fixed version
in 2.7.x. We suggest downgrade to 2.8.5 or upper version that contains the
vulnerability fix.

- **Versions affected**: 3.1.0 to 3.1.1, 3.0.0-alpha1 to 3.0.3, 2.9.0 to 2.9.1, 2.0.0-alpha to 2.8.4
- **Fixed versions**: 3.1.2, 2.9.2, 2.8.5
- **Impact**: information disclosure
- **Reporter**: Ekanth Sethuramalingam
- **Reported Date**: 2018/06/05
- **Issue Announced**: 2019/10/03 ([general@hadoop](https://lists.apache.org/thread.html/2067a797b330530a6932f4b08f703b3173253d0a2b7c8c524e54adaf@%3Cgeneral.hadoop.apache.org%3E))

## [CVE-2018-8029](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-8029) Apache Hadoop Privilege escalation vulnerability

A user who can escalate to yarn user can possibly run arbitrary
commands as root user.

- **Versions affected**: 3.0.0-alpha1 to 3.1.0, 2.9.0 to 2.9.1, 2.2.0 to 2.8.4
- **Fixed versions**: 3.1.1, 2.9.2, 2.8.5
- **Impact**: privilege escalation
- **Reporter**: Miklos Szegedi
- **Reported Date**: 2018/05/08
- **Issue Announced**: 2019/05/30 ([general@hadoop](https://lists.apache.org/thread.html/17084c09e6dedf60efe08028b429c92ffd28aacc28454e4fa924578a@%3Cgeneral.hadoop.apache.org%3E))

## [CVE-2018-11767](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-11767) Apache Hadoop KMS ACL regression

After the security fix for CVE-2017-15713, KMS has an access control regression,
blocking users or granting access to users incorrectly, if the system
uses non-default groups mapping mechanisms such as LdapGroupsMapping,
CompositeGroupsMapping, or NullGroupsMapping.

- **Versions affected**: 2.9.0 to 2.9.1, 2.8.3 to 2.8.4, 2.7.5 to 2.7.6
- **Fixed versions**: 2.9.2, 2.8.5, 2.7.7
- **Impact**: privilege escalation
- **Reporter**: Wei-Chiu Chuang
- **Reported Date**: 2018/05/09
- **Issue Announced**: 2019/03/11 ([general@hadoop](https://lists.apache.org/thread.html/5fb771f66946dd5c99a8a5713347c24873846f555d716f9ac17bccca@%3Cgeneral.hadoop.apache.org%3E))

## [CVE-2018-1296](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2018-1296) Apache Hadoop HDFS Permissive listXAttr Authorization

HDFS exposes extended attribute key/value pairs during listXAttrs,
verifying only path-level search access to the directory rather than
path-level read permission to the referent. This affects features that
store sensitive data in extended attributes, such as HDFS encryption 
secrets.

- **Versions affected**: 3.0.0-alpha1 to 3.0.0, 2.9.0, 2.8.0 to 2.8.3, 2.5.0 to 2.7.5
- **Fixed versions**: 3.0.1, 2.9.1, 2.8.4, 2.7.6
- **Impact**: information disclosure
- **Reporter**: Rushabh Shah
- **Reported Date**: 2018/02/09
- **Issue Announced**: 2019/01/24 ([general@hadoop](https://lists.apache.org/thread.html/752d5fe697ca6be6f472eabb1bcae7961a47d416e4013ac803a2ab2c@%3Cgeneral.hadoop.apache.org%3E))

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

# Thirdparty vulnerabilities
The following section describes thirdparty vulnerabilities that may be of interest to Hadoop users. Please contact the respective project owners for details.

## [CVE-2021-44228](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-44228) Log4JShell Vulnerability

It is understood that the log4jshell vulnerability CVE-2021-44228 impacts log4j2. Hadoop, as of 3.3.x depends on log4j 1.x, which is **NOT** susceptible to the attack. Once we migrate over to log4j2, we will adopt a version that is not susceptible to the attack, too. Therefore, no ASF version of Hadoop has ever been vulnerable. Third party products and applications based on Hadoop *may* be vulnerable, please consult the vendor or the project owner.

- **Versions affected**: N/A

## [CVE-2021-4104](https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2021-4104) Log4JShell Vulnerability

JMSAppender in Log4j 1.2, used by all versions of Apache Hadoop, is vulnerable to the Log4JShell attack in a similar fashion to CVE-2021-4428. However, the JMSAppender is not the default configuration shipped in Hadoop. When JMSAppender is not enabled, Hadoop is not vulnerable to the attack.

To mitigate the risk, you can remove JMSAppender from the log4j-1.2.17.jar artifact yourself following the instructions in this [link](http://slf4j.org/log4shell.html).

- **Versions affected**: N/A
