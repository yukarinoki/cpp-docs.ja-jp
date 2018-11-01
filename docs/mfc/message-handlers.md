---
title: メッセージ ハンドラー
ms.date: 11/04/2016
helpviewer_keywords:
- message handlers [MFC]
- command handling [MFC], message handlers
- handlers [MFC]
- message handling [MFC], message handler functions
- handlers [MFC], command
- handlers [MFC], message
ms.assetid: 51bc4e76-dbe3-4cc2-b026-3199d56b2fa9
ms.openlocfilehash: 1d775fc98fc97236cd63caf1e4422d32a9245410
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50588657"
---
# <a name="message-handlers"></a>メッセージ ハンドラー

Mfc では、専用*ハンドラー*関数は各メッセージを処理します。 メッセージ ハンドラー関数は、クラスのメンバー関数です。 このドキュメントでは、用語*メッセージ ハンドラー メンバー関数*、*メッセージ ハンドラー関数*、*メッセージ ハンドラー*、および*ハンドラー*同じ意味で。 一部の種類のメッセージ ハンドラーとも呼ばれます「コマンド ハンドラーです」

フレームワーク アプリケーションの作成には、作業の大部分を占めてメッセージ ハンドラーのアカウントを書き込んでいます。 ここでは、メッセージ処理メカニズムの動作方法について説明します。

メッセージのハンドラーはどのような実行は何でもそのメッセージへの応答で完了します。 クラスのプロパティ ウィンドウを使用してハンドラーを作成でき、ソース コード エディターを使用して、ハンドラーのコードを入力できます。

すべての Microsoft Visual C と MFC の機能を使用するには、ハンドラーを記述します。 すべてのクラスの一覧は、次を参照してください。[クラス ライブラリの概要](../mfc/class-library-overview.md)で、 *MFC リファレンス*します。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

