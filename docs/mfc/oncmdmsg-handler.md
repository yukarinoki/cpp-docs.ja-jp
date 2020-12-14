---
description: '詳細については、次を参照してください: OnCmdMsg Handler'
title: OnCmdMsg ハンドラー
ms.date: 11/04/2016
f1_keywords:
- OnCmdMsg
helpviewer_keywords:
- messages, routing
- handlers [MFC]
- command routing [MFC], OnCmdMsg handler
- handlers, OnCmdMessage [MFC]
- OnCmdMessage method [MFC]
ms.assetid: 8df07024-506f-47e7-bba9-1c3bc5ad8ab6
ms.openlocfilehash: 69dfbd7ccc52a6d90b57ef9cedf0f896d65057b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243966"
---
# <a name="oncmdmsg-handler"></a>OnCmdMsg ハンドラー

コマンドのルーティングを実現するために、各コマンドターゲットは、 `OnCmdMsg` シーケンス内の次のコマンドターゲットのメンバー関数を呼び出します。 コマンドターゲットはを使用して、 `OnCmdMsg` コマンドを処理できるかどうかを判断し、それを処理できない場合は別のコマンドターゲットにルーティングします。

各コマンドターゲットクラスは、メンバー関数をオーバーライドでき `OnCmdMsg` ます。 オーバーライドにより、各クラスで特定の次のターゲットにコマンドをルーティングできます。 たとえば、フレームウィンドウでは、テーブルの [標準コマンドルート](command-routing.md)に示されているように、常に現在の子ウィンドウまたはビューにコマンドがルーティングされます。

の既定 `CCmdTarget` の実装で `OnCmdMsg` は、コマンドターゲットクラスのメッセージマップを使用して、受信する各コマンドメッセージのハンドラー関数を検索します。これは、標準のメッセージを検索する場合と同じです。 一致するものが見つかった場合は、ハンドラーを呼び出します。 メッセージマップの検索につい [ては、「フレームワークがメッセージマップを検索する方法](how-the-framework-searches-message-maps.md)」で説明されています。

## <a name="see-also"></a>関連項目

[フレームワークがハンドラーを呼び出す方法](how-the-framework-calls-a-handler.md)
