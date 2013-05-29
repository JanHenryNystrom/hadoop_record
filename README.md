hadoop_record [(β)][1] [![Build Status](https://secure.travis-ci.org/JanHenryNystrom/hadoop_record.png)](http://travis-ci.org/JanHenryNystrom/hadoop_record)
==========
A [hadoop record][2] compiler

  * [Introduction](#introduction)
  * [Features/Modules](#features)
  * [Examples](#examples)
  * [Build](#build)
  * [Install](#install)
  * [Contribute](#contribute) - Read if you're planning to submit patches

<a name='introduction'>

Introduction
------------

The main purpose of this compiler, for a format that has been discontinued by the hadoop project, is to support a 
[zookeeper client][3], since the [zookeeper project][4] still uses hadoop records. Bearing this rational in mind
it not surprising that one of the main concerns is to be compatible with the compiler "jute", used by the zookeeper
project. The compiler is compatible with the definition of the hadoop records, however jute deviates from that
definition and that is supported as options to this compiler (which are the defaults).

<a name='features'>

Features/Modules
--------

  * A Hadoop record compiler hadoop_record

<a name='examples'>

Examples
--------
Here's an example of using hadoop_record in the Erlang shell:

```erl
Eshell V5.8.4  (abort with ^G)
1> hadoop_record:compile(zookeeper, [{src_dir, "test/hadoop_record/distro"}]).
ok
```

An example of the use in a Makefile from the [zookeeper client][3] library:

```sh
erl -pa deps/hadoop_record/ebin -run hadoop_record cmd "hadoop_record/zookeeper" "{dest_dir, \"src\"}" -run init stop -noshell
```

<a name='build'>

Build
-----

meck requires [rebar][5] to build, but provides make support to download and
install rebar. To build jhn_stdlib, go to the jhn_stdlib directory and type:

```sh
make
```

To make sure hadoop_record works on your platform, run the tests:

```sh
make test
```

Two things might seem alarming when running the tests:

  1. Warnings emitted by cover
  2. En exception printed by SASL

Both are expected due to the way Erlang currently prints errors. The
important line you should look for is `All XX tests passed`, if that
appears all is correct.


<a name='install'>

Install
-------

If you want to install your own built version of hadoop_record add the ebin
directory to your Erlang code path or move the hadoop_record folder into your
release folder and make sure that folder is in your `ERL_LIBS`
environment variable.


<a name='contribute'>

Contribute
----------

Should you find yourself using jhn_stdlib and have issues, comments or
feedback please [create an issue here on GitHub.] [6]

Patches are greatly appreciated, but since these libraries reflect my
learning process and I have rather peculiar notions of code hygiene
I may do extensive rewrites that does not in any way diminish the
appreciation I feel or indeed [express.] [7]

For a much nicer history, please [write good commit messages][8].
I know I really should.

  [1]: http://en.wikipedia.org/wiki/Software_release_life_cycle
       "Software release life cycle"
  [2]: https://github.com/JanHenryNystrom/hadoop_record/blob/master/doc/hadoop_record/package.html
       "Classes and a record description language translator for simplifying serialization and deserialization of records in a language-neutral manner"
  [3]: http://github.com/JanHenryNystrom/zk
       "A zookeeper client library"
  [4]: http://zookeeper.apache.org/
       "Centralized service for maintaining configuration information, naming, providing distributed synchronization"
  [5]: http://github.com/rebar/rebar
       "Rebar - A build tool for Erlang"
  [6]: http://github.com/JanHenryNystrom/hadoop_record/issues
       "hadoop_record issues"
  [7]: http://github.com/JanHenryNystrom/hadoop_record/blob/master/THANKS
       "thanks"
  [8]: http://github.com/erlang/otp/wiki/Writing-good-commit-messages
       "Erlang/OTP commit messages"
