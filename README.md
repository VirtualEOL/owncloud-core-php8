# ownCloud, but ready for PHP 8.0 

This is a fork of ownCloud 10 (PHP version) compatible with PHP 8.0+.

Tested with PHP 8.2.8.

The ownCloud company claims that getting PHP 8 support is too hard. This is false. It took me only one hour to get ownCloud working on PHP 8.2, and I never looked at their code before in my life.

* No support is provided, I will not maintain this repo, I don't use ownCloud
* Installing using SQLite works
* Installing with MySQL does not work currently (probably easy to fix, but I'm not going to)
* But upgrading from an existing MySQL setup works
* Forking is welcome

This repo was made for benchmarking [Paheko](https://fossil.kd2.org/paheko/) and [KaraDAV](https://github.com/kd2org/karadav) performance against ownCloud and NextCloud.

## Performance

The scenario is for sharing a 1MB PDF file publicly via a sharing link. On a i5 laptop (powered by a battery, so low performance), using Apache2 and mod_php. The benchmark was done with ab doing 5000 requests, by batch of 200 concurrent requests.

* NextCloud: 8 req/sec (!!!!)
* ownCloud: 57 req/sec
* Paheko: 320 req/sec

Conclusion: ownCloud is slow. But NextCloud is incredibly slow! They really need to work on their performance.
