---
title: OnIdle メンバー関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnIdle
dev_langs:
- C++
helpviewer_keywords:
- processing messages [MFC]
- OnIdle method [MFC]
- idle loop processing [MFC]
- CWinApp class [MFC], OnIdle method [MFC]
- message handling [MFC], OnIdle method [MFC]
ms.assetid: 51adc874-0075-4f76-be1c-79283f46c10b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9b334a4561af40b69bc367ab5b1129afa8fb29ae
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377299"
---
# <a name="onidle-member-function"></a>OnIdle メンバー関数

Windows メッセージが処理されていないときに、フレームワーク、 [CWinApp](../mfc/reference/cwinapp-class.md)メンバー関数は[OnIdle](../mfc/reference/cwinapp-class.md#onidle) (MFC ライブラリのリファレンスで説明)。

オーバーライド`OnIdle`バック グラウンド タスクを実行します。 既定のバージョンでは、ツール バー ボタンなどのユーザー インターフェイス オブジェクトの状態を更新し、その操作の過程で、フレームワークによって作成される一時オブジェクトのクリーンアップを実行します。 次の図は、メッセージ ループを呼び出す方法を示しています。`OnIdle`キューにメッセージがない場合にします。

![メッセージ ループ プロセス](../mfc/media/vc387c1.gif "vc387c1")メッセージ ループ

アイドル ループで実行できる操作についての詳細については、次を参照してください。[アイドル ループ プロセシング](../mfc/idle-loop-processing.md)します。

## <a name="see-also"></a>関連項目

[CWinApp: アプリケーション クラス](../mfc/cwinapp-the-application-class.md)
