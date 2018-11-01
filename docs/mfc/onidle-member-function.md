---
title: OnIdle メンバー関数
ms.date: 11/04/2016
f1_keywords:
- OnIdle
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
ms.openlocfilehash: 3d457c1675d5f5f3f88c67b1aac2d03509c21564
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662151"
---
# <a name="onidle-member-function"></a>OnIdle メンバー関数

Windows メッセージが処理されていないときに、フレームワーク、 [CWinApp](../mfc/reference/cwinapp-class.md)メンバー関数は[OnIdle](../mfc/reference/cwinapp-class.md#onidle) (MFC ライブラリのリファレンスで説明)。

オーバーライド`OnIdle`バック グラウンド タスクを実行します。 既定のバージョンでは、ツール バー ボタンなどのユーザー インターフェイス オブジェクトの状態を更新し、その操作の過程で、フレームワークによって作成される一時オブジェクトのクリーンアップを実行します。 次の図は、メッセージ ループを呼び出す方法を示しています。`OnIdle`キューにメッセージがない場合にします。

![メッセージ ループ プロセス](../mfc/media/vc387c1.gif "vc387c1")メッセージ ループ

アイドル ループで実行できる操作についての詳細については、次を参照してください。[アイドル ループ プロセシング](../mfc/idle-loop-processing.md)します。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
