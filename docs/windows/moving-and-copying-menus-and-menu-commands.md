---
title: 移動またはコピー メニューとメニュー コマンド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands, copying on menus
- menu items, moving
- commands, moving on menus
- menu items, copying
ms.assetid: 1d8df535-9922-4579-a9c2-37aeac1856eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cc95eef2c3cca678ae291846c2ebe0e5c1e80997
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42609083"
---
# <a name="moving-and-copying-menus-and-menu-commands"></a>メニューとメニュー コマンドの移動およびコピー

ドラッグ アンド ドロップ操作またはショートカット メニュー (右クリック メニュー) のコマンドを使用して、メニューとメニュー コマンドを移動またはコピーすることができます。

### <a name="to-move-or-copy-menus-or-menu-commands-using-the-drag-and-drop-method"></a>ドラッグ アンド ドロップ操作を使用してメニューやメニュー コマンドを移動またはコピーするには

1. 移動する項目を次の場所にドラッグまたはコピーします。

   - 現在のメニュー上の新しい場所。

   - 別のメニュー (他のメニューに移動するには、そのメニューにマウス ポインターをドラッグします)。

2. 挿入ガイドで目的の位置が示されたら、メニュー コマンドをドロップします。

### <a name="to-move-or-copy-menus-or-menu-commands-using-shortcut-menu-commands"></a>ショートカット メニューのコマンドを使用してメニューやメニュー コマンドを移動またはコピーするには

1. 1 つ以上のメニューまたはメニュー コマンドを右クリックします。

2. ショートカット メニューの **[切り取り]** (移動する場合) または **[コピー]** を選択します。

3. 項目を別のメニュー リソース ファイルまたはリソース スクリプト ファイルに移動する場合は、 [そのファイルを別のウィンドウで開きます](/visualstudio/ide/customizing-window-layouts-in-visual-studio)。

4. メニューやメニュー コマンドを移動またはコピーする位置を選択します。

5. ショートカット メニューの **[貼り付け]** を選択します。 移動またはコピーする項目は、選択した項目の前に配置されます。

   > [!NOTE]
   > ドラッグでコピーした項目を別のメニュー ウィンドウの別のメニューに貼り付けることもできます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 」を参照してください。マネージド プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、リソース文字列をプロパティに割り当てる方法については、「 [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6)を選択します。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[メニュー エディター](../windows/menu-editor.md)