---
title: Canimatectrl の使い方 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CAnimateCtrl
dev_langs:
- C++
helpviewer_keywords:
- animation controls [MFC], CAnimateCtrl class
- controls [MFC], animation
- CAnimateCtrl class [MFC], about CAnimateCtrl class [MFC]
ms.assetid: 696c0805-bef0-4e2e-a9e7-b37b9215b7f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b02a07b1f5a433ffa9525da8e8a7f942c9034d54
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398457"
---
# <a name="using-canimatectrl"></a>CAnimateCtrl の使い方

アニメーション コントロール、クラスによって表される[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)、オーディオ Video Interleaved (AVI) 形式でクリップを表示するウィンドウ-Windows の標準のビデオ/オーディオ形式。 AVI クリップは、一連の映画のように、ビットマップ フレームです。

スレッドの継続実行 AVI クリップが表示されますが、ために、アニメーション コントロールの 1 つの一般的な用途は、時間のかかる操作中にシステムの使用状況を示すは。 たとえば、Windows の検索 ダイアログ ボックスでは、システム ファイルを検索として移動虫眼鏡が表示されます。

アニメーション コントロールは、単純な AVI クリップを再生できますのみと、サウンドをサポートしていません。 (完了の制限事項の一覧を表示するには、次を参照してください[CAnimateCtrl](../mfc/reference/canimatectrl-class.md)。)。アニメーション コントロールの機能が大幅に限定されるため、変更される可能性は、マルチ メディアの再生または録音機能を提供するコントロールを必要がある場合、MCIWnd コントロールなどの代替を使用してください。 MCIWnd 管理の詳細については、マルチ メディアのドキュメントを参照してください。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [アニメーション コントロールの使い方](../mfc/using-an-animation-control.md)

- [アニメーション コントロールによる通知の送信](../mfc/notifications-sent-by-animation-controls.md)

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)

