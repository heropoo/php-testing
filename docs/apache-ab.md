## Apache ab

模拟100个并发用户，对一个页面发送1000次请求
```
ab -n 1000 -c 100 http://localhost/
```
其中-n代表请求数，-c代表并发数

返回结果：
```
This is ApacheBench, Version 2.3 <$Revision: 1706008 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient)
Completed 100 requests
Completed 200 requests
Completed 300 requests
Completed 400 requests
Completed 500 requests
Completed 600 requests
Completed 700 requests
Completed 800 requests
Completed 900 requests
Completed 1000 requests
Finished 1000 requests


Server Software:        Apache/2.4.18  ##apache版本 
Server Hostname:        localhost  ##请求的域名
Server Port:            80   ##请求端口

Document Path:          /    ##请求的path
Document Length:        1195 bytes  ##页面内容大小

Concurrency Level:      100  ##并发数 
Time taken for tests:   2.338 seconds  ##共使用了多少时间
Complete requests:      1000  ##完成的请求数 
Failed requests:        0  ##失败的请求
Total transferred:      1388000 bytes  ##总共传输字节数，包含http的头信息等
HTML transferred:       1195000 bytes  ##html字节数，实际的页面传递字节数
Requests per second:    427.78 [#/sec] (mean)  ##每秒多少请求，这个是非常重要的参数数值，服务器的吞吐量 
Time per request:       233.767 [ms] (mean)  ##用户平均请求等待时间 
Time per request:       2.338 [ms] (mean, across all concurrent requests)  ##服务器平均处理时间，也就是服务器吞吐量的倒数
Transfer rate:          579.84 [Kbytes/sec] received  ##每秒获取的数据长度

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.4      0       5
Processing:    61  221  49.6    221     389
Waiting:       61  220  49.8    221     389
Total:         62  221  49.6    222     389

Percentage of the requests served within a certain time (ms)
  50%    222    ## 50%的请求在222ms内返回
  66%    240
  75%    252
  80%    261
  90%    280
  95%    302
  98%    326
  99%    347
 100%    389 (longest request)
```