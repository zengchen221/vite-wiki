---
sidebarDepth: 4
---

# Mintage
:::tip 维护者
[viteLiz](https://github.com/viteLiz)
:::

铸币内置合约，合约账户地址： `vite_00000000000000000000000000000000000000056ad6d26692`

**支持调用方式：**

|  JSON-RPC 2.0  | HTTP | IPC |Publish–subscribe |Websocket |
|:------------:|:-----------:|:-----:|:-----:|:-----:|
| &#x2713;|  &#x2713; |  &#x2713; |waiting| &#x2713; |

## mintage_getMintageData
获取铸币交易请求数据

- **Parameters**: 

`Object`
  1. `selfAddr`: `Address`  交易的发起方
  2. `height`: `uint64`  当前块高度
  3. `prevHash`: `Hash`  前一个账户块的哈希
  4. `snapshotHash`: `Hash`  当前块引用的快照块哈希
  5. `tokenName`:`string`  代币名称，1-40个字符，包含大小写字母、空格和下划线，不能有连续空格，不能以空格开头或结尾
  6. `tokenSymbol`: `string` 代币简称，1-10个字符，包含大小写字母、空格和下划线，不能有连续空格，不能以空格开头或结尾
  7. `totalSupply`: `big.int` 总发行量，不能超过2**256-1
  8. `decimals`: `uint8` 小数位数，10**decimals不能超过totalSupply


- **Returns**: 
	- `[]byte` Data

- **Example**:


::: demo


```json tab:Request
{  
   "jsonrpc":"2.0",
   "id":1,
   "method":"mintage_getMintageData",
   "params": [{
   	  "selfAddr":"vite_a5a7f08011c2f0e40ccd41b5b79afbfb818d565f566002d3c6",
   		"height":2,
   		"prevHash":"3a56babeb0a8140b12ac55e91d2e05c41f908ebe99767b0e4aa5cd7af22d6de7",
   		"snapshotHash":"3a56babeb0a8140b12ac55e91d2e05c41f908ebe99767b0e4aa5cd7af22d6de7",
   		"tokenName":"Test Token",
   		"tokenSymbol":"test",
   		"totalSupply":100000000000,
   		"decimals":6
   	}]
}
```

```json tab:Response
{  
   "jsonrpc":"2.0",
   "id":1,
   "result": "46d0ce8b000000000000000000000000000000000000000000003fd16552e1551a267f3200000000000000000000000000000000000000000000000000000000000000a000000000000000000000000000000000000000000000000000000000000000e0000000000000000000000000000000000000000000000000000000174876e8000000000000000000000000000000000000000000000000000000000000000006000000000000000000000000000000000000000000000000000000000000000a5465737420546f6b656e0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000047465737400000000000000000000000000000000000000000000000000000000"
}
```
:::

## mintage_getMintageCancelPledgeData
获取取回铸币抵押交易请求数据

- **Parameters**: 

  * `TokenId`: 取回铸币抵押的代币id

- **Returns**: 
	- `[]byte` Data

- **Example**:


::: demo


```json tab:Request
{  
   "jsonrpc":"2.0",
   "id":1,
   "method":"mintage_getMintageCancelPledgeData",
   "params":["tti_5649544520544f4b454e6e40"]
}
```

```json tab:Response
{  
   "jsonrpc":"2.0",
   "id":1,
   "result":  "9b9125f5000000000000000000000000000000000000000000005649544520544f4b454e"
}
```
:::
