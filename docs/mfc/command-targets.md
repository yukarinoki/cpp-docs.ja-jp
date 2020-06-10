---
title: コマンド ターゲット
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: 59ba197174e95e42cd237c875f39f07801cb3dbe
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619313"
---
# <a name="command-targets"></a>コマンド ターゲット

フレームワークの図[コマンド](user-interface-objects-and-command-ids.md)は、メニュー項目などのユーザーインターフェイスオブジェクトと、オブジェクトがクリックされたときに結果のコマンドを実行するためにフレームワークが呼び出すハンドラー関数との間の接続を示しています。

Windows は、コマンドメッセージではないメッセージを、メッセージのハンドラーが呼び出されたウィンドウに直接送信します。 ただし、フレームワークはコマンドをいくつかの候補オブジェクト (コマンドターゲットと呼ばれます) にルーティングします。このオブジェクトの1つは、通常、コマンドのハンドラーを呼び出します。 ハンドラー関数は、コマンドと標準の Windows メッセージの両方に対して同じように動作しますが、[フレームワークがハンドラーを呼び出す方法](how-the-framework-calls-a-handler.md)について説明されているように、これらの関数が呼び出されるメカニズムは異なります。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](messages-and-commands-in-the-framework.md)
