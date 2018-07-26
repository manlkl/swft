# RESTFUL API for SWFT    

## 开始使用    

##### 一种软件架构风格、设计风格，而不是标准，只是提供了一组设计原则和约束条件。它主要用于客户端和服务器交互类的软件。基于这个风格设计的软件可以更简洁，更有层次，更易于实现缓存等机制。

RESTful 简称REST，即Representational State Transfer的缩写，是目前最流行的一种互联网软件架构。它结构清晰、符合标准、易于理解、扩展方便，正得到越来越多网站的采用。其优点如下：    
- 在RESTful架构中，每一个URL代表一种资源；    
- 客户端和服务器之间，传递这种资源的某种表现层；    
- 客户端通过四个HTTP指令，对服务器端资源进行操作，实现“表现层状态转化”。   

建议开发者使用REST API进行币币交易或者资产提现等操作。    
    
## 请求交互    

REST访问的根URL：`https://www.swft.pro/api/v1`     
访问时需要科学上网
所有请求基于Https协议，请求头信息中contentType需要统一设置为：`application/x-www-form-urlencoded`    
	
请求交互说明    
1. 请求参数：根据接口请求参数规定进行参数封装。    
2. 提交请求参数：将封装好的请求参数通过POST 或 GET 方式提交至服务器。    
3. 服务器响应：服务器首先对用户请求数据进行参数安全校验，通过校验后根据业务逻辑将响应数据以JSON格式返回给用户。    
4. 数据处理：对服务器响应数据进行处理。 

## ETH(以太坊) API参考  

### 获取以太坊 新地址 API 

获取以太坊新地址  

1. Post /etherApi/v1/getNewAddress    获取以太坊新地址

URL `https://www.swft.pro/etherApi/v1/getNewAddress`	

示例	

```
# Request
POST https://www.swft.pro/etherApi/v1/getNewAddress
-- request Body
{
    "serialNo": "swft000000001", 
    "timeStamp": "1516353333786", 
    "sign": "FB627E0180C3E4B41553B313125ACAAA", 
    "channelNo": "SWFTDEV00001",
    "label": "password"
}

# Response
{
	"data":"0x0000000000000000000000000000000000000000",
	"resCode":"888",
	"resMsg":"接口调用成功！"
}
```

返回值说明	

```
data: 	 调用接口返回的数据
resCode: 调用接口返回的状态码
resMsg:	 调用接口返回的消息信息
```

请求参数	

|参数名|	参数类型|	必填|	描述|
| :-----    | :-----   | :-----    | :-----   |
|serialNo|String|是|请求序列号|
|timeStamp|String|是|时间戳|
|sign|String|是|指纹密码|
|channelNo|String|是|渠道号|
|label|String|是|以太坊地址的pwd|

2. Post /etherapi/v1/getBalanceByAddress   获取以太坊地址的余额

URL `https://www.swft.pro/etherapi/v1/getBalanceByAddress`	

示例	

```
# Request
POST https://www.swft.pro/etherapi/v1/getBalanceByAddress
-- request Body
{
    "serialNo": "swft000000001", 
    "timeStamp": "1516353333786", 
    "sign": "FB627E0180C3E4B41553B313125ACAAA", 
    "channelNo": "SWFTDEV00001",
    "address": "0x0000000000000000000000000000000000000000"
}

# Response
{
	"data":"1234.8888",
	"resCode":"888",
	"resMsg":"接口调用成功！"
}
```

返回值说明	

```
data: 	 调用接口返回的数据
resCode: 调用接口返回的状态码
resMsg:	 调用接口返回的消息信息
```

请求参数	

|参数名|	参数类型|	必填|	描述|
| :-----    | :-----   | :-----    | :-----   |
|serialNo|String|是|请求序列号|
|timeStamp|String|是|时间戳|
|sign|String|是|指纹密码|
|channelNo|String|是|渠道号|
|address|String|是|以太坊地址|

3. Post /etherapi/v1/sendTransaction   发币交易

URL `https://www.swft.pro/etherapi/v1/sendTransaction`	

示例	

```
# Request
POST https://www.swft.pro/etherapi/v1/sendTransaction
-- request Body
{
    "serialNo": "swft000000001", 
    "timeStamp": "1516353333786", 
    "sign": "FB627E0180C3E4B41553B313125ACAAA", 
    "channelNo": "SWFTDEV00001",
    "sourceaddress": "0x0000000000000000000000000000000000000000",
    "targetaddress": "0x0000000000000000000000000000000000000000",
    "label": "source address pwd"
}

# Response
{
	"data":"0x724b3430358a0aa0c07efa56d9e02d10569e893714bfc810c60fba0383abe685",
	"resCode":"888",
	"resMsg":"接口调用成功！"
}
```

返回值说明	

```
data: 	 调用接口返回的数据
resCode: 调用接口返回的状态码
resMsg:	 调用接口返回的消息信息
```

请求参数	

|参数名|	参数类型|	必填|	描述|
| :-----    | :-----   | :-----    | :-----   |
|serialNo|String|是|请求序列号|
|timeStamp|String|是|时间戳|
|sign|String|是|指纹密码|
|channelNo|String|是|渠道号|
|sourceaddress|String|是|发送方以太坊地址|
|targetaddress|String|是|接收方以太坊地址|
|label|String|是|源地址pwd|

4. POST /etherapi/v1/getTransactionBlockNumber    获取以太坊交易成功确认数

URL `https://www.swft.pro/etherapi/v1/getTransactionBlockNumber`	

示例	

```
# Request
POST https://www.swft.pro/etherapi/v1/getTransactionBlockNumber
-- request Body
{
    "serialNo": "swft000000001", 
    "timeStamp": "1516353333786", 
    "sign": "FB627E0180C3E4B41553B313125ACAAA", 
    "channelNo": "SWFTDEV00001",
    "trxid": "0x724b3430358a0aa0c07efa56d9e02d10569e893714bf"
}

# Response
{
	"data":"345",
	"resCode":"888",
	"resMsg":"接口调用成功！"
}
```

返回值说明	

```
data: 	 调用接口返回的数据
resCode: 调用接口返回的状态码
resMsg:	 调用接口返回的消息信息
```

请求参数	

|参数名|	参数类型|	必填|	描述|
| :-----    | :-----   | :-----    | :-----   |
|serialNo|String|是|请求序列号|
|timeStamp|String|是|时间戳|
|sign|String|是|指纹密码|
|channelNo|String|是|渠道号|
|trxid|String|是|以太坊交易id|

### ERC20(智能合约) API 

--用于 ERC20 token 币币交易  

1. POST /erc20api/v1/getBalanceByAddress    获取用户信息

URL `https://www.swft.pro/erc20api/v1/getBalanceByAddress`

示例	

```
# Request
POST https://www.swft.pro/erc20api/v1/getBalanceByAddress
-- request Body
{
    "serialNo": "swft000000001", 
    "timeStamp": "1516353333786", 
    "sign": "FB627E0180C3E4B41553B313125ACAAA", 
    "channelNo": "SWFTDEV00001",
    "address": "0x724b3430358a0aa0c07efa56d9e02d10569e893714bf",
    "token": "SWFTC",
}
# Response
{
	"data":"345.2",
	"resCode":"888",
	"resMsg":"接口调用成功！"
}
```

返回值说明	

```
data: 	 调用接口返回的数据
resCode: 调用接口返回的状态码
resMsg:	 调用接口返回的消息信息
```

请求参数	

|参数名|	参数类型|	必填|	描述|
| :-----    | :-----   | :-----    | :-----   |
|serialNo|String|是|请求序列号|
|timeStamp|String|是|时间戳|
|sign|String|是|指纹密码|
|channelNo|String|是|渠道号|
|address|String|是|以太坊Erc20查询地址|
|token|String|是|Erc20代币名称|

2. POST /erc20api/v1/transaction    发币交易

URL `https://www.swft.pro/erc20api/v1/transaction`	访问频率 20次/2秒	

示例	

```
# Request
POST https://www.swft.pro/erc20api/v1/transaction
-- request Body
{
    "serialNo": "swft000000001", 
    "timeStamp": "1516353333786", 
    "sign": "FB627E0180C3E4B41553B313125ACAAA", 
    "channelNo": "SWFTDEV00001",
    "sourceaddress": "0x724b3430358a0aa0c07efa56d9e02d10569e893714bf",
    "targetaddress": "0x724b3430358a0aa0c07efa56d9e02d105dsafasdeeww",
    "amount": "300",
    "label": "sourceaddress pwd",
    "token": "SWFTC",
}
# Response
{
	"data":"0x724b3430358a0aa0c07efa56d9e02d10569e893714bfc810c60fba0383abe685",
	"resCode":"888",
	"resMsg":"接口调用成功！"
}
```

返回值说明	

```
data: 	 调用接口返回的数据
resCode: 调用接口返回的状态码
resMsg:	 调用接口返回的消息信息
```

请求参数	

|参数名|	参数类型|	必填|	描述|
| :-----    | :-----   | :-----    | :-----   |
|serialNo|String|是|请求序列号|
|timeStamp|String|是|时间戳|
|sign|String|是|指纹密码|
|channelNo|String|是|渠道号|
|sourceaddress|String|是|以太坊Erc20发送地址|
|targetaddress|String|是|以太坊Erc20接收地址|
|amount|String|是|发送代币的数量|
|label|String|是|发送地址密码|
|token|String|是|Erc20代币名称|
