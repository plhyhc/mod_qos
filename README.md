# mod_qos 11.54
Apache rate limiting

This is a fork of mod_qos found at http://mod-qos.sourceforge.net/

The purpose of this fork is to return a HTTP response code of 429 instead of 500 when a connection is dropped, due to too many concurrent connections.

For example limiting the number of concurrent requests to the /api url to 6.  This is placed in the http.conf file of apache.  Normally when more than 6 requests were received a HTTP 500 was given, but instead a 429 is now given in this fork.

```
<IfModule mod_qos.c>
   # limits concurrent requests to the locations:
   # - /api max. 6 concurrent requests
   QS_LocRequestLimit            /api                   6
</IfModule>
```



