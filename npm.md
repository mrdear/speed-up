## NPM 加速指南

`npm` 加速利用的是淘宝源,在任意npm命令后加`--registry=https://registry.npm.taobao.org`即可.


**清单1: 对单独命令使用淘宝源**

```sh
npm install -g angular-cli --registry=https://registry.npm.taobao.org
```

**清单2: 配置全局npm下载源**

```sh
# 查看当前源
npm config get registry

# 全局设置淘宝源
npm config set registry http://registry.npm.taobao.org/

# 全局设置npm默认源
npm config set registry https://registry.npmjs.org/
```

## YARN 加速指南

`YARN`和`NPM`比较类似,两者的配置方法差不多.


**清单3: 对单独命令使用淘宝源**

```sh
yarn global add angular-cli --registry=https://registry.npm.taobao.org
```


**清单4: 配置全局npm下载源**

```sh
# 查看当前源
yarn config get registry

# 全局设置淘宝源
yarn config set registry https://registry.npm.taobao.org

# 全局设置yarn默认源
yarn config set registry https://registry.yarnpkg.com
```