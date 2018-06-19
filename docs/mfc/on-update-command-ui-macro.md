---
title: ON_UPDATE_COMMAND_UI マクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_UPDATE_COMMAND_UI
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 726eba2edbb857784a3a23ddcfb2d69fd8e30a72
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348486"
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI マクロ
使用して、**プロパティ**コマンド ターゲット オブジェクトにコマンド更新ハンドラーへのユーザー インターフェイス オブジェクトを接続するウィンドウです。 ユーザー インターフェイス オブジェクトの ID を自動的に接続、`ON_UPDATE_COMMAND_UI`マクロを更新プログラムを処理するオブジェクトでのハンドラーを作成します。 参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)詳細についてはします。  
  
 たとえば、更新するには、プログラムの編集 メニューで、すべてクリア コマンドを使用して、**プロパティ**コマンド更新ハンドラーの関数宣言を選択したクラスのメッセージ マップ エントリを追加するウィンドウと呼ばれる`OnUpdateEditClearAll`クラス宣言、およびクラスの実装ファイルには空の関数テンプレートです。 関数プロトタイプは、次のようになります。  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]  
  
 すべてのハンドラー関数と同様に、 **afx_msg**キーワード。 1 つの引数へのポインターを受け取るすべての更新ハンドラーと同じように、`CCmdUI`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)

