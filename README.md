# TerarkDB

TerarkDB is a core product of [Terark](http://terark.com). It is a RocksDB distribution that powered by &copy;&trade;Terark algorithms. with these algorithms, TerarkDB is able to store more data and access much faster than official RocksDB(3+X more data and 10+X faster) on same hardware.

TerarkDB is completely compatible(binary compatible) with official RocksDB, TerarkDB has two components:

## 1. TerarkZipTable

`TerarkZipTable` is contained in the [terark-zip-rocksdb](https://github.com/terark/terark-zip-rocksdb) submodule. `TerarkZipTable` is a `SSTable`(Static Sorted Table) implementation that using  &copy;&trade;Terark algorithms for RocksDB. 

## 2. Terark modified RocksDB

We forked RocksDB and made a few changes to fit our algorithms, we've added it as a submodule named [rocksdb](https://github.com/terark/rocksdb) here.

Our changes for RocksDB does not change any RocksDB API, and does not have any extra dependencies, say, Terark modified RocksDB does not depend on TerarkZipTable(Without TerarkZipTable, [Terark modified RocksDB](http://github/terark/rocksdb) works exactly same as official RocksDB).

Our changes includes:

-  Add optional two pass scan on SSTable build, existing SSTable is not impacted.
-  Add [TerarkZipTable config by env var](https://github.com/Terark/terarkdb/wiki/Try-TerarkDB-With-Minimal-Effort), this change using functions in libterark-zip-table as weak symbol, this is why it does not depends on TerarkZipTable.

# License
This software is open source, you can read the source code,
but you can not compile this software by yourself,
you must get [our](http://terark.com) comercial license to use this software in production.

- contact@terark.com
- [terark.com](http://terark.com)

# Documentation
Now you can experience our product easily, please refer to our product documentation for more detail.

[TerarkDB Documentation](https://github.com/Terark/terarkdb/wiki)
