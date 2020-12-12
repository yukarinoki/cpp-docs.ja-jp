---
description: '詳細情報: メッセージハンドラー'
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
ms.openlocfilehash: dc3f52956f125542ef0c5d879543f1e8a49e803b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203368"
---
# <a name="message-handlers"></a>メッセージ ハンドラー

MFC では、専用の *ハンドラー* 関数が個々のメッセージを処理します。 メッセージハンドラー関数は、クラスのメンバー関数です。 このドキュメントでは、 *メッセージハンドラーメンバー関数*、メッセージ *ハンドラー関数*、 *メッセージハンドラー*、および *ハンドラー* という用語を使用します。 一部の種類のメッセージハンドラーは、"コマンドハンドラー" とも呼ばれます。

フレームワークアプリケーションの作成における作業の大部分に対するメッセージハンドラーアカウントの作成。 この記事ファミリでは、メッセージ処理機構のしくみについて説明します。

メッセージのハンドラーは、メッセージへの応答としてどのような処理を実行しますか。 クラスの [クラスウィザード](reference/mfc-class-wizard.md) を使用してハンドラーを作成し、ソースコードエディターを使用してハンドラーのコードを入力することができます。

Microsoft Visual C++ と MFC のすべての機能を使用して、ハンドラーを記述できます。 すべてのクラスの一覧については、「 *MFC リファレンス*」の「[クラスライブラリの概要](class-library-overview.md)」を参照してください。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](messages-and-commands-in-the-framework.md)
