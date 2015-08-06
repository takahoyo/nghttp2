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

# nghttp2 install

##　参考サイト
+ [tatsuhiro-t/nghttp2](https://github.com/tatsuhiro-t/nghttp2)
+ [HTTP2 traffic in Wireshark | Is Mise Paul](https://ismisepaul.wordpress.com/2015/03/04/http2-traffic-in-wireshark/)
+ [HTTP/2 WEBサーバ設定メモ【Nghttp2 (nghttpd) + CentOS 7】](https://blog.apar.jp/linux/2454/)
+ [nghttp2を使用する #1](http://qiita.com/0xfffffff7/items/c8f195c9f1782ca64e92)

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

## SSLサーバ証明書の作成


秘密鍵の作成

```
$ openssl genrsa 2048 > server.key
Generating RSA private key, 2048 bit long modulus
.....................................+++
...............................+++
e is 65537 (0x10001)
```

CSRの作成

```
$ openssl req -new -key server.key > server.csr
You are about to be asked to enter information that will be incorporated
into your certificate request.
What you are about to enter is what is called a Distinguished Name or a DN.
There are quite a few fields but you can leave some blank
For some fields there will be a default value,
If you enter '.', the field will be left blank.
-----
Country Name (2 letter code) [AU]:JP
State or Province Name (full name) [Some-State]:
Locality Name (eg, city) []:
Organization Name (eg, company) [Internet Widgits Pty Ltd]:CTF for Begginers
Organizational Unit Name (eg, section) []:Network
Common Name (e.g. server FQDN or YOUR name) []:ctf4b
Email Address []:

Please enter the following 'extra' attributes
to be sent with your certificate request
A challenge password []:
An optional company name []:
```

SSLサーバ証明書の作成

```
$ openssl x509 -days 3650 -req -signkey server.key < server.csr > server.crt
Signature ok
subject=/C=JP/ST=Some-State/O=CTF for Begginers/OU=Network/CN=ctf4b
Getting Private key
```

