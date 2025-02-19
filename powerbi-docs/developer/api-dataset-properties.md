---
title: Power BI 数据集属性
description: 了解 Power BI 数据集 API 的属性
author: rkarlin
ms.author: rkarlin
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-developer
ms.topic: conceptual
ms.date: 06/08/2018
ms.openlocfilehash: 508f304e2f5033c301db683e3b7557856fb3731b
ms.sourcegitcommit: 60dad5aa0d85db790553e537bf8ac34ee3289ba3
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "61386284"
---
# <a name="dataset-properties"></a>数据集属性

当前版本 1 的数据集 API 仅允许使用一个名称和一个表集合创建的数据集。 每个表可以具有一个名称和一个列集合。 每个列具有一个名称和数据类型。 我们主要通过对度量值和表格间的关系的支持来极大地扩展这些属性。 此版本受支持的属性的完整列表如下：

> [!IMPORTANT]
> 可从[数据集操作组](https://docs.microsoft.com/rest/api/power-bi/datasets)页进行访问。

## <a name="dataset"></a>数据集

名称  |类型  |说明  |只读  |必填

id | Guid | 系统范围内数据集的唯一标识符。 | True | False        
name | String | 用户定义的数据集名称。 | False | True        
tables     | Table[]        | 表的集合。        |  False       | False        
relationships     | Relationship[]        | 表之间的关系的集合。        | False        |  False  
defaultMode | String | 确定是推送还是流式处理数据集，还是同时执行两个操作，值为 "Push" 和"Streaming"。 | False | False


## <a name="table"></a>表

名称  |类型  |说明  |只读  |必填
---------|---------|---------|---------|---------

name | String | 用户定义的表名称。同时用作该表的标识符。 | False | True       
columns     |  column[]       |  列的集合。       | False        |  True       
measures     | measure[]        |  度量值的集合。       | False        |  False       
isHidden | Boolean | 如果为 True，表在客户端工具中为隐藏状态。 | False | False        


## <a name="column"></a>列

名称  |类型  |说明  |只读  |必填
---------|---------|---------|---------|---------

name | String | 用户定义的列名称。 | False | True       
dataType     |  String       |  受支持的 [EDM 数据类型](https://msdn.microsoft.com/library/ee382832.aspx)(#edm-数据类型) 和限制。 请参阅 [数据类型限制](#DataTypeRestrictions)(#数据类型限制)。      |  False       | True        
formatString | String | 一个描述如何在显示值时对值进行格式化的字符串。 若要了解字符串格式化的详细信息，请参阅 [FORMAT_STRING 内容](https://msdn.microsoft.com/library/ms146084.aspx)(#format_string-内容)。 | False | False        
sortByColumn | String | 同一个表中用于对当前列进行排序的另一个列的字符串名称。 | False | False       
dataCategory | String | 用于描述该列中数据的数据类别的字符串值。一些常见值包括：Address、City、Continent、Country、Image、ImageUrl、Latitude、Longitude、Organization、Place、PostalCode、StateOrProvince、WebUrl | False | False        

isHidden    |  Boolean       |  指示视图中是否隐藏该列的属性。 默认值为 False。       | False        | False        
summarizeBy     | String        |  列的默认聚合方法。 值包括：default、none、sum、min、max、count、average、distinctCount     |  False       | False

## <a name="measure"></a>度量值

名称  |类型  |说明  |只读  |必填
---------|---------|---------|---------|---------
name     | String        |  用户定义的度量值的名称。       |  False       | True        
expression     | String        | 有效的 DAX 表达式。        | False        |  True       

formatString     | String        |  描述如何在显示值时对值进行格式化。 若要了解字符串格式化的详细信息，请参阅 [FORMAT_STRING 内容](https://msdn.microsoft.com/library/ms146084.aspx)(#format_string-内容)。       | False        | False        

isHidden     | String        |  如果为 True，表将从客户端工具中隐藏。       |  False       | False       

## <a name="relationship"></a>关系

名称  |类型  |说明  |只读  |必填 
---------|---------|---------|---------|---------
name     | String        | 用户定义的关系的名称。 还可用作该关系的标识符。        | False       | True        
crossFilteringBehavior     | String        |    关系的筛选方向：OneDirection（默认）、BothDirections、Automatic       | False        | False        
fromTable     | String        | 外键表的名称。        | False        | True         
fromColumn    | String        | 外键列的名称。        | False        | True         
toTable    | String        | 主键表的名称。        | False        | True         
toColumn     | String        | 主键列的名称。        | False        | True        

<a name="DataTypeRestrictions"/>

## <a name="data-type-restrictions-applies-to-datatype-property"></a>数据类型限制（适用于 dataType 属性）

数据类型  |限制  
---------|---------
Int64     |   不允许使用 Int64.MaxValue 和 Int64.MinValue。      
Double     |  不允许使用 Double.MaxValue 和 Double.MinValue 值。 NaN 某些函数（例如 Min、Max）中不支持使用正无穷和负无穷。       
Boolean     |   True 或 False。
Datetime    |   在数据加载期间，我们将不足一天的值量化为 1/300 秒（3.33 毫秒）的整数倍。      

String | 目前允许每个字符串值最多包含 4000 个字符。

Decimal|精度 = 28，小数位数 = 4

## <a name="example"></a>示例
以下代码示例包括以下多个属性：

```json
{

  "name": "PushAdvanced",

  "tables": [

    {

      "name": "Date",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        }

      ]

    },

    {

      "name": "sales",

      "columns": [

        {

          "name": "Date",

          "dataType": "dateTime",

          "formatString": "dddd\\, mmmm d\\, yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "Sales",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ],

      "measures": [

        {

          "name": "percent to forecast",

          "expression": "SUM(sales[Sales])/SUM(forecast[forecast])",

          "formatString": "0.00 %;-0.00 %;0.00 %"

        }

      ]

    },

    {

      "name": "forecast",

      "columns": [

        {

          "name": "date",

          "dataType": "dateTime",

          "formatString": "m/d/yyyy",

          "summarizeBy": "none"

        },

        {

          "name": "forecast",

          "dataType": "int64",

          "formatString": "0",

          "summarizeBy": "sum"

        }

      ]

    }

  ],

  "relationships": [

    {

      "name": "2ea345ce-b147-436e-8ac2-9d3c4d82af8d",

      "fromTable": "sales",

      "fromColumn": "Date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    },

    {

      "name": "5d95f419-e589-4345-9581-6e70670b1bba",

      "fromTable": "forecast",

      "fromColumn": "date",

      "toTable": "Date",

      "toColumn": "Date",

      "crossFilteringBehavior": "bothDirections"

    }

  ]

}
```
