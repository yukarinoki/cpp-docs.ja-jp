---
title: レコード ビューのユーザー インターフェイスの更新 (MFC データ アクセス)
ms.date: 11/04/2016
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
ms.openlocfilehash: 9bfb907d21c928c605b304c595acb834d0046e35
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209054"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>レコード ビューのユーザー インターフェイスの更新 (MFC データ アクセス)

`CRecordView` は、ナビゲーションコマンドの既定のユーザーインターフェイス更新ハンドラーを提供します。 これらのハンドラーにより、ユーザー インターフェイス オブジェクト (メニュー項目とツール バー ボタン) の有効/無効が自動的に切り替えられます。 アプリケーションウィザードには標準のメニューが用意されています。 [ドッキング可能な**ツールバー** ] オプションを選択した場合は、コマンドの一連のツールバーボタンが表示されます。 `CRecordView` を使用してレコード ビュー クラスを作成する場合は、同じユーザー インターフェイス オブジェクトをアプリケーションに追加することが必要になることがあります。

### <a name="to-create-menu-resources-with-the-menu-editor"></a>エディター メニューを使用してメニュー リソースを作成するには

1. [メニューエディター](../windows/menu-editor.md)の使用方法については、同じ4つのコマンドを使用して独自のメニューを作成する方法に関する情報を参照してください。

#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>グラフィックス エディターを使用してツール バー ボタンを作成するには

1. ツールバー[エディター](../windows/toolbar-editor.md)の使用に関する情報を参照するには、ツールバーリソースを編集して、レコードナビゲーションコマンドのツールバーボタンを追加します。

## <a name="see-also"></a>参照

[レコードビューでのナビゲーションのサポート](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[レコードビューの使用](../data/using-a-record-view-mfc-data-access.md)
