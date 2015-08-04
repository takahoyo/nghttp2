# spdylay install

## 参考サイト
[Spdylay - SPDY C Library &mdash; Spdylay 1.3.3-DEV documentation](http://tatsuhiro-t.github.io/spdylay/package_README.html#build-from-git)
[Releases · tatsuhiro-t/spdylay](https://github.com/tatsuhiro-t/spdylay/releases)

## 必要なパッケージをインストール

```
$ apt-get install autoconf automake autotools-dev libtool pkg-config zlib1g-dev libcunit1-dev libssl-dev libxml2-dev libevent-dev
```

## gitを使ってインストール
```
$ autoreconf -i
$ automake
$ autoconf
$ ./configure
$ make
```

# nghttp2 Install

##　参考サイト
[tatsuhiro-t/nghttp2](https://github.com/tatsuhiro-t/nghttp2)

[HTTP2 traffic in Wireshark | Is Mise Paul](https://ismisepaul.wordpress.com/2015/03/04/http2-traffic-in-wireshark/)

## 必要なパッケージをインストール

```
$ sudo apt-get install make binutils autoconf  automake autotools-dev libtool pkg-config \
zlib1g-dev libcunit1-dev libssl-dev libxml2-dev libev-dev libevent-dev libjansson-dev \
libjemalloc-dev cython python3.4-dev g++ python-setuptools
```

## gitを使ってインストール

```
$ git clone https://github.com/tatsuhiro-t/nghttp2.git
$ autoreconf -i
$ automake
$ autoconf
$ ./configure
$ make
```
