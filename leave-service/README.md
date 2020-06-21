# DDD 示例程序

### 代码结构说明
* `application` 应用层
* `domain` 领域层
* `infrastructure` 基础设施层
* `interfaces` 接口层（Controller层）

#### `application` 应用层
* `service` 应用服务
#### `domain` 领域层
* `leave` 请假聚合
* `person` 人员聚合
* `rule` 审批规则聚合
#### `infrastructure` 基础设施层
* `client` 其他微服务的应用服务
* `common` 公共工具包
* `exception` 异常包
#### `interfaces` 接口层（Controller层）
* `assembler` 转换服务包
* `dto` 传输数据载体
* `facade` Controller

### 调用逻辑说明
* 应用服务负责编排领域服务`domain.*.service`
* 领域服务负责处理当前聚合内多个实体的业务逻辑
* 领域服务产生领域事件（如果多个事件则使用列表返回），在应用层订阅并调用领域服务对事件进行处理

