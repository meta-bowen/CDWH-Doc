目前大量打印以下日志：
```java
2020-12-16 11:14:46 [ DEBUG ][ pool-6-thread-4:5717579 ] - org.conch.util.Logger.doLog(Logger.java:460):  Error sending request to peer 47.113.121.190: WebSocket session is not open
2020-12-16 11:14:46 [ DEBUG ][ pool-6-thread-4:5717579 ] - org.conch.util.Logger.doLog(Logger.java:460):  Failed to connect to peer testnb.mw.run[47.113.121.190]
2020-12-16 11:14:47 [ DEBUG ][ pool-6-thread-10:5718800 ] - org.conch.util.Logger.doLog(Logger.java:460):  Re-connect boot node testnb.mw.run[47.113.121.190] when its state is NON_CONNECTED
2020-12-16 11:14:47 [ DEBUG ][ pool-6-thread-10:5718801 ] - org.conch.util.Logger.doLog(Logger.java:460):  Error sending request to peer 47.113.121.190: WebSocket session is not open
2020-12-16 11:14:47 [ DEBUG ][ pool-6-thread-10:5718801 ] - org.conch.util.Logger.doLog(Logger.java:460):  Failed to connect to peer testnb.mw.run[47.113.121.190]
2020-12-16 11:14:49 [ DEBUG ][ pool-6-thread-12:5720381 ] - org.conch.util.Logger.doLog(Logger.java:460):  Re-connect boot node testboot.mw.run[47.91.209.186] when its state is NON_CONNECTED
2020-12-16 11:14:49 [ DEBUG ][ pool-6-thread-12:5720385 ] - org.conch.util.Logger.doLog(Logger.java:460):  Error sending request to peer 47.113.121.190: WebSocket session is not open
2020-12-16 11:14:49 [ DEBUG ][ pool-6-thread-12:5720385 ] - org.conch.util.Logger.doLog(Logger.java:460):  Failed to connect to peer testnb.mw.run[47.113.121.190]
2020-12-16 11:14:50 [ DEBUG ][ pool-6-thread-14:5721419 ] - org.conch.util.Logger.doLog(Logger.java:460):  Error sending request to peer 47.113.121.190: WebSocket session is not open
2020-12-16 11:14:50 [ DEBUG ][ pool-6-thread-14:5721419 ] - org.conch.util.Logger.doLog(Logger.java:460):  Failed to connect to peer testnb.mw.run[47.113.121.190]
2020-12-16 11:14:51 [ DEBUG ][ pool-6-thread-7:5722452 ] - org.conch.util.Logger.doLog(Logger.java:460):  Error sending request to peer 47.113.121.190: WebSocket session is not open
2020-12-16 11:14:51 [ DEBUG ][ pool-6-thread-7:5722452 ] - org.conch.util.Logger.doLog(Logger.java:460):  Failed to connect to peer testnb.mw.run[47.113.121.190]
2020-12-16 11:14:52 [ DEBUG ][ pool-6-thread-16:5723668 ] - org.conch.util.Logger.doLog(Logger.java:460):  Error sending request to peer 47.113.121.190: WebSocket session is not open
2020-12-16 11:14:52 [ DEBUG ][ pool-6-thread-16:5723668 ] - org.conch.util.Logger.doLog(Logger.java:460):  Failed to connect to peer testnb.mw.run[47.113.121.190]
2020-12-16 11:14:55 [ DEBUG ][ pool-6-thread-14:5726433 ] - org.conch.util.Logger.doLog(Logger.java:460):  Error sending request to peer 47.113.121.190: WebSocket session is not open
2020-12-16 11:14:55 [ DEBUG ][ pool-6-thread-14:5726433 ] - org.conch.util.Logger.doLog(Logger.java:460):  Failed to connect to peer testnb.mw.run[47.113.121.190]
```

2020-12-17 10:56:22 PeerImpl.send#660: Peer 47.113.121.190 version 0.0.5 returned error: {"cause":"Black the peer 183.15.178.15[183.15.178.15] caused by Exceed the access max count 1000 at one day","error":"Your peer is blacklisted"}, request was: {"useNATService":false,"protocol":1,"announcedAddress":"192.168.0.22","requestType":"getCumulativeDifficulty"}, disconnecting

2020-12-17 11:06:34 Guard.isSelfClosingPeer#131: Peer 47.113.121.190 returned error: You've blacklisted by them

2020-12-17 11:16:43 PeerImpl.send#660: Peer 47.113.121.190 version 0.0.5 returned error: {"cause":"Black the peer 183.15.178.15[183.15.178.15] caused by Exceed the access max count 1000 at one day","error":"Your peer is blacklisted"}, request was: {"cosUpdateTime":"2020-11-29 11:22:33","lastBlockHash":"dc121c0eab075853531cf25f5dadea6a91895073a3d0b5e8981c75df7693e14e","runningMode":"COMMAND","blockchainState":0,"lastBlockTimestamp":"2020-12-17 11:12:51","platform":"Windows 10 amd64","enableStorage":true,"protocol":1,"announcedAddress":"192.168.0.22","lastBlockId":-4768853044160600059,"currentFork":"MainFork","enableBizAPIs":true,"cumulativeDifficulty":"72962274349681","disabledAPIs":"","lastBlockHeight":6022,"apiServerIdleTimeout":30000,"requestType":"getInfo","bestPeer":"http:\/\/127.0.0.1:7216","services":"116","version":"0.0.5","useNATService":false,"apiPort":7216,"application":"COS","peerLoad":{"load":-1,"port":7216,"lastUpdate":1608173766216,"host":"127.0.0.1","uri":"http:\/\/127.0.0.1:7216"},"bindRsAccount":"CDW-EF9Z-8J9G-LLHC-9VU5U","lastBlockGenerator":"CDW-7KUZ-WFW7-MEQ9-6KG37","shareAddress":true}, disconnecting

以上出现不同打印的原因：
自闭列表的有效时间为 10 min，需考虑是否需要调整自闭列表的时间。