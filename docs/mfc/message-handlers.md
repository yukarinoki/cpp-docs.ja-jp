---
title: メッセージ ハンドラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be4ccf9ec33e5ddf497193c1942e9f300f8cae57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="message-handlers"></a>メッセージ ハンドラー
MFC では、専用*ハンドラー*関数は、各メッセージを処理します。 メッセージ ハンドラー関数は、クラスのメンバー関数です。 このドキュメントでは、用語*メッセージ ハンドラー メンバー関数は、*、*メッセージ ハンドラー関数*、*メッセージ ハンドラー*、および*ハンドラー*同義です。 一部のメッセージ ハンドラーとも呼ばれます「コマンド ハンドラー」  
  
 フレームワーク アプリケーションの作成には、作業の大部分を占めてメッセージ ハンドラーのアカウントを書き込んでいます。 ここでは、メッセージ処理のメカニズムの動作方法について説明します。  
  
 メッセージのハンドラーは、何が必要なあらゆるそのメッセージを応答で元に戻す。 クラスのプロパティ ウィンドウを使用してハンドラーを作成し、ソース コード エディターを使用して、ハンドラーのコードを入力できます。  
  
 ハンドラーを記述するのにには、すべての Microsoft Visual C と MFC の機能を使用できます。 すべてのクラスの一覧は、次を参照してください。[クラス ライブラリの概要](../mfc/class-library-overview.md)で、 *『 MFC リファレンス*です。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

