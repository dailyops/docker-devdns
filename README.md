# Why do this?

 本地搭建开发友好的域名系统
 避免大量修改/etc/hosts文件

## Quickstart

```
docker-compose up -d
dig @localhost -p5300 a.test.dev

# 查看log
docker logs -f devdns
```

## Usage on Mac host

put etc-resolver-dev file into `/etc/resolver/dev`

try: 

```
ping some.demo.dev
```

## Todo

* optimize docker image size

## History

* 2016.12 开始使用https://github.com/madleech/MichaelsDnsServer
  build top on rubydns
  make bootable at mac host using plist file

* 2017.8 基于docker搭建本地环境
  rubydns不错且活跃
  rubydns底层实现技术已发生变化(不再使用celluloid-io);MichaelsDnsServer个人项目，好久不更新
  决定基于rubydns最新版本，参照MichaelDnsServer实现个人版本
  并通过版本关联和docker部署机制实现依赖固化

  更多参考[rubydns samples](https://github.com/socketry/rubydns/tree/master/examples)
