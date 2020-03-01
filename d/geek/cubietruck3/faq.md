### [返回 Cubietruck3](index.md)

------

# 我整理的FAQ

## Lubuntu 13

### 执行 ```php -v``` 时报以下错误

```
PHP Warning:  PHP Startup: Unable to load dynamic library '/usr/lib/php5/20121212+lfs/curl.so' - /usr/lib/arm-linux-gnueabihf/libgssapi.so.3: symbol krb5_ntlm_init_get_challange, version HEIMDAL_KRB5_2.0 not defined in file libkrb5.so.26 with link time reference in Unknown on line 0
```

__解决方法__

```
# apt-get install libgssapi3-heimdal
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages will be upgraded:
  libgssapi3-heimdal
1 upgraded, 0 newly installed, 0 to remove and 264 not upgraded.
Need to get 74.4 kB of archives.
After this operation, 6,144 B of additional disk space will be used.
Get:1 http://ports.ubuntu.com/ubuntu-ports/ utopic/main libgssapi3-heimdal armhf 1.6~rc2+dfsg-8 [74.4 kB]
Fetched 74.4 kB in 1s (45.5 kB/s)
(Reading database ... 33850 files and directories currently installed.)
Preparing to replace libgssapi3-heimdal:armhf 1.6~git20120403+dfsg1-2 (using .../libgssapi3-heimdal_1.6~rc2+dfsg-8_armhf.deb) ...
Unpacking replacement libgssapi3-heimdal:armhf ...
```
