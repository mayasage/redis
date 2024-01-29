---
runme:
  id: 01HNABRQ0J2MYDTSR6W6MM96G6
  version: v2.2
---

# Pointers

- Use Scan if you have a big database
- Use Object to get encoding of value
- Use Type to get type of value
- Has built in support for Master-Slave & Multi-Master replication
- Supports data sharding (data hashed into 16384 slots divided in servers)
- Built-in support for clusters and replicas

```sh {"id":"01HNAFKV5BH1JYA310S3JNPCQF"}
# Use Lua through EVAL inside Redis
EVAL "return {KEYS[1],KEYS[2],ARGV[1],ARGV[2]}" 2 key1 key2
```