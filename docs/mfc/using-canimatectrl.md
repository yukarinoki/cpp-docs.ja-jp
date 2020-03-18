---
title: CAnimateCtrl の使い方
ms.date: 11/04/2016
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
ms.openlocfilehash: 79c1a0111317514ef6fd68acd0c6a2ebdccc3ba4
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447106"
---
# <a name="using-canimatectrl"></a>CAnimateCtrl の使い方

[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)クラスによって表されるアニメーションコントロールは、AUDIO VIDEO INTERLEAVED (AVI) 形式 (標準の Windows ビデオ/オーディオ形式) でクリップを表示するウィンドウです。 AVI クリップは、ムービーのような一連のビットマップフレームです。

AVI クリップが表示されている間、スレッドは実行を続けているため、アニメーションコントロールの一般的な用途の1つは、時間のかかる操作中にシステムの動作を示すことです。 たとえば、[Windows 検索] ダイアログボックスには、システムがファイルを検索するときに、移動中の虫眼鏡が表示されます。

アニメーションコントロールで再生できるのは単純な AVI クリップだけで、サウンドはサポートされていません。 (制限事項の完全な一覧については、「 [CAnimateCtrl](../mfc/reference/canimatectrl-class.md)」を参照してください)。アニメーションコントロールの機能は厳しく制限されており、変更される可能性があるため、マルチメディア再生や記録機能を提供するコントロールが必要な場合は、MCIWnd コントロールなどの代替手段を使用する必要があります。 MCIWnd コントロールの詳細については、マルチメディアのドキュメントを参照してください。

## <a name="what-do-you-want-to-know-more-about"></a>詳細については、次を参照してください。

- [アニメーション コントロールの使い方](../mfc/using-an-animation-control.md)

- [アニメーション コントロールによる通知の送信](../mfc/notifications-sent-by-animation-controls.md)

## <a name="see-also"></a>参照

[コントロール](../mfc/controls-mfc.md)
