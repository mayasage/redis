---
runme:
  id: 01HNABDD5AMEEZRJ3XWV99CKF5
  version: v2.2
---

# Use Cases

## Strings

- Binary safe
- Generic
- Can serialize anything
- Can behave as random access vector
- Large data encoded into small space
- Internally held as a byte array
- Max size is 512 MB

### Strings - Use Cases

- Plain Strings
  - Serving static content
  - Redis.io used Redis DB to serve all static pages

- Caching frequently used data
- Counters like daily visitors

- Default & configs: SET app:config:website www.xyz.com

### Strings - Encoding Types

Redis decide automatically.

- int
- embstr: <44 bytes (<39 in Redis 3.x)
- raw: >44 bytes

## Lists

- An Array
- Can be encoded and memory optimized
- Can only contain strings
- Can container > 4 billion elements

### Lists - Use Cases

- Event Queue
  - Resque, Celery, Logstash

- Most recent data
  - Twitter stores latest tweets of a user in a list

- RSS Feeds
  - Pub-sub

- Leaderboards
  - Adding new articales
  - Sorting them by most viewed or voted

## Hashes

- Like JSON
- Schemaless
- String fields, string values
- Can contain > 4 billion elements

### Hashes - Use Cases

- Storing Object Properties
- In Schemaless Situations
- User Profiles
- User Posts
  - Instagram

- Storing Multi-Tenant Metrics

## Sets

- Provide Intersection, Difference and Union
- Max # is 4 billion

### Sets - Use Cases

- unique user visits
- sharded data of unique values
- ip tracking
- product recommendation
- ecommerce sales
- inappropriate content filtering

## Sorted Sets

- Implemented with skip list and a hash table
- fields are members, numerical values are scores
- ordered based on scores
- unique members only

### Sorted Sets - Use Cases

- Multiplayer Gaming
  - Update scores and load top scorers

- Forums
  - Rank highest voted answers (Redis.io)

## HyperLogLog

- probabilistic
- count unique things
- saves memory

### HyperLogLog - Use Cases

- count unique visitors
- keep best stocks of all times
- create unique names
- you only care about count