---
title: ユーザー インターフェイス オブジェクトとコマンド Id |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- keyboard shortcuts, associating with IDs
- MFC, command routing
- toolbar controls [MFC], command ID
- menu items, associating with IDs
- user interface objects [MFC], associating with IDs
- command IDs, user interface objects
- command routing [MFC], MFC
- command handling [MFC], user-interface objects
ms.assetid: 4ea19e9b-ed1e-452e-bd33-7f509107a45b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6b56babf0e42dde521a6bda3a7d9713db519182c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385600"
---
# <a name="user-interface-objects-and-command-ids"></a>ユーザー インターフェイス オブジェクトとコマンド ID
メニュー項目、ツール バー ボタン、およびアクセラレータ キー、「ユーザー インターフェイス オブジェクト」コマンドを生成できます。 このような各ユーザー インターフェイス オブジェクトは、ID を持つ オブジェクトとコマンドに同じ ID を割り当てることによって、ユーザー インターフェイス オブジェクトをコマンドに関連付けます。 説明したよう[メッセージ](../mfc/messages.md)コマンドは、特別なメッセージとして実装されます。 「コマンド フレームワーク内の」次の図は、フレームワークがコマンドを管理する方法を示します。 生成するとき、ユーザー インターフェイス オブジェクトのコマンドなど`ID_EDIT_CLEAR_ALL`、コマンドを処理できないアプリケーション内のオブジェクトのいずれかの: ドキュメント オブジェクトの下の図の`OnEditClearAll`関数は、ドキュメントのメッセージ マップを通じて呼び出されます。  
  
 ![フレームワークにおけるコマンド](../mfc/media/vc385p1.gif "vc385p1")  
フレームワークにおけるコマンド  
  
 「コマンド更新フレームワーク内の」次の図は、MFC がメニュー項目とツール バー ボタンなどのユーザー インターフェイス オブジェクトを更新する方法を示します。 メニューは、停止、またはツールバーのボタンの場合、アイドル ループ時に削除、前に、MFC は、更新コマンドをルーティングします。 次の図では、ドキュメント オブジェクトで、更新コマンド ハンドラー`OnUpdateEditClearAll`を有効にするにまたは、ユーザー インターフェイス オブジェクトを無効にします。  
  
 ![Framework の更新コマンド](../mfc/media/vc385p2.png "vc385p2")  
フレームワーク内のコマンド更新  
  
## <a name="see-also"></a>関連項目  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

