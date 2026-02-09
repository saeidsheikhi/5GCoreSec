# Dataset Statistics (auto-generated)

## Splits

- **Train shape:** (1753454, 29)

- **Test shape:** (194829, 29)

- **Label column:** `attack`

- **Train memory:** 623.69 MB

- **Test memory:** 69.31 MB



## Label / Class Distribution (Train vs Test)

| index | train_count | train_pct | test_count | test_pct |
| --- | --- | --- | --- | --- |
| benign | 1332625 | 76 | 148070 | 76 |
| DoS_MQTT | 250514 | 14.2869 | 27835 | 14.2869 |
| DDoS | 165070 | 9.41399 | 18341 | 9.4139 |
| Eavesdropping | 3525 | 0.201032 | 392 | 0.201202 |
| MITM | 677 | 0.03861 | 75 | 0.038495 |
| SQL Injection | 475 | 0.027089 | 53 | 0.027203 |
| Brute Force | 291 | 0.016596 | 32 | 0.016425 |
| Unauthorized Data Access | 207 | 0.011805 | 23 | 0.011805 |
| Device Spoofing | 70 | 0.003992 | 8 | 0.004106 |


- **Train imbalance ratio (majority/minority):** 19037.50

- **Test imbalance ratio (majority/minority):** 18508.75



## Schema

| index | column | dtype | non_null_pct | is_label |
| --- | --- | --- | --- | --- |
| 0 | ip.len | int64 | 100 | False |
| 1 | ip.flags.df | int64 | 100 | False |
| 2 | ip.flags.mf | float64 | 99.9337 | False |
| 3 | tcp.port | float64 | 99.9337 | False |
| 4 | tcp.ack_raw | float64 | 99.9337 | False |
| 5 | ip.fragments | float64 | 0.0663 | False |
| 6 | ip.ttl | int64 | 100 | False |
| 7 | ip.proto | float64 | 99.9337 | False |
| 8 | tcp.window_size.1 | float64 | 99.9337 | False |
| 9 | tcp.ack | float64 | 99.9337 | False |
| 10 | tcp.seq | float64 | 99.9337 | False |
| 11 | tcp.len | float64 | 99.9337 | False |
| 12 | tcp.stream | float64 | 99.9337 | False |
| 13 | tcp.urgent_pointer | float64 | 99.9337 | False |
| 14 | tcp.flags | object | 99.9337 | False |
| 15 | tcp.analysis.ack_rtt | float64 | 56.0816 | False |
| 16 | tcp.segments | float64 | 3.6623 | False |
| 17 | tcp.reassembled.length | float64 | 3.6623 | False |
| 18 | http.request | float64 | 22.1213 | False |
| 19 | udp.port | float64 | 0.0663 | False |
| 20 | udp.length | float64 | 0.0663 | False |
| 21 | frame.time_relative | float64 | 100 | False |
| 22 | frame.time_delta | float64 | 100 | False |
| 23 | tcp.time_relative | float64 | 99.9337 | False |
| 24 | tcp.time_delta | float64 | 99.9337 | False |
| 25 | tcp.srcport | float64 | 99.9337 | False |
| 26 | tcp.dstport | float64 | 99.9337 | False |
| 27 | http.request.uri | object | 22.055 | False |
| 28 | attack | object | 100 | True |


## Missing Values (Top columns)

### Train

| index | missing_count | missing_pct |
| --- | --- | --- |
| ip.fragments | 1752292 | 99.9337 |
| udp.port | 1752292 | 99.9337 |
| udp.length | 1752292 | 99.9337 |
| tcp.segments | 1689238 | 96.3377 |
| tcp.reassembled.length | 1689238 | 96.3377 |
| http.request.uri | 1366730 | 77.945 |
| http.request | 1365568 | 77.8787 |
| tcp.analysis.ack_rtt | 770089 | 43.9184 |
| ip.flags.mf | 1162 | 0.0663 |
| tcp.port | 1162 | 0.0663 |
| tcp.ack_raw | 1162 | 0.0663 |
| ip.proto | 1162 | 0.0663 |
| tcp.window_size.1 | 1162 | 0.0663 |
| tcp.ack | 1162 | 0.0663 |
| tcp.seq | 1162 | 0.0663 |


### Test

| index | missing_count | missing_pct |
| --- | --- | --- |
| ip.fragments | 194700 | 99.9338 |
| udp.port | 194700 | 99.9338 |
| udp.length | 194700 | 99.9338 |
| tcp.segments | 187705 | 96.3435 |
| tcp.reassembled.length | 187705 | 96.3435 |
| http.request.uri | 151591 | 77.8072 |
| http.request | 151462 | 77.741 |
| tcp.analysis.ack_rtt | 85940 | 44.1105 |
| ip.flags.mf | 129 | 0.0662 |
| tcp.port | 129 | 0.0662 |
| tcp.ack_raw | 129 | 0.0662 |
| ip.proto | 129 | 0.0662 |
| tcp.window_size.1 | 129 | 0.0662 |
| tcp.ack | 129 | 0.0662 |
| tcp.seq | 129 | 0.0662 |


## Duplicates

- **Train duplicate rows:** 1263796 (72.0747%)

- **Test duplicate rows:** 87314 (44.8157%)



## Feature Summary (Train)

- **# features (excluding label):** 28

- **Numeric features:** 26

- **Non-numeric features:** 2


### Numeric feature statistics (top 20 by std)

| index | count | mean | std | min | 1% | 5% | 50% | 95% | 99% | max |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| tcp.ack_raw | 1.75229e+06 | 1.91936e+09 | 1.25169e+09 | 0 | 7.76506e+06 | 1.48826e+08 | 1.8496e+09 | 3.96845e+09 | 4.28569e+09 | 4.29416e+09 |
| tcp.ack | 1.75229e+06 | 1.52191e+08 | 4.44555e+08 | 0 | 1 | 121 | 23425 | 1.3873e+09 | 2.00112e+09 | 4.29497e+09 |
| tcp.seq | 1.75229e+06 | 1.35229e+06 | 6.68639e+07 | 0 | 0 | 0 | 11673 | 51765 | 61805 | 4.29497e+09 |
| tcp.stream | 1.75229e+06 | 154388 | 316117 | 0 | 0 | 6 | 67 | 956982 | 1.09288e+06 | 1.09294e+06 |
| tcp.window_size.1 | 1.75229e+06 | 50378.9 | 26558.1 | 0 | 0 | 0 | 64128 | 64240 | 65024 | 268800 |
| udp.port | 1162 | 27621.8 | 24444.3 | 53 | 53 | 53 | 46113 | 52063 | 57548 | 64139 |
| tcp.srcport | 1.75229e+06 | 26521.3 | 21378.2 | 0 | 80 | 80 | 43570 | 45267 | 60037 | 65535 |
| ip.flags.mf | 1.75229e+06 | 26521.3 | 21378.2 | 0 | 80 | 80 | 43570 | 45267 | 60037 | 65535 |
| tcp.port | 1.75229e+06 | 15349.4 | 20830 | 0 | 80 | 80 | 80 | 44374 | 57842 | 65535 |
| tcp.dstport | 1.75229e+06 | 15349.4 | 20830 | 0 | 80 | 80 | 80 | 44374 | 57842 | 65535 |
| http.request | 387886 | 66.3863 | 1783.2 | 1 | 1 | 1 | 1 | 1 | 1 | 63413 |
| udp.length | 1162 | 391.391 | 485.065 | 30 | 30 | 33 | 88 | 1258 | 1258 | 1258 |
| frame.time_relative | 1.75345e+06 | 416.514 | 258.799 | 0 | 5.05736 | 37.6155 | 400.986 | 842.409 | 990.263 | 991.017 |
| tcp.time_relative | 1.75229e+06 | 222.04 | 197.388 | 0 | 0 | 0 | 194.388 | 557.122 | 589.184 | 656.181 |
| tcp.len | 1.75229e+06 | 121.331 | 113.148 | 0 | 0 | 0 | 120 | 308 | 308 | 1348 |
| tcp.reassembled.length | 64216 | 401.51 | 94.9454 | 400 | 400 | 400 | 400 | 400 | 400 | 15819 |
| ip.fragments | 1162 | 57.2556 | 5.19218 | 48 | 48 | 52 | 54 | 63 | 63 | 64 |
| tcp.time_delta | 1.75229e+06 | 0.68343 | 1.78749 | 0 | 0 | 0 | 0.000127 | 4.10537 | 4.82497 | 300.179 |
| ip.ttl | 1.75345e+06 | 62.9644 | 1.21652 | 17 | 63 | 63 | 63 | 63 | 63 | 64 |
| ip.len | 1.75345e+06 | 0.859659 | 0.34734 | 0 | 0 | 0 | 1 | 1 | 1 | 1 |

_(showing first 20 rows out of 26)_


### Non-numeric feature summary (top 20 by nunique)

| index | column | dtype | nunique | top_value | top_count |
| --- | --- | --- | --- | --- | --- |
| 0 | tcp.flags | object | 8 | 0x0018 | 849457 |
| 1 | http.request.uri | object | 5 | /contact | 195201 |

