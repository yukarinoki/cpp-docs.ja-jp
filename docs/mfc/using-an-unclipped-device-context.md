---
description: '詳細情報: クリッピングを行っていないデバイスコンテキストの使用'
title: クリッピングを行わないデバイス コンテキストの使用
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
ms.openlocfilehash: 76131d35b108b04caf0b07be8c46e250120f9f62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202640"
---
# <a name="using-an-unclipped-device-context"></a>クリッピングを行わないデバイス コンテキストの使用

コントロールがクライアントの四角形の外に描画されないことが確実である場合は、によって行われるの呼び出しを無効にすることで、サイズが小さくても、検出速度を上げることができ `IntersectClipRect` `COleControl` ます。 これを行うには、 [COleControl:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)によって返されるフラグのセットから *clipPaintDC* フラグを削除します。 次に例を示します。

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

MFC ActiveX コントロールウィザードを使用してコントロールを作成するときに、[[コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)] ページで [クリッピングを行わない **デバイスコンテキスト**] オプションを選択すると、このフラグを削除するコードが自動的に生成されます。

ウィンドウなしのアクティベーションを使用している場合、この最適化は無効です。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)
