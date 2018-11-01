---
title: シンボルの新規作成
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.creating
helpviewer_keywords:
- New Symbol dialog box [C++]
- symbols [C++], creating
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
ms.openlocfilehash: 9305f5bf409d5c0d4da227d2aadd3f16dc85945c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600113"
---
# <a name="creating-new-symbols"></a>シンボルの新規作成

新しいプロジェクトを開始するときは、必要なシンボル名を、シンボル名を割り当てるリソースを作成する前に決めておくと便利です。

### <a name="to-create-a-new-symbol-using-the-resource-symbols-dialog-box"></a>[リソース シンボル] ダイアログ ボックスを使用して新しいシンボルを作成するには

1. [リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)、選択**新規**します。

2. **名前**ボックスに、シンボル名を入力します。

3. 割り当てられたシンボル値を受け入れます。

   - または -

   **値**ボックスに、新しい値を入力します。

4. クリックして**OK**新しいシンボルをシンボルの一覧に追加します。

既に存在するシンボルの名前を入力すると、その名前のシンボルが既に定義されていることを示すメッセージ ボックスが表示されます。 複数の同じ名前のシンボルを定義することはできませんが、同じ数値を持つ異なるシンボルを定義することができます。 詳細については、次を参照してください。[シンボル名の制限](../windows/symbol-name-restrictions.md)と[シンボル値の制限](../windows/symbol-value-restrictions.md)します。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 リソースにアクセスする、マネージ プロジェクトにリソース ファイルを手動で追加するのには静的なリソースを表示して、リソースの割り当ては、プロパティに文字列です。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース シンボルの表示](../windows/viewing-resource-symbols.md)<br/>
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)