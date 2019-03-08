# fips-libcurl-ssl

Static pre-compiled lib-curl libraries for fips build system. Stripped from all protocols except HTTP and HTTPS. Build with zlib support.

### Pre-combiled library

libcurlssl.a has been created like this:

1. git clone https://github.com/bagder/curl.git
2. cd curl
3. ./buildconfig (+ install any missing packages it complains about)
4. ./configure --disable-shared --enable-http --disable-ftp --disable-file --disable-ldap --disable-rtsp --disable-dict --disable-telnet --disable-tftp --disable-pop3 --disable-imap --disable-smtp --disable-gopher --disable-manual --disable-sspi --disable-crypto-auth --disable-ntlm-wb --disable-tls-srp --disable-cookies --with-ssl --without-gnutls --without-polarssl --without-cyassl --without-nss --without-axtls --without-ca-path --without-libmetalink --without-libssh2 --without-librtmp --without-winidn --without-libidn --without-nghttp2
5. make
6. the resulting lib is curl/lib/.libs/libcurl.a

### Dependencies

__zlib__: https://github.com/floooh/fips-zlib.git

__libssl__ and __libcrypto__: https://github.com/GeertArien/fips-openssl.git
