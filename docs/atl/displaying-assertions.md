---
description: '詳細情報: アサーションの表示'
title: アサーションの表示
ms.date: 05/05/2019
helpviewer_keywords:
- debugging [ATL], displaying assertions
- assertions, displaying
- debugging assertions
- assertions, debugging
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
ms.openlocfilehash: 3f925d5f3a7d1ad0ac1171ea8983b57ead147bf4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153015"
---
# <a name="displaying-assertions"></a>アサーションの表示

サービスに接続しているクライアントが応答を停止していると思われる場合は、サービスがアサートされており、表示できないメッセージボックスが表示されている可能性があります。 これを確認するには、Visual Studio デバッガーを使用してコードをデバッグします (このセクションで前述した「 [タスクマネージャーの使用](../atl/using-task-manager.md) 」を参照してください)。

表示できないメッセージボックスが表示されていることを確認した場合は、サービスを再度使用する前に、[ **デスクトップとの対話をサービスに許可** する] オプションを設定することをお勧めします。 このオプションは、サービスによって表示されるすべてのメッセージボックスがデスクトップに表示されることを許可するスタートアップパラメーターです。 このオプションを設定するには、コントロールパネルの [サービス] を開き、サービスを選択して [ **スタートアップ**] をクリックし、[ **デスクトップとの対話をサービスに許可する** ] オプションを選択します。

## <a name="see-also"></a>関連項目

[デバッグのヒント](../atl/debugging-tips.md)
