### Redis

**Nosql In-Memory Database (SUPER FAST):**

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



 USEFUL LINKS:

  - https://redis.io/download (Installing Redis)
  - https://redis.io/commands (List of Redis Commands)