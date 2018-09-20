---
title: メッセージの割り当て |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7324da5eaff15d240cabbaede2c2982021361257
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410982"
---
# <a name="mapping-messages"></a>メッセージ マップ

各メッセージまたはコマンドを受信できるフレームワーク クラス独自"メッセージにマップが存在します" フレームワークでは、メッセージ マップを使用してメッセージとコマンドをハンドラー関数に接続します。 クラスから派生したあらゆるクラス`CCmdTarget`メッセージ マップがあることができます。 他の記事では、メッセージ マップの詳細を説明し、それらを使用する方法について説明します。

名前「メッセージ マップ」にもかかわらず両方を処理するメッセージがメッセージし、コマンド: メッセージの一覧のすべての 3 つのカテゴリ[メッセージ カテゴリ](../mfc/message-categories.md)します。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

