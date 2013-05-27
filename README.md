hadoop_record [(β)][1] [![Build Status](https://secure.travis-ci.org/JanHenryNystrom/hadoop_record.png)](http://travis-ci.org/JanHenryNystrom/hadoop_record)
=============

A [hadoop record][2] compiler

The main purpose of this compiler, for a format that has been discontinued by the hadoop project, is to support a 
[zookeeper client][3], since the [zookeeper project][4] still uses hadoop records. Bearing this rational in mind
it not surprising that one of the main concerns is to be compatible with the compiler "jute", used by the zookeeper
project. The compiler is compatible with the definition of the hadoop records, however jute deviates from that
definition and that is supported as options to this compiler (which are the defaults).

  [1]: http://en.wikipedia.org/wiki/Software_release_life_cycle
       "Software release life cycle"
  [2]: https://github.com/JanHenryNystrom/hadoop_record/blob/master/doc/hadoop_record/package.html
       "Classes and a record description language translator for simplifying serialization and deserialization of records in a language-neutral manner"
  [3]: http://github.com/JanHenryNystrom/zk
       "A zookeeper client library"
  [4]: http://zookeeper.apache.org/
       "Centralized service for maintaining configuration information, naming, providing distributed synchronization"
