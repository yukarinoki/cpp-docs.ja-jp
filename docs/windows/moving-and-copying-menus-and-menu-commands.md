---
title: 移動またはコピー メニューとメニュー コマンド (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- commands [C++], copying on menus
- menu items, moving
- commands [C++], moving on menus
- menu items, copying
ms.assetid: 1d8df535-9922-4579-a9c2-37aeac1856eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b12d9d09cd2e4b35c458c2acbefa48eee8c4b0a9
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/10/2018
ms.locfileid: "44312758"
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

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 リソースにアクセスする、マネージ プロジェクトにリソース ファイルを手動で追加するのには静的なリソースを表示して、リソースの割り当ては、プロパティに文字列です。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[メニュー エディター](../windows/menu-editor.md)