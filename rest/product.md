# 产品 API

### 获取产品列表

**API 定义：**
```bash
GET /dmp_api/products?_page=1&_limit=10 
```

**查询参数：**
```bash
GET /dmp_api/products?_page=1&_limit=10
```

### 创建一个产品

**API 定义：**
```bash
POST /dmp_api/products
```

**请求体：**

```json
{
  "productName": "共享单车",
  "description": "共享单车系列"
}
```

**字段说明：**

| 字段名         | 示例值   | 字段类型   | 是否必填  | 说明   |
| ----------- | ----- | ------ | ----- | ---- |
| productName | 共享单车 | String | true  | 产品名称 |
| description | 共享单车系列  | String | false | 产品描述   | 



**成功响应：**

```json
{
  "createAt": "2018-03-01 15:54:56",
  "description": "共享单车系列",
  "devices": [],
  "id": 5,
  "productID": "i9lb6X",
  "productName": "共享单车",
  "updateAt": null,
  "userID": 2
}
```

### 查看产品详情

**API 定义：**

```bash
/dmp_api/products/{product_id}
```

**成功响应：**

```bash
{
  "createAt": "2018-03-01 16:43:57",
  "createUser": "EMQ",
  "description": "共享单车",
  "deviceCount": 0,
  "devices": [],
  "id": 9,
  "productID": "Gq2kxM",
  "productName": "共享单车",
  "updateAt": null,
  "userID": 2
}
```

**字段说明：**

| 字段名         | 示例值                 | 字段类型   | 说明   |
| ----------- | ------------------- | ------ | ---- |
| createAt    | 2018-03-01 16:43:57 | Date | 创建日期      |
| createUser  | EMQ              | string | 创建用户名     |
| description | 共享单车                | String | 产品描述   |
| deviceCount | 0                   | number | 该产品下设备数量     |
| devices     |                     | object | 该产品下所有设备 ID     |
| id          | 9                   | number | 产品 ID     |
| productID   | Gq2kxM              | string | 产品识别码     |
| productName | 共享单车                | String | 产品名称 |
| updateAt    |                     | object | 更新时间     |
| userID      | 2                   | number | 创建者 ID    | 


### 编辑产品信息

**API 定义：**

```bash
PUT /dmp_api/products/{product_id}
```

**请求体：**

```json
{
  "description": "共享单车传感器",
  "productName": "共享单车"
}
```




**成功响应：**

```json
{
  "createAt": "2018-03-01 15:54:56",
  "description": "共享单车传感器",
  "devices": [],
  "id": 5,
  "productID": "i9lb6X",
  "productName": "共享单车",
  "updateAt": "2018-03-01 16:27:00",
  "userID": 2
}
``` 

### 删除产品

**API 定义：**
```bash
# 单个删除
/dmp_api/products?ids={product_id}

# 批量删除
/dmp_api/products?ids={product_id, product_id, product_id}
```
> 支出批量删除，多个 product_id 使用英文逗号分隔


**成功响应：**

```bash
HTTP Status Code 204
```
