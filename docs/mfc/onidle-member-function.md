---
title: OnIdle メンバー関数
ms.date: 11/19/2018
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: 17595713f942c7fe7784fa2a12adbcc583cad418
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619844"
---
# <a name="onidle-member-function"></a>OnIdle メンバー関数

Windows メッセージが処理されない場合、フレームワークは[CWinApp](reference/cwinapp-class.md)メンバー関数[OnIdle](reference/cwinapp-class.md#onidle) (MFC ライブラリリファレンスで説明) を呼び出します。

`OnIdle`バックグラウンドタスクを実行するには、をオーバーライドします。 既定のバージョンは、ツールバーボタンなどのユーザーインターフェイスオブジェクトの状態を更新し、操作の過程でフレームワークによって作成された一時オブジェクトのクリーンアップを実行します。 次の図は、キューにメッセージが存在しない場合のメッセージループの呼び出し方法を示してい `OnIdle` ます。

![メッセージ ループ プロセス](../mfc/media/vc387c1.gif "メッセージ ループ プロセス") <br/>
メッセージ ループ

アイドルループで実行できる操作の詳細については、「[アイドルループ処理](idle-loop-processing.md)」を参照してください。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](cwinapp-the-application-class.md)
