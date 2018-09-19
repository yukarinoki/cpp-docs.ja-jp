---
title: レコード ビュー (MFC データ アクセス) のユーザー インターフェイスの更新 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user interfaces, updating
- menus, updating as context changes
- record views, user interface
ms.assetid: 2c7914b6-2dc3-40c3-b2f2-8371da2a4063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 43f5d1017b3f89474e9dd7eebce0cf71c8c8c448
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086877"
---
# <a name="user-interface-updating-for-record-views--mfc-data-access"></a>レコード ビューのユーザー インターフェイスの更新 (MFC データ アクセス)

`CRecordView` 移動コマンド用の既定のユーザー インターフェイス更新ハンドラーを提供します。 これらのハンドラーにより、ユーザー インターフェイス オブジェクト (メニュー項目とツール バー ボタン) の有効/無効が自動的に切り替えられます。 アプリケーション ウィザードは、標準のメニューを提供し、選択した場合、**ドッキング可能ツールバー**オプション、コマンドのツール バー ボタンのセット。 `CRecordView` を使用してレコード ビュー クラスを作成する場合は、同じユーザー インターフェイス オブジェクトをアプリケーションに追加することが必要になることがあります。  
  
### <a name="to-create-menu-resources-with-the-menu-editor"></a>エディター メニューを使用してメニュー リソースを作成するには  
  
1. 使用に関する情報を参照し、[メニュー エディター](../windows/menu-editor.md)、4 つのコマンドを独自のメニューを作成します。  
  
#### <a name="to-create-toolbar-buttons-with-the-graphics-editor"></a>グラフィックス エディターを使用してツール バー ボタンを作成するには  
  
1. 使用に関する情報を参照し、[ツール バー エディター](../windows/toolbar-editor.md)、編集、レコード移動コマンド用のツール バー ボタンを追加するツール バー リソース。  
  
## <a name="see-also"></a>関連項目  

[レコード ビュー内のナビゲーションのサポート](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)<br/>
[レコード ビューの使用](../data/using-a-record-view-mfc-data-access.md)