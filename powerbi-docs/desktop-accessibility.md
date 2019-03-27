---
title: Power BI Desktop 报表中的辅助功能
description: 用于创建可访问 Power BI Desktop 报表的功能和建议
author: davidiseminger
manager: kfile
ms.reviewer: ''
ms.service: powerbi
ms.subservice: powerbi-desktop
ms.topic: conceptual
ms.date: 01/11/2019
ms.author: davidi
LocalizationGroup: Create reports
ms.openlocfilehash: e3dd7d9120b524dd09d6f0d60764385185210d83
ms.sourcegitcommit: 89e9875e87b8114abecff6ae6cdc0146df40c82a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "58306288"
---
# <a name="accessibility-in-power-bi-desktop-reports"></a>Power BI Desktop 报表中的辅助功能
Power BI 具有使残疾人士能够更轻松地使用 Power BI 报表并与之进行交互的功能。 这些功能包括通过键盘或屏幕阅读器使用报表、通过按 Tab 键将焦点移动到页面中的各个对象以及在可视化效果中方便地使用标记。

![在折线图和分区图中使用不同的标记来改善辅助功能](media/desktop-accessibility/accessibility_01.png)

## <a name="consuming-a-power-bi-desktop-report-with-a-keyboard-or-screen-reader"></a>通过键盘或屏幕阅读器使用 Power BI Desktop 报表
从 2017 年 9 月发行版 Power BI Desktop 开始，可以按 ? 键显示一个窗口，其中介绍了中可在 Power BI Desktop 中使用的辅助功能键盘快捷方式。

![在 Power BI Desktop 中按 ? 键可显示辅助功能键盘快捷方式](media/desktop-accessibility/accessibility_03.png)

借助辅助功能的增强功能，可以使用以下方法通过键盘或屏幕阅读器使用 Power BI 报表：

查看报表时，通常应关闭扫描模式。

可以使用 Ctrl+F6 在报表页选项卡或在给定的报表页中的对象之间切换焦点。

* 当焦点位于报表页选项卡上时，使用 Tab 或箭头键将焦点从一个报表页移到下一个报表页。 无论当前是否被选中，屏幕阅读器都会读出报表页的标题。 若要加载当前焦点所在的报表页，使用 Enter 或空格键。
* 当焦点位于已加载的报表页上时，使用 Tab 键将焦点转移到页面上的每个对象，其中包括所有文本框、图像、形状和图表。 屏幕阅读器可读取对象类型、对象标题（如果有）和对象说明（如果报表作者已提供）。 

在视觉对象之间导航时，可按 Alt+Shift+F10 将焦点移到该视觉对象标头，其中包括排序、导出图表背后的数据和焦点模式等多种选项。 

![在 Power BI Desktop 中按 Alt+Shift+F10 可将焦点移到该视觉对象标头](media/desktop-accessibility/accessibility_08.png)

按 Alt+Shift+F11 可以访问“显示数据”窗口。 这使用户能够使用通常在屏幕阅读器中使用的相同键盘快捷方式来了解 HTML 表中的视觉对象中使用的数据。 

![在 Power BI Desktop 中按 Alt+Shift+F11 可访问视觉对象的“查看数据”窗口](media/desktop-accessibility/accessibility_04.png)

> [!NOTE]
> 仅可在屏幕阅读器中通过此键盘快捷方式访问“显示数据”功能。 如果通过视觉对象标头中的选项打开“显示数据”，屏幕阅读器将无法访问此功能。 使用“显示数据”时，请启用扫描模式以利用屏幕阅读器提供的所有热键。

自 2018 年 7 月发布“Power BI Desktop”以来，切片器还具有内置的辅助功能。 选择切片器时，若要调整切片器的值，使用 CTRL+向右键（控制键加向右键）可移动切片器内的各种控件。 例如，最初按 CTRL+向右键时，焦点位于橡皮擦上，按下空格键等同于单击橡皮擦按钮，这样便可擦除切片器上的所有值。 

可以通过按 TAB 键移动切片器中的控件。 位于橡皮擦上时，按 TAB 键移动到下拉按钮。 按另一个 TAB 则移动到第一个切片器值（如果切片器有多个值，如一个范围）。 

![在 Power BI Desktop 中按 CTRL+（向右键）可调整切片器中的要素或值，按 SPACE 可选择元素并调整其值](media/desktop-accessibility/accessibility_07.png)

这些附加辅助功能的创建目的是使用户能够通过屏幕阅读器和键盘导航充分利用 Power BI 报表。

## <a name="tips-for-creating-accessible-reports"></a>创建可访问报表的提示
以下提示可帮助你创建更易于访问的 Power BI Desktop 报表。

### <a name="general-tips-for-accessible-reports"></a>有关可访问的报表的一般提示

* 对于“行”、“区域”、“组合图”、“散点图”和“气泡”视觉对象，请启用标记，并对每行使用不同的标记形状。
  
  * 若要启用“标记”，可在“可视化效果”窗格中选择“格式”部分，展开“形状”部分，然后向下滚动查找“标记”切换，并将其切换为“开”。
  * 然后，从“形状”部分中的下拉列表框中选择每行（如果使用区域图表，则为区域）的名称。 在下拉列表下方，可以调整用于所选行的标记的许多方面，包括其形状、颜色和大小。
  
  ![在折线图和分区图中使用不同的标记来改善辅助功能](media/desktop-accessibility/accessibility_01.png)
  
  * 对每行使用不同的标记形状可使报表使用者更容易区分行（或区域）。
* 作为上一个项目符号的后续内容，不要依赖颜色传达信息。 除了在折线图和散点图上使用形状外，不要依赖条件格式在表和矩阵中提供见解。 
* 为报表上的每个视觉对象选择有意图的排序顺序。 当屏幕阅读器用户在图表背后的数据中导航时，它会选取与该视觉对象相同的排序顺序。
* 从主题库中选择一个高对比度、适合色盲人士的主题，然后使用[**主题**预览功能](desktop-report-themes.md)将其导入。
* 为报表上的每个对象提供替换文字。 这可确保报表使用者了解你想通过视觉对象表达的内容，即使他们看不见视觉对象、图像、形状或文本框。 在“可视化效果”窗格中选中对象（例如视觉对象、形状等），选择“格式”部分，展开“常规”，然后滚动到底部并填写“替换文字”文本框，可为 Power BI Desktop 报表上的任何对象提供“替换文字”。
  
  ![可在“可视化效果”>“格式”>“常规”>“替换文字”框中为报表中的任何对象添加替换文字](media/desktop-accessibility/accessibility_02.png)
* 请确保报表在文本和任意背景颜色之间有足够的对比度。 可以使用 [Colour Contrast Analyser](https://developer.paciellogroup.com/resources/contrastanalyser/)（颜色对比度分析程序）等多种工具检查报表颜色。 
* 使用易于阅读的文本大小和字体。 文本太小或难以阅读的字体对辅助功能没有任何帮助。
* 包括所有视觉对象中的标题、轴标签和数据标签。
* 为所有报表页使用有意义的标题。
* 尽可能避免报表中出现装饰形状和图像，因为它们将包含在报表的 Tab 键顺序中。 如果需要在报表中添加修饰对象，请更新对象的替换文字，以便屏幕阅读器用户知道它只用于修饰。

### <a name="arranging-items-in-field-buckets"></a>排列“字段”存储桶中的项
从 Power BI Desktop 的 2018 年 10 月版本开始，“字段”也可以使用键盘导航和与屏幕阅读器进行交互。 

要改进使用屏幕阅读器创建报表的过程，可使用上下文菜单，在“字段”列表的井中向上或向下移动字段，或将字段移动到其他井中（如“图例”、“值”或其他）。

![借助“字段”井中的“上下文”菜单，可向上、向下或向其他区域移动字段](media/desktop-accessibility/accessibility_09.png)

## <a name="high-contrast-support-for-reports"></a>报表的高对比度支持

使用 Windows 中的高对比度模式时，所选设置和调色板也会应用到 Power BI Desktop 的报表中。 

![Windows 高对比度设置](media/desktop-accessibility/accessibility_05.png)

Power BI Desktop 自动检测 Windows 中使用的高对比度主题，并将这些设置应用到报表。 报表发布到 Power BI 服务或其他位置时，这些高对比度颜色也会跟随报表。

![Windows 高对比度设置](media/desktop-accessibility/accessibility_05b.png)

Power BI 服务还尝试检测 Windows 选择的高对比度设置，但该检测的有效性和准确性取决于用于 Power BI 服务的浏览器。 如果要在 Power BI 服务中手动设置主题，可选择“视图”>“高对比度颜色”，然后选择要应用于报表的主题。

![在 Power BI 服务中设置高对比度](media/desktop-accessibility/accessibility_06.png)

请注意：在 Power BI Desktop 中，“可视化效果”和“字段”字段等区域不反映 Windows 高对比度配色方案的选择。


## <a name="considerations-and-limitations"></a>注意事项和限制
辅助功能存在一些已知问题和限制，如以下列表所述：

* 通过 Power BI Desktop 使用屏幕阅读器时，如果在 Power BI Desktop 中打开任何文件前打开所选屏幕阅读器，则将获得最佳体验。
* 如果使用讲述人，以 HTML 表形式导航“显示数据”有一些相关限制。

## <a name="keyboard-shortcuts"></a>键盘快捷方式
键盘快捷方式有助于使用键盘在 Power BI 报表中移动。 下表介绍了 Power BI 报表中可用的快捷方式。 除了在 Power BI Desktop 中使用这些键盘快捷方式以外，还可以在以下体验中使用这些快捷方式：

* “问答资源管理器”对话框
* “入门指南”对话框
* “文件”菜单和“关于”对话框
* 警告栏
* “文件还原”对话框
* “哭脸”对话框

在我们持续努力提升可访问性的情况下，以前的体验列表也支持屏幕阅读器和高对比度设置。


### <a name="frequently-used-shortcuts"></a>常用快捷方式
| 如何执行此操作           | 操作方法                |
| :------------------- | :------------------- |
| 在分区间移动焦点  | Ctrl + F6 |
| 在分区中向前移动焦点 | Tab         |
| 在分区中向后移动焦点 | Shift + Tab |
| 选择或取消选择对象 | Enter 或空格键 |
| 多重选择对象 | Ctrl + 空格键 |

### <a name="on-visual"></a>启用视觉对象
| 如何执行此操作           | 操作方法                |
| :------------------- | :------------------- |
| 将焦点移动到视觉对象菜单 | Alt + Shift + F10 |
| 显示数据 | Alt + Shift +F11  |
| 输入一个视觉对象 | Ctrl + 向右键 |
| 输入一层 | 输入 |
| 退出一层或视觉对象 | Esc |
| 选中或取消选中数据点 | Enter 或空格键 |
| 多选 | Ctrl + Enter 或 Ctrl + 空格键 |
| 右键单击 | <ul><li>Windows 键盘：Windows 上下文键 + F10。  Windows 上下文键位于左 Alt 键和向左键之间</li><li>其他键盘：Shift + F10</li></ul> |
| 清除选定内容 | Ctrl + Shift + C |

### <a name="pane-navigation"></a>窗格导航
| 如何执行此操作           | 操作方法                |
| :------------------- | :------------------- |
| 多选 | Ctrl + 空格键 |
| 折叠单个表 | 左箭头键 |
| 展开单个表 | 右箭头键 |
| 折叠所有表 | Alt + Shift + 1 |
| 展开所有表 | Alt + Shift + 9 |
| 打开上下文菜单 | <ul><li>Windows 键盘：Windows 上下文键 + F10。  Windows 上下文键位于左 Alt 键和向左键之间</li><li>其他键盘：Shift + F10</li></ul> |

### <a name="slicer"></a>切片器
| 如何执行此操作           | 操作方法                |
| :------------------- | :------------------- |
| 与切片器进行交互 | Ctrl + 向右键 |

### <a name="selection-pane"></a>“选择”窗格
| 如何执行此操作           | 操作方法                |
| :------------------- | :------------------- |
| 激活“选择”窗格 | F6 |
| 在分层中向上移动对象 | Ctrl + Shift + F |
| 在分层中向下移动对象 | Ctrl + Shift + B |
| 隐藏/显示（切换）对象 | Ctrl + Shift + S |

### <a name="dax-editor"></a>DAX 编辑器
| 如何执行此操作           | 操作方法                |
| :------------------- | :------------------- |
| 向上/向下移动行 | Alt + 向上键/向下键 |
| 向上/向下复制行 | Shift + Alt + 向上键/向下键 |
| 在下方插入行 | Ctrl + Enter |
| 在上方插入行 | Ctrl + Shift + Enter |
| 跳转到匹配的括号 | Ctrl + Shift + \ |
| 缩进/突出行 | Ctrl + ] / [ |
| 插入光标 | Alt + 单击 |
| 选择当前行 | Ctrl + I |
| 选择当前所选内容的所有匹配项 | Ctrl + Shift + L |
| 选择当前词语的所有匹配项 | Ctrl + F2 |

### <a name="enter-data"></a>输入数据
| 如何执行此操作           | 操作方法                |
| :------------------- | :------------------- |
| 退出可编辑网格 | Ctrl + Tab 键 |


## <a name="next-steps"></a>后续步骤
* [在 Power BI Desktop 中使用报表主题（预览版）](desktop-report-themes.md)

