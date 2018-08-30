---
title: ショートカット メニューの作成 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- context menus, Menu Editor
- pop-up menus, creating
- menus, pop-up
- menus, creating
- shortcut menus, creating
- pop-up menus, displaying
ms.assetid: dff4dddf-2e8d-4c34-b755-90baae426b58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6b06fa02420b70538faa70b24137df634420dd8d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222645"
---
# <a name="creating-pop-up-menus"></a>ショートカット メニューの作成

[ポップアップ メニュー](../mfc/menus-mfc.md) には、頻繁に使用するコマンドが表示されます。 これらは状況依存となっていて、マウス ポインターの場所に応じて表示できます。 アプリケーションでポップアップ メニューを使用には、メニュー自体をビルドし、アプリケーション コードに接続する必要があります。

メニュー リソースをロードして使用するメニュー リソースを作成すると、アプリケーション コードが必要な[TrackPopupMenu](/windows/desktop/api/winuser/nf-winuser-trackpopupmenu)がメニューを表示します。 ユーザーがメニューの外部をクリックしてポップアップ メニューを閉じるか、コマンドをクリックすると、この関数に戻ります。 ユーザーがコマンドを選択した場合は、そのコマンドのメッセージが、ハンドルが渡されたウィンドウに送信されます。

### <a name="to-create-a-pop-up-menu"></a>ポップアップ メニューを作成するには

1. 空のタイトルで[メニューを作成](../windows/creating-a-menu.md) します ( **キャプション**は指定しません)。

2. [新しいメニューにメニュー コマンドを追加](../windows/adding-commands-to-a-menu.md)します。 最初のメニュー コマンド、空のメニュー タイトルの下に移動 (一時的なキャプションという`Type Here`)。 **キャプション** とその他の情報を入力します。

   ポップアップ メニューのその他のメニュー コマンドに対して、この手順を繰り返します。

3. メニュー リソースを保存します。

   > [!TIP]
   > ポップアップ メニューを表示する方法の詳細については、「 [ポップアップ メニューとしてのメニューの表示する](../windows/viewing-a-menu-as-a-pop-up-menu.md)」を参照してください。

## <a name="requirements"></a>要件

Win32

## <a name="see-also"></a>関連項目

[ショートカット メニューとアプリケーションの関連付け](../windows/connecting-a-pop-up-menu-to-your-application.md)  
[メニュー エディター](../windows/menu-editor.md)