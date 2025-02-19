---
title: 查找已登录的 Power BI 用户
description: 如果你是租户管理员，想查看已登录 Power BI 的用户，则可以使用 Azure Active Directory 访问和使用情况报告进行查看。
author: mgblythe
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-admin
ms.topic: conceptual
ms.date: 04/23/2019
ms.author: mblythe
LocalizationGroup: Administration
ms.openlocfilehash: 7149d8601aa7a834f91a8d98f3a7a9deac7bf43b
ms.sourcegitcommit: 762857c8ca09ce222cc3f8b006fa1b65d11e4ace
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2019
ms.locfileid: "66721340"
---
# <a name="find-power-bi-users-that-have-signed-in"></a>查找已登录的 Power BI 用户

如果你是租户管理员，并想要确定已登录 Power BI 的用户，请查看 [Azure Active Directory 访问和使用情况报告](/azure/active-directory/reports-monitoring/concept-sign-ins)了解相关信息。

> [!NOTE]
> “登录”报表提供了有用的信息，但它并未标识每个用户拥有的许可证类型  。 请使用 Microsoft 365 管理中心查看许可证。

## <a name="requirements"></a>要求

任何用户（包括非管理员）都可以查看自己的登录活动报告，但必须符合以下要求，才能查看所有用户的报告。

* 租户必须将 Azure Active Directory Premium 许可证与其关联。

* 必须属于以下角色之一：全局管理员、安全管理员或安全读取者。

## <a name="use-the-azure-portal-to-view-sign-ins"></a>使用 Azure 门户查看登录活动

若要查看登录活动，请按以下步骤操作。

1. 在“Azure 门户”  中，选择“Azure Active Directory”  。

1. 在“监视”  下，选择“登录活动”  。
   
    ![Azure UI 的屏幕截图，其中突出显示了“Azure Active Directory”和“登录”选项。](media/service-admin-access-usage/azure-portal-sign-ins.png)

1. 按“Microsoft Power BI”  或“Power BI Gateway”  筛选应用，再选择“应用”  。

    “Microsoft Power BI”筛选出与服务相关的登录活动，而“Power BI Gateway”则筛选出本地数据网关专属登录活动   。
   
    ![登录筛选器的屏幕截图，突出显示“应用程序”字段。](media/service-admin-access-usage/sign-in-filter.png)

## <a name="export-the-data"></a>导出数据

你可以以两种格式之一[下载登录报表](/azure/active-directory/reports-monitoring/quickstart-download-sign-in-report)：CSV 文件或 JSON 文件。

![“下载”按钮的屏幕截图。](media/service-admin-access-usage/download-sign-in-data-csv.png)

在“登录”报告的顶部，选择“下载”，然后选择以下选项之一   ：

* **XSV**：下载当前已筛选数据的 CSV 文件。

* **JSON**：下载当前已筛选数据的 JSON 文件。

## <a name="data-retention"></a>数据保留期

与登录活动相关的数据最长可保留 30 天。 有关详细信息，请参阅 [Azure Active Directory 报表保留策略](/azure/active-directory/reports-monitoring/reference-reports-data-retention)。

## <a name="next-steps"></a>后续步骤

[在组织内使用审核](service-admin-auditing.md)

更多问题？ [尝试咨询 Power BI 社区](https://community.powerbi.com/)