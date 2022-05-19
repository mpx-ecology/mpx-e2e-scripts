# e2e-scripts

提供 e2e 测试中需要的命令脚本，包含以下脚本及命令：

1. 用于给开发环境安装的，串行执行 spec 文件的 e2e-runner 命令；

## 1. e2e-runner

**注意这个命令不支持全局调用**

调用这个命令需要在小程序项目根目录下执行，另外此目录要求存在 .e2erc.js 配置文件，配置文件形如：

```javascript
module.exports = {
  sequence: [ // spec 文件顺序
    // 'bHomeToCancelOrder',
    // 'BHomeToPayment',
    'CHomeToCancelOrder',
    'CHomeToPayment',
    // 'BHomeToCancelOrderBooking'
  ],
  reportsDir: 'test/reports', // 测试报告存放文件夹
  testSuitsDir: 'test/e2e/suits/', // spec 文件存放目录
  record: true // 是否需要记录运行时间日志，为 true 时会在项目目录中创建 e2e-record.txt 文件
}

```

### 1.1 安装
```shell script
$ npm install @mpxjs/e2e-scripts --save-dev
```

### 1.2 调用
```shell script
npx e2e-runner
```
