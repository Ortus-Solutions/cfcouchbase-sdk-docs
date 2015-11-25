#CFCouchbase SDK 2.0

###Requirements

- Couchbase Server 1.8+
    - For N1QL queries Couchbase Server 4.0+ 
- Adobe ColdFusion 9.01+
- Railo 3.1+
- Lucee 4.0+

###Features 

- Lightweight, standalone library can be used with any CFML application or CFML framework
- High performance
- Asynchronous calls 
- Auto-sharding of documents evenly across cluster
- 24/7 uptime via on-the-fly node removal and rebalance operations   
- Easily configurable
- Fully-featured API includes view management and execution
- Built on the official Java SDK, but customized to take advantage of CFML
- Optimistic concurrency control (Documents are not locked by default for maximum throughput)
- Conflict management via Compare And Swap (CAS) mechanism
- Full cluster and document stats available
- Provides direct access to underlying Java SDK for advanced usage 
- Ability to create as many Couchbase clients as necessary