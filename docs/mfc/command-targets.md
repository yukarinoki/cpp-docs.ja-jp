---
description: '詳細情報: コマンドターゲット'
title: コマンド ターゲット
ms.date: 11/04/2016
helpviewer_keywords:
- command targets
- command mapping
- messages, command [MFC]
- command routing [MFC], command targets
ms.assetid: b0f784e5-c6dc-4391-9e71-aa7b7dcbe9f0
ms.openlocfilehash: b7be03282400c2d3a0dcf5eb0d24a0b06456ebca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206254"
---
# <a name="command-targets"></a>コマンド ターゲット

フレームワークの図 [コマンド](user-interface-objects-and-command-ids.md) は、メニュー項目などのユーザーインターフェイスオブジェクトと、オブジェクトがクリックされたときに結果のコマンドを実行するためにフレームワークが呼び出すハンドラー関数との間の接続を示しています。

Windows は、コマンドメッセージではないメッセージを、メッセージのハンドラーが呼び出されたウィンドウに直接送信します。 ただし、フレームワークはコマンドをいくつかの候補オブジェクト (コマンドターゲットと呼ばれます) にルーティングします。このオブジェクトの1つは、通常、コマンドのハンドラーを呼び出します。 ハンドラー関数は、コマンドと標準の Windows メッセージの両方に対して同じように動作しますが、 [フレームワークがハンドラーを呼び出す方法](how-the-framework-calls-a-handler.md)について説明されているように、これらの関数が呼び出されるメカニズムは異なります。

## <a name="see-also"></a>関連項目

[フレームワークのメッセージとコマンド](messages-and-commands-in-the-framework.md)
