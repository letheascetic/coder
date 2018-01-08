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

* easy integration with scrapy/scrapy-redis
* kafka as message bus
* elk supported

        Rest: submit crawl requests
        Kafka Monitor: validates API requests in the correct format 
        Redis Monitor: moderate the redis based crawling queue, expire old crawls, stop existing crawls, gather information about the cluster

### frontera

* easy integration with scrapy
* relational databases support with SQLAlchemy and HBase key-value database out of the box
* ZeroMQ and Kafka as message bus
* customizable crawling policy

        strategy workers: scoring the links, deciding if link needs to be scheduled and when to stop crawling
        DB workers: store all the metadata, including scores and content, and generating new batches for downloading by spiders.

### scrapy-redis vs scrapy-cluster vs frontera




