![Vector](vector.png)

Vector is an open source on-instance performance monitoring framework which exposes hand picked high resolution system and application metrics to every engineer’s browser. Having the right metrics available on-demand and at a high resolution is key to understand how a system behaves and correctly troubleshoot performance issues.

## Disclaimer

This is the first release of Vector. As such, expect to find bugs and issues. We count on your support to find and report them!

Vector is under constant development and new versions should be released often.

## Getting Started

In order to get started, you should first install Performance Co-Pilot (PCP) on each instance you plan to monitor. PCP will collect the metrics and make them available for Vector.

Optional monitoring agents can also be installed in order to collect specific metrics that are not supported by PCP's system agent.

Once PCP is installed, you should be able to run Vector and connect to the target instance.

### Performance Co-Pilot (PCP)

Vector depends on Performance Co-Pilot (PCP) to collect metrics on each instance you plan to monitor.

Since Vector depends on version 3.10 or higher, the packages currently available on most Linux distro repositories would not suffice. Until newer versions are available in the repositories, you should be able to install PCP from binary packages made available by the PCP development team on:

```
ftp.pcp.io
````

Or building it from source. To do so, get the current version of the source code:

```
$ git clone git://git.pcp.io/pcp
```

Then build and install:

```
$ cd pcp
$ ./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var
$ make
# make install
```

More information on how to install Performance Co-Pilot can be found at:

[http://pcp.io/docs/installation.html#src](http://pcp.io/docs/installation.html#src)

### Vector

Vector is a static web application that runs inside the client's browser. It can run locally or deployed to any HTTP server available, like Apache or Nginx.

To run in locally, first clone the repo:

```
$ git clone https://github.com/Netflix/Vector.git
```

Make sure you have Bower installed on your system:

[http://bower.io/#getting-started](http://bower.io/#getting-started)

And install all dependencies:

```
$ cd Vector
$ bower install
```

To run it with Gulp, first make sure you have Gulp installed on your system:

[https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md)

Then, install the dependencies and execute the default Gulp task:

```
$ npm install
$ gulp
```

The default Gulp task has live reload enabled.

To run it with Python's SimpleHTTPServer:

```
$ cd Vector
$ python -m SimpleHTTPServer 8080
```

Then open Vector on your browser:

[http://localhost:8080](http://localhost:8080)

And enter the hostname from the instance you plan on monitoring. That's it!

## Issues

For bugs, questions and discussions please use the Github Issues.

## License

Copyright 2015 Netflix, Inc.

Licensed under the Apache License, Version 2.0 (the “License”); you may not use this file except in compliance with the License. You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an “AS IS” BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.