---
title: "Apache Hadoop Ozone Releases"
layout: downloads
type: custompage
---
<!---
  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

   https://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License. See accompanying LICENSE file.
-->

## To verify Hadoop Ozone releases using GPG:

1.  Download the release hadoop-ozone-X.Y.Z-src.tar.gz from a [mirror
    site](https://www.apache.org/dyn/closer.cgi/hadoop/ozone).
2.  Download the signature file hadoop-ozone-X.Y.Z-src.tar.gz.asc from
    [Apache](https://dist.apache.org/repos/dist/release/hadoop/ozone/).
3.  Download the [Hadoop
    KEYS](https://dist.apache.org/repos/dist/release/hadoop/common/KEYS)
    file.
4.  gpg --import KEYS
5.  gpg --verify hadoop-X.Y.Z-src.tar.gz.asc

## To perform a quick check using SHA-256:

1.  Download the release hadoop-ozone-X.Y.Z-src.tar.gz from a [mirror
    site](https://www.apache.org/dyn/closer.cgi/hadoop/ozone).
2.  Download the checksum hadoop-ozone-X.Y.Z-src.tar.gz.mds from
    [Apache](https://dist.apache.org/repos/dist/release/hadoop/ozone/).
3.  shasum -a 256 hadoop-ozone-X.Y.Z-src.tar.gz

All previous releases of Hadoop Ozone are available from the [Apache release
archive](https://archive.apache.org/dist/hadoop/ozone/) site.

## License

_The software licensed under [Apache License 2.0](https://www.apache.org/licenses/LICENSE-2.0)_
