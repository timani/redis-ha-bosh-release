# HA Redis BOSH Release

## About

I'm a fan of having multiple reusable BOSH releases that work together
to create a larger *"mega-deployment"*. For example, if your deployment
needs a more than single node [Redis][redis] installation then I think
you should put in the extra effort to create a new Redis release rather
than bolting it to an existing deployment.

This is a good idea because it enables the cluster to be considered as
a black box that provides a service by exposing a small interface (in
the Redis case this is probably a set of cluster IPs and the credentials
required to log in. By splitting out a new release we are able to
administrate and upgrade the Redis cluster separately.

This is that Redis release. I saw that Redis has a new feature coming
in version 2.8 called [Redis Sentinel][redis-sentinel] that manages a
cluster of Redis instances and provides HA features such as automatic
failover, monitoring, and notifications when the system becomes
unstable. I felt like this was a brilliant candidate to show the power
and flexibility that using [BOSH][bosh] can bring.

This release also serves as a teaching and example material that shows,
what I feel, are the best practices and idioms for when creating a
release. This project will be considered a success if it allows anyone
with a BOSH director so create a functional, high-availability Redis
cluster - on any infrastructure that BOSH supports - with next to no
effort.

Let's see how it goes.

[redis]: http://redis.io/ "Redis"
[redis-sentinel]: http://redis.io/topics/sentinel "Redis Sentinel"
[bosh]: http://github.com/cloudfoundry/bosh "BOSH"

## Authors

 * [Chris Brown](https://github.com/xoebus)
