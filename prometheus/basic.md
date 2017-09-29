# 基础概念

## 数据模型

Prometheus 存储的是时序数据, 即按照相同时序(相同的名字和标签)，以时间维度存储连续的数据的集合。

### 时序索引

时序(time series) 是由名字(Metric)，以及一组 key/value 标签定义的，具有相同的名字以及标签属于相同时序。

时序的名字由 ASCII 字符，数字，下划线，以及冒号组成，它必须满足正则表达式 [a-zA-Z_:][a-zA-Z0-9_:]*, 其名字应该具有语义化，一般表示一个可以度量的指标，例如 http_requests_total, 可以表示 http 请求的总数。

时序的标签可以使 Prometheus 的数据更加丰富，能够区分具体不同的实例，例如 http_requests_total{method="POST"} 可以表示所有 http 中的 POST 请求。

标签名称由 ASCII 字符，数字，以及下划线组成， 其中 __ 开头属于 Prometheus 保留，标签的值可以是任何 Unicode 字符，支持中文。

### 时序样本

按照某个时序以时间维度采集的数据，称之为样本，其值包含：

* 一个 float64 值
* 一个毫秒级的 unix 时间戳

### 格式

Prometheus 时序格式与 OpenTSDB 相似：

    <metric name>{<label name>=<label value>, ...}

其中包含时序名字以及时序的标签。

## 时序 4 种类型

Prometheus 时序数据分为 Counter, Gauge, Histogram, Summary 四种类型。

### Counter

Counter 表示收集的数据是按照某个趋势（增加／减少）一直变化的，我们往往用它记录服务请求总量，错误总数等。

例如 Prometheus server 中 http_requests_total, 表示 Prometheus 处理的 http 请求总数，我们可以使用 delta, 很容易得到任意区间数据的增量，这个会在 PromQL 一节中细讲。

### Gauge

Gauge 表示搜集的数据是一个瞬时的，与时间没有关系，可以任意变高变低，往往可以用来记录内存使用率、磁盘使用率等。

例如 Prometheus server 中 go_goroutines, 表示 Prometheus 当前 goroutines 的数量。

### Histogram

Histogram 由 <basename>_bucket{le="<upper inclusive bound>"}，<basename>_bucket{le="+Inf"}, <basename>_sum，<basename>_count 组成，主要用于表示一段时间范围内对数据进行采样，（通常是请求持续时间或响应大小），并能够对其指定区间以及总数进行统计，通常我们用它计算分位数的直方图。

例如 Prometheus server 中 prometheus_local_storage_series_chunks_persisted, 表示 Prometheus 中每个时序需要存储的 chunks 数量，我们可以用它计算待持久化的数据的分位数。

### Summary

Summary 和 Histogram 类似，由 <basename>{quantile="<φ>"}，<basename>_sum，<basename>_count 组成，主要用于表示一段时间内数据采样结果，（通常是请求持续时间或响应大小），它直接存储了 quantile 数据，而不是根据统计区间计算出来的。

例如 Prometheus server 中 prometheus_target_interval_length_seconds。

### Histogram vs Summary

* 都包含 <basename>_sum，<basename>_count
* Histogram 需要通过 <basename>_bucket 计算 quantile, 而 Summary 直接存储了 quantile 的值。


