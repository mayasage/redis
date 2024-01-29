---
runme:
  id: 01HNAEFHBEP3HK7SE6SEP2CES3
  version: v2.2
---

# Concepts

## Redis Protocol

- RESP (REdis Serialization Protocol)
- simple implementation
- fast parsing
- human readable

In RESP, type of data depends on 1st byte:

- "+" for simple strings
- "-" for errors
- ":" for integers
- "$" for bulk strings
- "*" for arrays

```plaintext {"id":"01HNAEP54170K378QK0W3DP00B"}
# SET name Redis

*3<cr><lf>
$3<cr><lf>
SET<cr><lf>
$4<cr><lf>
name<cr><lf>
$5<cr><lf>
Redis<cr><lf>

OR

"*3\r\n$3\r\nSET\r\n$4\r\nname\r\n$5\r\nRedis\r\n"
```