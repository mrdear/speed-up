## Github加速指南

github加速分两种,一种是访问加速,一种是下载资源加速


### 访问加速

并没有特别好的方式,网上基本都是用更改hosts方式加速访问,然而网站背后ip变化频繁,这种方式很不稳定,可以的话建议直接走代理


### 资源访问加速

最近有个同学开源了 [https://github.com/YUX-IO/ffp](https://github.com/YUX-IO/ffp) ,软件的使用很简单,在任意资源连接前加
`https://ffp.yux.io`即可加速, 本质原理为利用中间服务器作为跳板机,转发相应请求达到加速目地.

eg:
```shell script
# slow 
curl -fsSL https://get.docker.com -o get-docker.sh

# fast
curl -fsSL https://ffp.yux.io/https://get.docker.com -o get-docker.sh

```
