## Why a networked in-memory cache can be faster than hitting even a local database

### How fast is looking up something in Redis?

See [Redis benchmarks](http://redis.io/topics/benchmarks). 

![image](http://i.imgur.com/FAkQi20l.png)

Clearly, Redis lookup is not likely to be the bottleneck in the normal case.

The "in-memory" caching thing rocks.

### How fast is looking up something in a db like Postgres?

Here's a New Relic database query speed report from a real production system.

![image](http://i.imgur.com/yUTwS4tl.png)

As you can see, queries take varying numbers of milliseconds. This is actually a pretty fast server -- lots of production systems have queries that take longer than these examples.

### How fast is a network call to another server?

Usually your servers are going to be co-located physically with the application server(s) connecting to it.

Modern datacenters use Gigabit ethernet, which is... really fricking fast.

See the "Latency induced by network and communication" section in [http://redis.io/topics/latency](Redis latency).

> Clients connect to Redis using a TCP/IP connection or a Unix domain connection. The typical latency of a 1 Gbit/s network is about 200 us, while the latency with a Unix domain socket can be as low as 30 us. It actually depends on your network and system hardware. On top of the communication itself, the system adds some more latency (due to thread scheduling, CPU caches, NUMA placement, etc ...). System induced latencies are significantly higher on a virtualized environment than on a physical machine. The consequence is even if Redis processes most commands in sub microsecond range, a client performing many roundtrips to the server will have to pay for these network and system related latencies.

### Summary

* Redis processes most commands ultra-fast -- in less than 1 microsecond.
* Communicating with Redis is very fast -- takes 30 to 200 microseconds.
* Let's assume communicating with a local database server will be effectively instantaneous, in the low microseconds.
* HOWEVER Your db server will take an order of magnitude longer than looking up a cached result -- from a few milliseconds up to hundreds of milliseconds for more complex queries.

#### Conclusion

Looking up pre-computed, in-memory cached values in Redis will generally win.