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
ms.openlocfilehash: 43caffe53be180221b4145a03df7cfc41c31828e
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928639"
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI マクロ
使用して、**プロパティ**コマンド ターゲット オブジェクトにコマンド更新ハンドラーへのユーザー インターフェイス オブジェクトを接続するウィンドウです。 ON_UPDATE_COMMAND_UI マクロをユーザー インターフェイス オブジェクトの ID を接続し、ハンドラーを更新プログラムを処理するオブジェクトを生成するには自動的にします。 参照してください[関数へのメッセージの割り当て](../mfc/reference/mapping-messages-to-functions.md)詳細についてはします。  
  
 たとえば、更新するには、プログラムの編集 メニューで、すべてクリア コマンドを使用して、**プロパティ**コマンド更新ハンドラーの関数宣言を選択したクラスのメッセージ マップ エントリを追加するウィンドウと呼ばれる`OnUpdateEditClearAll`クラス宣言、およびクラスの実装ファイルには空の関数テンプレートです。 関数プロトタイプは、次のようになります。  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]  
  
 すべてのハンドラー関数と同様に、 **afx_msg**キーワード。 1 つの引数へのポインターを受け取るすべての更新ハンドラーと同じように、`CCmdUI`オブジェクト。  
  
## <a name="see-also"></a>関連項目  
 [ユーザー インターフェイス オブジェクトの更新方法](../mfc/how-to-update-user-interface-objects.md)

