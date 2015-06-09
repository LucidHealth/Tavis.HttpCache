# Tavis.HttpCache

This library is an implementation of a HTTP cache.  It is designed to be plugged into the System.Net.Http.HttpClient class as a message handler.


			
             var httpCache = new HttpCache(new InMemoryContentStore());
             var cachingHandler = new HttpCacheHandler(httpClientHandler, httpCache);
             var client = new HttpClient(cachingHandler);


The objective of this library is to implement all the functionality described by the [HTTP caching specification RFC 7234](https://tools.ietf.org/html/rfc7234).

The motivation for this library was to provide a PCL compatible replacement for WinInetProxy cache and fix the parts of that library that do not work.

The caching logic and the storage mechanism are separated to allow different storage options.  Currently there is only an in-memory store.  A file based store is high on the list of priorities.
