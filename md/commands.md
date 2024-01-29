---
runme:
  id: 01HNAB0JD1E8048690TJKA9ARK
  version: v2.2
---

# Redis Commands

## Link

[redis](https://redis.io/commands/)

## Strings

- SET, SETNX, MSET, MSETNX
  - Set value, Set value if key does not exist, Set multiple values, Set
    multiple values if none of the keys exist

- GET, MGET, GETSET
  - Get value, Get multiple values, Set value, return old value

- PSETEX, SETEX
  - Set with expiry in seconds and milliseconds

- INCR, INCRBY, INCRBYFLOAT
  - Increment integer, Add to integer, Add to float

- DECR, DECRBY
  - Decrement integer, Subtract from integer

## Lists

- LPUSH, RPUSH
  - Add Value at beginning, Add value at the end

- LPUSHX, RPUSHX
  - Only push if key already exists

- LLEN, LRANGE
  - Get number of values, Get values from Start to Stop

- LINDEX, LSET, LINSERT
  - Get a value by index, Set a value by index, Add a value before or after
    another

- LREM, LTRIM
  - Delete element from list, Trim list by range

- LPOP, RPOP
  - Delete and Get the first element, Delete and Get the last element

## Hashes

- HSET, HSETNX, HMSET
  - Set field value, Set field value if field does not exist, Set multiple field
    values

- HGET, HMGET
  - Get field value, Get multiple field values

- HLEN, HKEYS, HVALS, HGETALL
  - Get Number of fields, Get all field keys, Get all field values, Get all
    fields and values

- HEXISTS, HDEL
  - Check field exists, delete field

- HINCRBY, HINCRBYFLOAT
  - Increment field integer value, Increment field float value

## Sets

- SADD, SMOVE, SREM, SPOP
  - Add one or more members, Move a member from one set to another, Remove one
    or more members, Remove and return one or multiple random members

- SCARD, SMEMBERS, SISMEMBER, SRANDMEMBER
  - Get number of members, Get all members, Test if member exists, Get one or
    more random members

- SUNION, SUNIONSTORE
  - Get all keys from all sets, no duplicates, same operation but store
    results in a new key

- SINTER, SINTERSTORE
  - Get keys that exist in all sets only, same operation but store results in
    a new key

- SDIFF, SDIFFSTORE
  - Return keys from the first set that are not in the subsequent sets, same
    operation but store results in a new key

## Sorted Sets

- ZADD, ZINCRBY
  - Add one or more members or update score, Increment the score of a member,
    Remove one or more members

- ZCARD, ZCOUNT, ZSCORE, ZRANK
  - Get number of members, Count members within sort key (score) range, Get
    the score associated with the given member, Determine the index of a member

- ZRANGE, ZRANGEBYLEX, ZRANGEBYSCORE, ZLEXCOUNT
  - Get members sorted by sort key (score), Return a range of members by
    lexicographical range, Return a range of members by score, Count the number of members between a given lexicographical range

- ZREM, ZREMRANGEBYLEX, ZREMRANGEBYRANK, ZREMRANGEBYSCORE
  - Remove one or more members, Remove all members between the given
    lexicographical range, Remove all members within the given indexes, Remove all members within the given scores

- ZREVRANGE, ZREVRANGEBYSCORE, ZREVRANK, ZREVRANGEBYLEX
  - Return a range of members by index with scores ordered from high to low,
    Return a range of members by score, with scores ordered from high to low, Determine the index of a member with scores ordered from high to low, Return a range of members by lexicographical range, ordered from higher to lower strings

- ZINTERSTORE, ZUNIONSTORE
  - Get keys that exist in all sets only and store the resulting sorted set in
    a new key, Add multiple sorted sets and store the resulting sorted set in a new key

## HyperLogLog

- PFADD, PFCOUNT
  - Append one or more elements, count number of elements

- PFMERGE
  - Merge elements from multiple keys

## Bulk Insertion

```sh {"id":"01HNAE8Z322BTRQC1XPCK5RE2E"}
cat data.txt | redis-cli --pipe
```

## Dump & Restore

```sh {"id":"01HNAF0NDXFEBR1TX7ZW7WAMMA"}
dump name
restore name 0 <paste code for key: name >
```