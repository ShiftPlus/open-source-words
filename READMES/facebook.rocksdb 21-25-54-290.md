rocksdb a persistent key value store for flash and ram storage rocksdb is developed and maintained by facebook database engineering team it is built on earlier work on leveldb by sanjay ghemawat sanjay google com and jeff dean jeff google com this code is a library that forms the core building block for a fast key value server especially suited for storing data on flash drives it has a log structured merge database lsm design with flexible tradeoffs between write amplification factor waf read amplification factor raf and space amplification factor saf it has multi threaded compactions making it specially suitable for storing multiple terabytes of data in a single database start with example usage here https github com facebook rocksdb tree master examples see the github wiki for more explanation the public interface is in include callers should not include or rely on the details of any other header files in this package those internal apis may be changed without warning design discussions are conducted in https www facebook com groups rocksdb dev license rocksdb is dual licensed under both the gplv2 found in the copying file in the root directory and apache 2 0 license found in the license apache file in the root directory you may select at your option one of the above listed licenses