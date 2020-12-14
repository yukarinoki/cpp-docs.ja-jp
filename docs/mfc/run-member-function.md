---
description: '詳細情報: Run Member 関数'
title: Run メンバー関数
ms.date: 11/04/2016
helpviewer_keywords:
- WinMain method [MFC]
ms.assetid: 24ab7597-2354-495b-9a20-2c8ccc7385b3
ms.openlocfilehash: ae67c6b02344a65735ce06775b1d1788d1dabf2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217823"
---
# <a name="run-member-function"></a>Run メンバー関数

フレームワークアプリケーションは、ほとんどの時間を、 [CWinApp](../mfc/reference/cwinapp-class.md)クラスの[Run](../mfc/reference/cwinapp-class.md#run)メンバー関数に費やします。 初期化の後、は `WinMain` `Run` を呼び出してメッセージループを処理します。

`Run` メッセージループを順番に実行し、メッセージキューで使用可能なメッセージを確認します。 メッセージが使用可能な場合は、 `Run` アクションのためにディスパッチします。 使用できるメッセージがない場合 (多くの場合は、)、自身 `Run` `OnIdle` またはフレームワークが実行する必要のあるアイドル時間の処理を実行するためにを呼び出します。 メッセージがなく、アイドル処理も行われていない場合、アプリケーションは何かが発生するまで待機します。 アプリケーションが終了すると、はを `Run` 呼び出し `ExitInstance` ます。 [OnIdle メンバー関数](../mfc/onidle-member-function.md)の図は、メッセージループ内のアクションのシーケンスを示しています。

メッセージのディスパッチは、メッセージの種類によって異なります。 詳細については、「 [フレームワークのメッセージとコマンド](../mfc/messages-and-commands-in-the-framework.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CWinApp: Application クラス](../mfc/cwinapp-the-application-class.md)
