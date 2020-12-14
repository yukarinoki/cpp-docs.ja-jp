---
description: '詳細情報: メッセージのマッピング'
title: メッセージ マップ
ms.date: 11/04/2016
helpviewer_keywords:
- message maps [MFC], about message maps
- mappings [MFC], commands
- commands [MFC], mapping
- command mapping [MFC]
- message handling [MFC], connecting to handler functions
- commands [MFC], connecting to handler functions
- mappings [MFC], messages
- messages [MFC], mapping
ms.assetid: 996f0652-0698-4b8c-b893-cdaa836d9d0f
ms.openlocfilehash: 34d100a7ae527acc9f5520474e75b486b2f6276c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280795"
---
# <a name="mapping-messages"></a>メッセージ マップ

メッセージまたはコマンドを受信できる各フレームワーククラスには、独自の "メッセージマップ" があります。 フレームワークはメッセージマップを使用して、メッセージとコマンドをハンドラー関数に接続します。 クラスから派生 `CCmdTarget` したクラスは、メッセージマップを持つことができます。 その他の記事では、メッセージマップの詳細とその使用方法について説明しています。

"メッセージマップ" という名前の場合でも、メッセージマップはメッセージとコマンドの両方を処理します。メッセージの [カテゴリ](message-categories.md)に一覧表示されている3つのメッセージのすべてのカテゴリです。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](messages-and-commands-in-the-framework.md)
