# distributed crawler framework

* scrapy-redis
* scrapy-cluster
* frontera

### scrapy arch

* single process for per spider
* requests/response queue in memory

### scrapy redis

* multi same spiders run in parallel
* store requests/response in redis queue, share requests/response for all same spiders
* new scheduler/pipline for scrapy-redis

### scrapy-cluster

> Kafka Monitor: validates API requests in the correct format 
> Redis Monitor: moderate the redis based crawling queue, expire old crawls, stop existing crawls, gather information about the cluster


### scrapy-redis vs scrapy-cluster vs frontera


