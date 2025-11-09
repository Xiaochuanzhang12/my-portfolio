# iquery数据字典：iquery数据库数据字典

本数据字典记录了iquery数据库中各张数据表的基本情况。

## 1.user_demographics数据表

- 基本解释

  ​		user_demographics数据表记录了电信用户的个人基本情况，主要涵盖客户基本生物属性，包括性别、年龄状况、是否结婚以及是否经济独立等。

- 数据来源

  ​	user_demographics数据集由一线业务人员人工采集记录，并且通过回访确认相关信息，数据集的准确性和可信度都非常高。

- 各字段说明

| Column Name | Description | Value Range | Value Explanation | Type |
|-------------|-------------|-------------|-------------------|------|
| customerID | 客户ID，user_demographics数据表主键 |              | 由数字和字母组成的 | VARCHAR(255) |
| gender | 用户的性别 | Female, Male | Female (女性), Male (男性) | VARCHAR(255) |
| SeniorCitizen | 是否为老人 | 0, 1 | 0 (不是), 1 (是) | INT |
| Partner | 用户是否有伴侣 | Yes, No | Yes (有), No (没有) | VARCHAR(255) |
| Dependents | 用户经济是否独立，往往用于判断用户是否已经成年 | No, Yes | Yes (有), No (没有) | VARCHAR(255) |

## 2.user_services数据表

- 基本解释

  ​        user_services数据表记录了每位用户订购电信服务的基本情况，截至目前，电信服务商提供了种类多样的服务，包括电话类服务和网络类服务等，本数据集表记录了每位用户订阅电信服务的基本情况。

- 数据来源

  ​		user_services数据表由后台系统自动创建生成，并未经过人工校验。

- 各字段说明

| Column Name | Description | Value Range | Value Explanation | Type |
|-------------|-------------|-------------|-------------------|------|
| customerID | 客户ID，user_services数据表主键 |  | 由数字和字母组成的 | VARCHAR(255) |
| PhoneService | 用户是否有电话服务 | No, Yes | Yes (有), No (没有) | VARCHAR(255) |
| MultipleLines | 用户是否开通了多条电话业务 | No phone service, No, Yes | Yes (有多条电话线业务), No (没有多条电话线业务), No phone service (没有电话服务) | VARCHAR(255) |
| InternetService | 用户的互联网服务类型 | DSL, Fiber optic, No | DSL (DSL), Fiber optic (光纤), No (没有) | VARCHAR(255) |
| OnlineSecurity | 是否开通网络安全服务 | No, Yes, No internet service | Yes（有）、No（无） or No internetservice（没有网路服务） | VARCHAR(255) |
| OnlineBackup | 是否开通在线备份服务 | Yes, No, No internet service | Yes（有）、No（无） or No internetservice（没有网路服务） | VARCHAR(255) |
| DeviceProtection | 是否开通设备保护服务 | No, Yes, No internet service | Yes（有）、No（无） or No internetservice（没有网路服务） | VARCHAR(255) |
| TechSupport | 是否开通技术支持业务 | No, Yes, No internet service | Yes（有）、No（无） or No internetservice（没有网路服务） | VARCHAR(255) |
| StreamingTV | 是否开通网络电视 | No, Yes, No internet service | Yes（有）、No（无） or No internetservice（没有网路服务） | VARCHAR(255) |
| StreamingMovies | 是否开通网络电影 | No, Yes, No internet service | Yes（有）、No（无） or No internetservice（没有网路服务） | VARCHAR(255) |

## 3.user_payments数据表

- 基本解释

  ​		user_payments数据表记录了每一位用户支付状况，既包括用户的支付方式和合同类型，同时也包含用户具体支付金额，包括月付金额和总金额等。

- 数据来源

  ​		user_payments数据表由后台自动记录生成，并未经过校验。

- 各字段说明

| Column Name | Description | Value Range | Value Explanation | Type |
|-------------|-------------|-------------|-------------------|------|
| customerID | 客户ID，user_payments数据表主键 |  | 由数字和字母组成的 | VARCHAR(255) |
| Contract | 合同类型 | Month-to-month, One year, Two year | Month-to-month (月付), One year (一年付), Two year (两年付) | VARCHAR(255) |
| PaperlessBilling | 是否无纸化账单 | Yes, No | Yes (是), No (否) | VARCHAR(255) |
| PaymentMethod | 支付方式 | Electronic check, Mailed check, Bank transfer (automatic), Credit card (automatic) | Electronic check (电子检查), Mailed check (邮寄支票), Bank transfer (automatic) (银行转账), Credit card (automatic) (信用卡) | VARCHAR(255) |
| MonthlyCharges | 月费用 |  | 用户平均每月支付费用 | FLOAT        |
| TotalCharges | 总费用 |  | 截至目前用户总消费金额 | VARCHAR(255) |

## 4.user_churn

- 基本解释

  ​		user_churn数据表记录了当前用户流失情况。

- 数据来源

  ​		user_churn数据表由后台自动创建并记录，当合同截至后但用户未续费，则判断该用户目前处于流失状态。

- 各字段说明

| Column Name | Description | Value Range | Value Explanation | Type |
|-------------|-------------|-------------|-------------------|------|
| customerID | 客户ID，user_churn数据表主键 |             | 由数字和字母组成的 | VARCHAR(255) |
| Churn | 用户是否流失 | No, Yes | Yes (是), No (否) | VARCHAR(255) |

