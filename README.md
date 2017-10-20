# php-framework-benchmark

php framework benchmark (include laravel、symfony、silex、lumen、slim、yii2、tastphp)

All framework response "ok" benchmark.

### Test benchmark environment

```
OS Name:        Mac OS X
OS Version:     10.12.6
Architecture:   x86_64
CPU：Intel Core i7  1.7 GHz *2
RAM：8 GB
PHP version 7.1.10
```

### Framework version

```
Laravel version 5.5.0
Lumen version 5.5.0
symfony version 3.3.10
Silex version 2.0.2
Silm version 3.1.4
yii2 version 2.0.12
Tastphp version 1.3.6
```


### Result

<img src="https://raw.githubusercontent.com/xujiajun/php-framework-benchmark/master/imgs/php-framework-vs.png">


## Detail

### Laravel ab test

Laravel version 5.5.0

[optimization](https://laravel.com/docs/5.5/deployment#autoloader-optimization)

run commands before test:

```
composer install --optimize-autoloader
php artisan config:cache
// php artisan route:cache  //cannot use route caching if you have ANY route closures
```

ab test result:

```
➜  laravel-5.5.0 git:(master) ✗ ab -n 1000 -c 100 http://laravel-benchmark.dev/
This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking laravel-benchmark.dev (be patient)
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


Server Software:        nginx/1.12.0
Server Hostname:        laravel-benchmark.dev
Server Port:            80

Document Path:          /
Document Length:        2 bytes

Concurrency Level:      100
Time taken for tests:   3.295 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      982346 bytes
HTML transferred:       2000 bytes
Requests per second:    303.46 [#/sec] (mean)
Time per request:       329.538 [ms] (mean)
Time per request:       3.295 [ms] (mean, across all concurrent requests)
Transfer rate:          291.11 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    1   1.8      0       8
Processing:    22  311  59.4    315     571
Waiting:       22  311  59.4    315     571
Total:         30  312  58.0    315     571

Percentage of the requests served within a certain time (ms)
  50%    315
  66%    335
  75%    351
  80%    354
  90%    362
  95%    367
  98%    378
  99%    407
 100%    571 (longest request)

```

### Lumen version 5.5.0

run commands before test:

```
composer install --optimize-autoloader
```

ab test result:

```
➜  lumen-5.5.0 git:(master) ✗ ab -n 1000 -c 100 http://lumen-benchmark.dev/
This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking lumen-benchmark.dev (be patient)
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


Server Software:        nginx/1.12.0
Server Hostname:        lumen-benchmark.dev
Server Port:            80

Document Path:          /
Document Length:        2 bytes

Concurrency Level:      100
Time taken for tests:   0.639 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      199000 bytes
HTML transferred:       2000 bytes
Requests per second:    1565.02 [#/sec] (mean)
Time per request:       63.897 [ms] (mean)
Time per request:       0.639 [ms] (mean, across all concurrent requests)
Transfer rate:          304.14 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.9      0       6
Processing:     9   61   9.9     62      74
Waiting:        9   61   9.9     62      74
Total:         14   61   9.1     62      74

Percentage of the requests served within a certain time (ms)
  50%     62
  66%     64
  75%     65
  80%     66
  90%     68
  95%     71
  98%     72
  99%     73
 100%     74 (longest request)
 ```

### Symfony version 3.3.10

run commands before test:

```
composer install --optimize-autoloader
```

ab test result:

```
➜  symfony-3.3.10 git:(master) ✗ ab -n 1000 -c 100 http://symfony-benchmark.dev/
This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking symfony-benchmark.dev (be patient)
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


Server Software:        nginx/1.12.0
Server Hostname:        symfony-benchmark.dev
Server Port:            80

Document Path:          /
Document Length:        2 bytes

Concurrency Level:      100
Time taken for tests:   1.716 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      237000 bytes
HTML transferred:       2000 bytes
Requests per second:    582.60 [#/sec] (mean)
Time per request:       171.646 [ms] (mean)
Time per request:       1.716 [ms] (mean, across all concurrent requests)
Transfer rate:          134.84 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    1   0.9      0       5
Processing:    12  163  34.6    168     218
Waiting:       12  163  34.6    168     218
Total:         17  163  33.9    169     218
WARNING: The median and mean for the initial connection time are not within a normal deviation
        These results are probably not that reliable.

Percentage of the requests served within a certain time (ms)
  50%    169
  66%    176
  75%    184
  80%    187
  90%    199
  95%    207
  98%    211
  99%    213
 100%    218 (longest request)
 ```
 
### Silex version 2.0.2

run commands before test:

```
composer install --optimize-autoloader
```

ab test result:

```
➜  silex-2.0.2 git:(master) ✗ ab -n 1000 -c 100 http://silex-benchmark.dev/
This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking silex-benchmark.dev (be patient)
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


Server Software:        nginx/1.12.0
Server Hostname:        silex-benchmark.dev
Server Port:            80

Document Path:          /
Document Length:        2 bytes

Concurrency Level:      100
Time taken for tests:   0.747 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      237000 bytes
HTML transferred:       2000 bytes
Requests per second:    1338.53 [#/sec] (mean)
Time per request:       74.709 [ms] (mean)
Time per request:       0.747 [ms] (mean, across all concurrent requests)
Transfer rate:          309.80 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.9      0       4
Processing:    15   71   9.3     73      88
Waiting:       15   71   9.3     73      88
Total:         20   72   8.6     73      89

Percentage of the requests served within a certain time (ms)
  50%     73
  66%     74
  75%     75
  80%     76
  90%     79
  95%     81
  98%     82
  99%     84
 100%     89 (longest request)
 ```

### slim version 3.1.4

run commands before test:

```
composer install --optimize-autoloader
```

ab test:

```
➜  silm-3.1.4 git:(master) ✗ ab -n 1000 -c 100 http://slim-benchmark.dev/
This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking slim-benchmark.dev (be patient)
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


Server Software:        nginx/1.12.0
Server Hostname:        slim-benchmark.dev
Server Port:            80

Document Path:          /
Document Length:        2 bytes

Concurrency Level:      100
Time taken for tests:   0.703 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      333000 bytes
HTML transferred:       2000 bytes
Requests per second:    1423.44 [#/sec] (mean)
Time per request:       70.252 [ms] (mean)
Time per request:       0.703 [ms] (mean, across all concurrent requests)
Transfer rate:          462.90 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   1.0      0       5
Processing:     7   67  15.7     65     210
Waiting:        7   66  15.7     65     210
Total:         12   67  15.1     66     210

Percentage of the requests served within a certain time (ms)
  50%     66
  66%     69
  75%     70
  80%     72
  90%     88
  95%     96
  98%    102
  99%    105
 100%    210 (longest request)
 ```

### yii2 version 2.0.12

run commands before test:

```
composer install --optimize-autoloader

```

ab test result:

```
➜  yii2-2.0.12 git:(master) ✗ ab -n 1000 -c 100 http://yii2-benchmark.dev/
This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking yii2-benchmark.dev (be patient)
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


Server Software:        nginx/1.12.0
Server Hostname:        yii2-benchmark.dev
Server Port:            80

Document Path:          /
Document Length:        2 bytes

Concurrency Level:      100
Time taken for tests:   0.649 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      165000 bytes
HTML transferred:       2000 bytes
Requests per second:    1539.74 [#/sec] (mean)
Time per request:       64.946 [ms] (mean)
Time per request:       0.649 [ms] (mean, across all concurrent requests)
Transfer rate:          248.10 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   1.0      0       5
Processing:    16   62   9.2     61      96
Waiting:       16   62   9.2     61      96
Total:         21   62   9.2     61      98

Percentage of the requests served within a certain time (ms)
  50%     61
  66%     64
  75%     67
  80%     69
  90%     73
  95%     77
  98%     89
  99%     94
 100%     98 (longest request)
 ```
 
### Tastphp version 1.3.6

run commands before test:

```
composer install --optimize-autoloader
php bin/console cache:config
php bin/console cache:route

```

ab test result:

```
➜  tastphp-1.3.6 git:(master) ✗ ab -n 1000 -c 100 http://tastphp-benchmark.dev/
This is ApacheBench, Version 2.3 <$Revision: 1757674 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking tastphp-benchmark.dev (be patient)
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


Server Software:        nginx/1.12.0
Server Hostname:        tastphp-benchmark.dev
Server Port:            80

Document Path:          /
Document Length:        2 bytes

Concurrency Level:      100
Time taken for tests:   0.487 seconds
Complete requests:      1000
Failed requests:        0
Total transferred:      165000 bytes
HTML transferred:       2000 bytes
Requests per second:    2051.92 [#/sec] (mean)
Time per request:       48.735 [ms] (mean)
Time per request:       0.487 [ms] (mean, across all concurrent requests)
Transfer rate:          330.63 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    0   0.8      0       4
Processing:     7   46   7.5     48      55
Waiting:        7   46   7.5     48      55
Total:         11   46   6.8     48      56

Percentage of the requests served within a certain time (ms)
  50%     48
  66%     49
  75%     50
  80%     51
  90%     52
  95%     53
  98%     54
  99%     55
 100%     56 (longest request)
```




