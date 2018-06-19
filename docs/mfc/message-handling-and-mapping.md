---
title: メッセージの処理とマップ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, messages
- message handling [MFC]
- message maps [MFC]
ms.assetid: 62fe2a1b-944c-449d-a0f0-63c11ee0a3cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66171c5df636597a2ff6be0438b558dc418b72af
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348529"
---
# <a name="message-handling-and-mapping"></a>メッセージの処理とマップ
ここでは、MFC フレームワークがメッセージとコマンドの処理方法とハンドラー関数への接続方法を説明します。  
  
 Windows 用の従来のプログラムでは、Windows メッセージは、ウィンドウ プロシージャで大きな switch ステートメントで処理されます。 MFC が代わりに使用して[メッセージ マップ](../mfc/message-categories.md)に直接メッセージを個別のクラス メンバー関数にマップします。 この目的でメッセージ マップは仮想関数よりも効率的であり最も適切な C++ オブジェクトで処理するメッセージが可能に: アプリケーション、ドキュメント、ビュー、およびなどです。 1 つのメッセージまたはメッセージ、コマンド Id の範囲をマップしたり、Id を制御できます。  
  
 **WM_COMMAND**メッセージ-通常、メニューのツールバーのボタン、またはアクセラレータによって生成 — もメッセージ マップ機構を使用します。 MFC 標準を定義する[ルーティング](../mfc/command-routing.md)アプリケーション間では、コマンドのメッセージのフレーム ウィンドウ、ビュー、および、プログラム内のアクティブなドキュメントです。 必要がある場合、このルーティングを上書きすることができます。  
  
 メッセージ マップ指定することも (メニューやツールバーのボタン) のユーザー インターフェイス オブジェクトを更新する方法を有効または無効にすることに合わせて、現在のコンテキスト。  
  
 メッセージと windows メッセージ キューの詳細については、次を参照してください。[メッセージとメッセージ キュー](http://msdn.microsoft.com/library/windows/desktop/ms632590) Windows SDK に含まれています。  
  
## <a name="what-do-you-want-to-know-more-about"></a>詳しくは次のトピックをクリックしてください。  
  
-   [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)  
  
-   [フレームワークがメッセージのハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)  
  
-   [フレームワークのメッセージ マップ検索方法](../mfc/how-the-framework-searches-message-maps.md)  
  
-   [メッセージ ハンドラー関数の宣言](../mfc/declaring-message-handler-functions.md)  
  
-   [マップ (関数にメッセージを)](../mfc/reference/mapping-messages-to-functions.md)  
  
-   [ステータス バーにコマンド情報を表示する方法](../mfc/how-to-display-command-information-in-the-status-bar.md)  
  
-   [ユーザー インターフェイス オブジェクトの動的更新](../mfc/how-to-update-user-interface-objects.md)  
  
-   [方法: テンプレート クラスのメッセージ マップを作成する](../mfc/how-to-create-a-message-map-for-a-template-class.md)  
  
## <a name="see-also"></a>関連項目  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)   
 [CWnd クラス](../mfc/reference/cwnd-class.md)   
 [CCmdTarget クラス](../mfc/reference/ccmdtarget-class.md)
