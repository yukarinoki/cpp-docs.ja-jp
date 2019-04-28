---
title: アサーションの表示
ms.date: 11/04/2016
helpviewer_keywords:
- debugging [ATL], displaying assertions
- assertions, displaying
- debugging assertions
- assertions, debugging
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
ms.openlocfilehash: bb06b8f124180ed566ecf2c761deb359444fb019
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62234879"
---
# <a name="displaying-assertions"></a>アサーションの表示

サービスに接続されているクライアントが応答を停止する場合は、サービスがアサートすることを確認する必要がないメッセージ ボックスが表示されますがある可能性があります。 これはコードをデバッグする Visual C のデバッガーを使用して確認できます (を参照してください[タスク マネージャーを使用して](../atl/using-task-manager.md)このセクションで前述した)。

設定することがあります、サービスで表示できない、メッセージ ボックスが表示されていると判断した場合、**デスクトップとの対話を許可するサービス**もう一度サービスを使用する前にオプション。 このオプションは、デスクトップに表示されるサービスによって表示されるメッセージ ボックスを許可する起動時のパラメーターです。 このオプションを設定するコントロール パネルの [サービス アプリケーションを開き、サービスを選択して、] をクリックして**スタートアップ**を選び、**デスクトップとの対話を許可するサービス**オプション。

## <a name="see-also"></a>関連項目

[デバッグのヒント](../atl/debugging-tips.md)
