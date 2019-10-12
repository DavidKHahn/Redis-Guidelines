## Redis
**NoSQL In-Memory Database (SUPER FAST):**

 - Open source database often used for really high performance scalable applications
 - Key-Value store similar to how we handle objects
 - Used for short-lived data in applications (JWT, session management, caching data, webpage hit counts)
 - Writes onto disk occasionally with snapshot capabilities to recover info

 **Redis CLI Commands:**

 - In terminal (MAC) cd into redis folder and ``src/redis-server`` to start Redis server.
 - Open 2nd terminal cd into redis folder again and ``src/redis-cli`` to open redis cli

 - ``SET name "Godzilla"`` -> sets key (name) and value (Godzilla)
 - ``GET name`` -> returns value "Godzilla"
 - ``EXISTS name`` -> checks if something exists (returns "(integer) 1" in this case)
 - ``DELETE name`` -> deletes name key
 - ``SET session "Jenny"`` -> sets session
 - ``EXPIRE session 10`` -> session will expire (delete) in 10 seconds
 - ``SET counter 1000``, ``INCRBY counter 100`` will increase amount by 100 to 1100
 - ``GET counter`` -> returns 1100 and ``DECR counter`` will return 1099
 - ``MSET a 2 b 5`` sets multiple variables at the same time
 - ``MGET a b`` returns multiple variables at the same time

**Redis Data Type for HASH Commands:**

 - ``HMSET user id 23 name "Jordan"`` setting hash for each data in this case need to use ``HGET user id`` or ``HGET user name`` to get "23" or "Jordan" also can use ``HGETALL user`` to return all data.

**Redis Data Type for LIST Commands (related to Linked Lists rather than Arrays):**

 - Main principle: *Insertion is fast with lists except not as fast compared to arrays when finding keys (great for creating really long lists with need to add elements quickly otherwise use sorted lists in Redis for faster searching or getting elements)*
 - ``LPUSH listname 100`` inserts data starting from left side into 'listname' list
 - ``RPUSH listname "Wilt Chamberlain"`` inserts data starting from right side into 'listname'
 - ``LRANGE listname 0 1`` retrieves data from 'listname' starting with range 0 to 1 returning '100', "Wilt Chamberlain" in this case
 - ``RPOP listname`` similar to Javascript's method of removing last data off list
 - ``LTRIM ourlist 0 1`` trims off data from list based on start index and ending index points

 **Redis Data Type for SETS and SORTED SETS Commands:**

- Sets in Redis are unordered collection of strings
- Sorted sets in Redis are ordered collection of strings
- Possible to add, remove, test for existing members in a group
- Similar to lists but sets does not allow repeated values or members (only allows single copies of elements)

**SETS:**
- ``SADD ourset 1 2 3 4 5`` adds elements to set
- ``SMEMBERS ourset`` returns elements from set
- ``SADD ourset 1 2 3 4`` will state '0' since none of the information has been added due to already having same copy
- ``SISMEMBER ourset 5`` checks 'ourset' to see if '5' exists and will return '1' (true in this case)

**SORTED SETS:**
- Every member of a Sorted Set is associated with a score which allows it to be ordered from smallest to greatest.
- ``ZADD team 50 "Wizards"``
- ``ZADD team 40 "Cavs"``
- ``ZRANGE team 0 1`` returns "Cavs" then "Wizards" based on the score (low to high)
- ``ZADD team 1 "Lakers"``
- ``ZRANGE team 0 2`` will return "Lakers", "Cavs", "Wizards"
- ``ZRANK team "Wizards"`` will return 2 based on order placed by score (Current Range: 0,1,2)

 **Useful Links:**

  - https://redis.io/download (Installing Redis)
  - https://redis.io/commands (List of Redis Commands)
