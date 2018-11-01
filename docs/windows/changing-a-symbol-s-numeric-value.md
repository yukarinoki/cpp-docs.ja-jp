---
title: シンボルを変更する&#39;s 数値
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing.value
helpviewer_keywords:
- numeric values
- symbols [C++], numeric values
- numeric values, changing symbols
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
ms.openlocfilehash: 9013ce886b1e596a858321b32249d885d03015ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629841"
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

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[シンボル値の制限](../windows/symbol-value-restrictions.md)<br/>
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)