URL Shortener using Redis (Java + Docker)

This project implements a simple URL Shortener application in Java, utilizing Redis as the primary data store. The application runs in the terminal and supports full CRUD-style operations for managing short and long URLs.

It is containerized using Docker and orchestrated with Docker Compose, allowing easy execution of both the Java app and the Redis server.

Technologies Used

Java 17
Maven
Redis (via Docker)
Jedis (Redis client for Java)
Docker & Docker Compose
WSL (used for session logging on Linux)


The app flow:

Asks for a username
Provides the following menu:
  Insert new long URL
  Query original URL from a short code
  View usage statistics
  Exit


Redis Data Structures Used

Key	                  Type	              Description
url:long	            Hash	      Maps long URL → short code
url:short	            Hash	       Maps short code → long URL
user:<username>	      Set	     Tracks all short codes created by the user
user:count	          Hash	    Counts how many URLs each user has inserted
counter:<shortCode>	 String	   Tracks how many times each short URL was used

All operations are optimized for O(1) time complexity wherever possible.
