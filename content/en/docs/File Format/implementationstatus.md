---
title: "Implementation status"
linkTitle: "Implementation status"
weight: 8
---
### Physical types

| Data type                                 | C++   | Java   | Go    | Rust  |
| ----------------------------------------- | ----- | ------ | ----- | ----- |
| BOOLEAN                                   |       |        |       |       |
| INT32                                     |       |        |       |       |
| INT64                                     |       |        |       |       |
| INT96                                     |       |        |       |       |
| FLOAT                                     |       |        |       |       |
| DOUBLE                                    |       |        |       |       |
| BYTE_ARRAY                                |       |        |       |       |
| FIXED_LEN_BYTE_ARRAY                      |       |        |       |       |

### Logical types

| Data type                                 | C++   | Java   | Go    | Rust  |
| ----------------------------------------- | ----- | ------ | ----- | ----- |
| STRING                                    |       |        |       |       |
| ENUM                                      |       |        |       |       |
| UUID                                      |       |        |       |       |
| 8 and 16 bit signed INT                   |       |        |       |       |
| 8, 16, 32, 64 bit unsigned INT            |       |        |       |       |
| DECIMAL (INT32)                           |       |        |       |       |
| DECIMAL (INT64)                           |       |        |       |       |
| DECIMAL (BYTE_ARRAY)                      |       |        |       |       |
| DECIMAL (FIXED_LEN_BYTE_ARRAY)            |       |        |       |       |
| DATE                                      |       |        |       |       |
| TIME (INT32)                              |       |        |       |       |
| TIME (INT64)                              |       |        |       |       |
| TIMESTAMP (INT32)                         |       |        |       |       |
| TIMESTAMP (INT64)                         |       |        |       |       |
| INTERVAL                                  |       |        |       |       |
| JSON                                      |       |        |       |       |
| BSON                                      |       |        |       |       |
| LIST                                      |       |        |       |       |
| MAP                                       |       |        |       |       |
| UNKNOWN                                   |       |        |       |       |

### Encoding

| Encoding                                  | C++   | Java   | Go    | Rust  |
| ----------------------------------------- | ----- | ------ | ----- | ----- |
| PLAIN                                     |       |        |       |       |
| PLAIN_DICTIONARY                          |       |        |       |       |
| RLE_DICTIONARY                            |       |        |       |       |
| RLE                                       |       |        |       |       |
| BIT_PACKED                                |       |        |       |       |
| DELTA_BINARY_PACKED                       |       |        |       |       |
| DELTA_LENGTH_BYTE_ARRAY                   |       |        |       |       |
| DELTA_BYTE_ARRAY                          |       |        |       |       |
| BYTE_STREAM_SPLIT                         |       |        |       |       |

### Compression

| Compression                               | C++   | Java   | Go    | Rust  |
| ----------------------------------------- | ----- | ------ | ----- | ----- |
| UNCOMPRESSED                              |       |        |       |       |
| SNAPPY                                    |       |        |       |       |
| GZIP                                      |       |        |       |       |
| LZO                                       |       |        |       |       |
| BROTLI                                    |       |        |       |       |
| LZ4                                       |       |        |       |       |
| ZSTD                                      |       |        |       |       |
| LZ4_RAW                                   |       |        |       |       |

### Other format level features

|                                           | C++   | Java   | Go    | Rust  |
| ----------------------------------------- | ----- | ------ | ----- | ----- |
| xxHash Bloom filters                      |       |        |       |       |
| bloom filter length                       |       |        |       |       |
| Statistics min_value, max_value           |       |        |       |       |
| Column index                              |       |        |       |       |
| Offset index                              |       |        |       |       |
| Modular encryption                        |       |        |       |       |
| Page CRC32 checksum                       |       |        |       |       |
| Modular encryption                        |       |        |       |       |

### High level data API-s for parquet feature usage

| Format                                       | C++   | Java   | Go    | Rust  |
| -------------------------------------------- | ----- | ------ | ----- | ----- |
| Hive-style partitioning                      |       |        |       |       |
| Partition pruning on the partition column    |       |        |       |       |
| External column data                         |       |        |       |       |
| RowGroup Sorting column                      |       |        |       |       |
| Read / Write RowGroup metadata and data (1)  |       |        |       |       |
| RowGroup pruning using statistics            |       |        |       |       |
| Read / Write page metadata and data (2)      |       |        |       |       |
| Page pruning using projection pushdown       |       |        |       |       |
| Page pruning using statistics                |       |        |       |       |
| Page pruning using bloom filter              |       |        |       |       |

* \(1) Ability to construct RowGroup objects from existing RowGroups or raw values (eg. without decoding or decompressing lower level data when read)

* \(2) Ability to construct Page objects from existing Pages or raw values (eg. without decoding or decompressing lower level data when read)