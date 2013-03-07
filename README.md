Nginx Binary Builder
=======================

This repo contains nginx source files with custom configuration used to build binary used in [abhishekmunie/heroku-buildpack-nginx](https://github.com/abhishekmunie/heroku-buildpack-nginx.git)
See [auto/options](https://github.com/abhishekmunie/nginx-binary-builder/blob/master/auto/options) for modified options.

Changed Options
==================

    NGX_FILE_AIO=YES
    NGX_IPV6=YES
    USE_PCRE=YES
    PCRE=./pcre-8.32
    PCRE_JIT=YES
    HTTP_SSL=YES
    HTTP_REALIP=YES
    HTTP_DAV=YES
    HTTP_SECURE_LINK=YES
    HTTP_FLV=YES
    HTTP_MP4=YES
    HTTP_GUNZIP=YES
    HTTP_GZIP_STATIC=YES
    HTTP_STUB_STATUS=YES
    MAIL=YES
    MAIL_SSL=YES
    USE_ZLIB=YES
    ZLIB=./zlib-1.2.7

Using Your Custom Configuration
==================================

* To use your custom configuration, clone this repo
    git clone https://github.com/abhishekmunie/nginx-binary-builder.git
* Customize the configurations
* Run `build_nginx` to build local repo or push your changes & run `build_github_nginx` to build your fork
* Download the archive
* Fork [abhishekmunie/heroku-buildpack-nginx](https://github.com/abhishekmunie/heroku-buildpack-nginx) on GitHub
* Replace `vendor/nginx` of buildpack with `objs/nginx` from archive
* Push the changes, to your fork
* create an app with `--buildpack <your-fork-url>` or `heroku config:set BUILDPACK_URL=<your-fork-url>` for existing app.