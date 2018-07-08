请注意：该项目基于Fabric的1.0-beta版本，可能跟最新的版本存在不兼容的情况。chaincode的API部分应该是兼容的。

### 基于区块链的农业供应链解决方案demo

#### 说明
* 该demo作为演示，展示了如何在农业场景下使用区块链:
  * 农产品流转溯源
  * 资金流
  * 信息流
  * 金融风控

* 各个角色：
  * 商户： 管理订单、结算支付
  * 农户： 管理资产、管理订单
  * 中间环节： 包装商、仓库、物流
  * 金融： 管理贷款还款、风险


#### 结构说明

* basedocker: node以及npm dependencies 打包成Docker container，避免每次Docker运行都需要download dependencies
* chaincode: chaincode代码以及配套工具:
  * org define
  * channel data tool
  * chaincode source code
  * certificate files
  * docker config files
* config: 配置文档
* public: 前端web页面
* server: 后端服务代码
  * chaincode: chaincode tool for service
  * middleware: service middleware
  * model
  * service
  * server.js: 后端服务初始化入口
* test: 后端service单元测试代码
* pm2.sh: 如果不采用Docker部署，pm2部署也是可以
* app.js: 初始化backend service，连接chaincode

#### 运行说明
 * 如前文所说，这段代码历史比较悠久，不确定能否运行起来，因为相关依赖版本可能不对，请尽量按照相关版本来搞。
 * docker.sh: 用来下载相关的Docker镜像用的，主要是hyperledger。
 * chaincode目录： 该目录用来搭建起整个hyperledger几个Docker镜像的，具体命令请查阅docker-compose。
 * 前面如果都搭建起来的话，需要查看输出的log是否有错误。
 * 之后是搭建nodejs层，在 basedocker/nodeNnpm里面，这个只需要运行一次，主要是CHINA网络不稳定，会导致环境大概率下载失败
 * 以上是根据记忆写的，可能有些出入，大体方向肯定是没错的。

