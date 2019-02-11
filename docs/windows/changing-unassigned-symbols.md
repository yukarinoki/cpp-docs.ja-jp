---
title: 変更または未使用のシンボルを削除します。
ms.date: 11/04/2016
f1_keywords:
- vc.editors.symbol.changing.unassigned
helpviewer_keywords:
- symbols [C++], unassigned
- Change Symbol dialog box [C++]
- unassigned symbols
- symbols [C++], deleting
ms.assetid: b6abee4a-3c24-4697-a166-fe6a86cad35f
ms.openlocfilehash: 47cc3d7a387092afe77fdbcf4bbdb6d085eeda25
ms.sourcegitcommit: 966e4466f10c93fc12faf33d28e03b39489423fc
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/11/2019
ms.locfileid: "55987015"
---
# <a name="changing-or-deleting-unassigned-symbols"></a>変更または未使用のシンボルを削除します。

[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)、編集またはリソースまたはオブジェクトに既に割り当てられていない既存のシンボルを削除することができます。

マネージ プロジェクトにリソースを追加する方法については、次を参照してください。 [Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="to-change-an-unassigned-symbol"></a>未使用のシンボルを変更するには

1. **名前**ボックスで未使用のシンボルを選択し、選択**変更**します。

1. シンボルの名前またはで用意されているボックス内の値を編集、**シンボルの変更** ダイアログ ボックス。

   > [!NOTE]
   > シンボルの変更を*は*リソースまたはオブジェクトに割り当てられている、リソース エディターを使用する必要がありますまたは**プロパティ**ウィンドウ。 詳細については、次を参照してください。[シンボルまたはシンボル名を変更する](../windows/changing-a-symbol-or-symbol-name-id.md)します。

## <a name="to-delete-an-unassigned-unused-symbol"></a>割り当てられていない (使用されていない) シンボルを削除するには

[リソース シンボル ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)、削除、および選択する記号を選択して**削除**します。

   > [!NOTE]
   > リソース ファイル内の未使用のシンボルを削除する前に、プログラム内の他の場所や、コンパイル時に含められるリソース ファイルで使用されていないことを確認してください。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース シンボルの表示](../windows/viewing-resource-symbols.md)<br/>
[シンボル名の制限](../windows/symbol-name-restrictions.md)<br/>
[シンボル値の制限](../windows/symbol-value-restrictions.md)<br/>
[定義済みシンボル ID](../windows/predefined-symbol-ids.md)