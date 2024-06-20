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
| INT96 (1)                                 |       |        |       |       |
| FLOAT                                     |       |        |       |       |
| DOUBLE                                    |       |        |       |       |
| BYTE_ARRAY                                |       |        |       |       |
| FIXED_LEN_BYTE_ARRAY                      |       |        |       |       |

* \(1) This type is deprecated, but as of 2024 it's common in currently produced parquet files.


### Logical types

| Data type                                 | C++   | Java   | Go    | Rust  |
| ----------------------------------------- | ----- | ------ | ----- | ----- |
| STRING                                    |       |        |       |       |
| ENUM                                      |       |        |       |       |
| UUID                                      |       |        |       |       |
| 8, 16, 32, 64 bit signed and unsigned INT |       |        |       |       |
| DECIMAL (INT32)                           |       |        |       |       |
| DECIMAL (INT64)                           |       |        |       |       |
| DECIMAL (BYTE_ARRAY)                      |       |        |       |       |
| DECIMAL (FIXED_LEN_BYTE_ARRAY)            |       |        |       |       |
| DATE                                      |       |        |       |       |
| TIME (INT32)                              |       |        |       |       |
| TIME (INT64)                              |       |        |       |       |
| TIMESTAMP (INT64)                         |       |        |       |       |
| INTERVAL                                  |       |        |       |       |
| JSON                                      |       |        |       |       |
| BSON                                      |       |        |       |       |
| LIST                                      |       |        |       |       |
| MAP                                       |       |        |       |       |
| UNKNOWN (always null)                     |       |        |       |       |
| FLOAT16                                   |       |        |       |       |

### Encodings

| Encoding                                  | C++   | Java   | Go    | Rust  |
| ----------------------------------------- | ----- | ------ | ----- | ----- |
| PLAIN                                     |       |        |       |       |
| PLAIN_DICTIONARY                          |       |        |       |       |
| RLE_DICTIONARY                            |       |        |       |       |
| RLE                                       |       |        |       |       |
| BIT_PACKED (deprecated)                   |       |        |       |       |
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
| LZ4 (deprecated)                          |       |        |       |       |
| ZSTD                                      |       |        |       |       |
| LZ4_RAW                                   |       |        |       |       |

### Other format level features

|                                           | C++   | Java   | Go    | Rust  |
| ----------------------------------------- | ----- | ------ | ----- | ----- |
| xxxHash-based bloom filters               |       |        |       |       |
| Bloom filter length (1)                   |       |        |       |       |
| Statistics min_value, max_value           |       |        |       |       |
| Page index                                |       |        |       |       |
| Page CRC32 checksum                       |       |        |       |       |
| Modular encryption                        |       |        |       |       |
| Size statistics (2)                       |       |        |       |       |


* \(1) In parquet.thrift: ColumnMetaData->bloom_filter_length

* \(2) In parquet.thrift: ColumnMetaData->size_statistics

### High level data APIs for Parquet feature usage

| Format                                       | C++   | Java   | Go    | Rust  |
| -------------------------------------------- | ----- | ------ | ----- | ----- |
| External column data (1)                     |       |        |       |       |
| Row group "Sorting column" metadata (2)      |       |        |       |       |
| Row group pruning using statistics           |       |        |       |       |
| Reading select columns only                  |       |        |       |       |
| Page pruning using statistics                |       |        |       |       |
| Page pruning using bloom filter              |       |        |       |       |


* \(1) In parquet.thrift: ColumnChunk->file_path

* \(2) In parquet.thrift: RowGroup->sorting_columns
