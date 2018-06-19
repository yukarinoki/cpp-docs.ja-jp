---
title: メンバー関数を実行 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be1d7d90b4c13a23e2e3456e7371abbae61be4e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379897"
---
# <a name="run-member-function"></a>Run メンバー関数
ほとんどの時間内に費やすフレームワーク アプリケーション、[実行](../mfc/reference/cwinapp-class.md#run)クラスのメンバー関数[CWinApp](../mfc/reference/cwinapp-class.md)です。 初期化後は、`WinMain`呼び出し**実行**メッセージ ループを処理します。  
  
 **実行**、使用可能なメッセージのメッセージ キューをチェックするメッセージ ループを切り替えます。 メッセージが、使用可能な場合は**実行**をディスパッチします。 True の場合、これは多くの場合、使用可能なメッセージがない場合は、**実行**呼び出し`OnIdle`完了またはフレームワークを必要とするアイドル処理を実行します。 ある場合にメッセージがないとなしのアイドル処理を行うには、アプリケーションは何かが発生するまで待機します。 アプリケーションが終了すると、**実行**呼び出し`ExitInstance`です。 図に[OnIdle メンバー関数は、](../mfc/onidle-member-function.md)メッセージ ループで一連のアクションを示しています。  
  
 メッセージのディスパッチは、メッセージの種類によって異なります。 詳細については、次を参照してください。[フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)です。  
  
## <a name="see-also"></a>関連項目  
 [CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
