---
title: メッセージのカテゴリ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages [MFC], categories
- control-notification messages [MFC]
- Windows messages [MFC], categories
- controls [MFC], notifications
- command messages [MFC]
- messages [MFC], Windows
- message handling [MFC], message types
ms.assetid: 68e1db75-9da6-4a4d-b2c2-dc4d59f8d87b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d0e4710c74c12bf62cd19df6a053aea9ac35eaf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="message-categories"></a>メッセージの種類
メッセージの種類は用に作成するハンドラーは次の 3 つのメイン カテゴリがあります。  
  
1.  Windows メッセージ  
  
     始まるメッセージ、主に、これが含まれています、 **wm _ で始まる**プレフィックスを除く**WM_COMMAND**です。 Windows メッセージは、windows およびビューによって処理されます。 これらのメッセージには、メッセージを処理する方法を決定するために使用するパラメーターが多くの場合があります。  
  
2.  コントロールの通知  
  
     これが含まれます**WM_COMMAND**コントロールとその他の子ウィンドウからの通知メッセージを親ウィンドウ。 エディット コントロールがその親を送信するなど、 **WM_COMMAND**メッセージを含む、 **EN_CHANGE**コントロール通知コード、ユーザーが取得操作するときに、エディット コントロールでテキスト変更可能性があります。 メッセージのウィンドウのハンドラーは、コントロール内のテキストを取得するなど、いくつかの適切な方法で、通知メッセージに応答します。  
  
     フレームワークは、他のコントロール通知メッセージをルーティング**wm _ で始まる**メッセージ。 ただしは、1 つの例外、 **BN_CLICKED**にユーザーがクリックしたときに、ボタンによって送信されたコントロール通知メッセージです。 このメッセージがコマンド メッセージとして特別に扱われ、その他のコマンドと同様にルーティングします。  
  
3.  コマンド メッセージ  
  
     これが含まれます**WM_COMMAND**ユーザー インターフェイス オブジェクトからの通知メッセージ: メニューのツールバーのボタン、およびアクセラレータ キー。 フレームワークは、他のメッセージを異なるコマンドを処理し、」の説明に従って、オブジェクトの多くの種類で処理できます[コマンド ターゲット](../mfc/command-targets.md)です。  
  
##  <a name="_core_windows_messages_and_control.2d.notification_messages"></a> Windows メッセージとコントロール通知メッセージ  
 1 と 2 のカテゴリ内のメッセージ、Windows メッセージとコントロール通知 — windows によって処理されます: クラスから派生したクラスのオブジェクトを`CWnd`です。 これが含まれます`CFrameWnd`、 `CMDIFrameWnd`、 `CMDIChildWnd`、 `CView`、 `CDialog`、およびこれらの基本クラスから派生した独自のクラスです。 このようなオブジェクトをカプセル化、 `HWND`Windows のウィンドウへのハンドル。  
  
##  <a name="_core_command_messages"></a> コマンド メッセージ  
 カテゴリ 3 内のメッセージ-コマンド: 各種のオブジェクトによって処理されることができます: ドキュメント、ドキュメント テンプレート、およびウィンドウとビューだけでなく、アプリケーション オブジェクト自体です。 コマンドは、特定のオブジェクトに直接影響を与える、時に合理的にコマンドを処理するオブジェクトです。 たとえば、ファイル メニューの 開く コマンドは、アプリケーションに論理的に関連付けられた: アプリケーションが、コマンド受信時に指定されたドキュメントを開きます。 したがって、開いているコマンドのハンドラーは、アプリケーション クラスのメンバー関数です。 詳細については、コマンドおよびオブジェクトへのルーティング方法は、次を参照してください。[フレームワークがハンドラーを呼び出す方法](../mfc/how-the-framework-calls-a-handler.md)です。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

