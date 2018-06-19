---
title: メッセージ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- messages, MFC
- messages [MFC]
ms.assetid: b1476310-a135-42ca-817c-444fb3675491
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: abd49410f9982788e9403f0cb83ca8656473417d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344105"
---
# <a name="messages"></a>メッセージ
メッセージ ループで、**実行**クラスのメンバー関数`CWinApp`取得には、さまざまなイベントによって生成されたメッセージがキューに登録します。 たとえば、ユーザーには、マウスがクリックすると、Windows は送信いくつかのマウスに関連するメッセージなど`WM_LBUTTONDOWN`マウスの左ボタンが押されたときに、`WM_LBUTTONUP`マウスの左ボタンが離されたとき。 アプリケーション メッセージ ループのフレームワークの実装では、目的のウィンドウ メッセージをディスパッチします。  
  
 メッセージの重要なカテゴリの記載[メッセージ カテゴリ](../mfc/message-categories.md)です。  
  
## <a name="see-also"></a>関連項目  
 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)

