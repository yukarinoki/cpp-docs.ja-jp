---
title: シンボルまたはシンボル名 (ID) の変更
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing
helpviewer_keywords:
- symbol names
- symbols [C++], names
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
ms.openlocfilehash: 98df98a2ed466066d9f0d32d6686e55e75280167
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487400"
---
# <a name="changing-a-symbol-or-symbol-name-id"></a>シンボルまたはシンボル名 (ID) の変更

リソースまたはリソース オブジェクトを新規作成すると、IDD_DIALOG1 などの既定のシンボル名が開発環境によって割り当てられます。 使用することができます、[プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)を既定のシンボル名を変更する、またはリソースに既に関連付けられている任意のシンボルの名前を変更します。

### <a name="to-change-a-resources-symbol-name"></a>リソースのシンボル名を変更するには

1. [リソース ビュー](../windows/resource-view-window.md)リソースを選択します。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. **プロパティ**ウィンドウで、新しいシンボル名を入力するか既存のシンボルの一覧から選択、 **ID**ボックス。

   新しいシンボル名を入力すると、値が自動的に割り当てられます。

使用することができます、[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)リソースに割り当てられていないシンボルの名前を変更します。 詳細については、次を参照してください。[未使用のシンボルを変更する](../windows/changing-unassigned-symbols.md)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[シンボル名の制限](../windows/symbol-name-restrictions.md)<br/>
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)