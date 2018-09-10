---
title: シンボルを変更する&#39;s 数値 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.value
dev_langs:
- C++
helpviewer_keywords:
- numeric values
- symbols [C++], numeric values
- numeric values, changing symbols
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eef16275bcd563a258347f8853a3c705594df99d
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318675"
---
# <a name="changing-a-symbol39s-numeric-value"></a>シンボルを変更する&#39;s 数値

1 つのリソースに関連付けられているシンボルを使用することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)シンボル値を変更します。 使用することができます、[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)リソースに割り当てられていないシンボルの値を変更します。 詳細については、次を参照してください。[未使用のシンボルを変更する](../windows/changing-unassigned-symbols.md)します。

### <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>1 つのリソースまたはオブジェクトに割り当てられているシンボル値を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)リソースを選択します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. **プロパティ**ウィンドウで、型、シンボル名の後に等号 (=)、整数の**ID**ボックスで、たとえば。

    ```
    IDC_EDITNAME=5100
    ```

新しい値は、次回のプロジェクトの保存時に、シンボル ヘッダー ファイルに格納されます。 検証後は、[ID] ボックスに等号と値は表示されず、シンボル名だけが表示されます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 リソースにアクセスする、マネージ プロジェクトにリソース ファイルを手動で追加するのには静的なリソースを表示して、リソースの割り当ては、プロパティに文字列です。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[シンボル値の制限](../windows/symbol-value-restrictions.md)  
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)