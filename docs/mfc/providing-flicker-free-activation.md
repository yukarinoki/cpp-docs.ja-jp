---
description: 詳細については、Flicker-Free ライセンス認証の提供に関するページをご覧ください。
title: ちらつきなしのアクティベーションの提供
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
ms.openlocfilehash: c0af1ccdd4795f55296ff38e0e74bc6492f79eb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248828"
---
# <a name="providing-flicker-free-activation"></a>ちらつきなしのアクティベーションの提供

コントロールが非アクティブ状態とアクティブな状態で同じように描画される場合 (ウィンドウなしのアクティベーションを使用しない場合) は、非アクティブ状態とアクティブな状態の間で遷移を行うときに通常発生する描画操作とそれに付随する視覚ちらつきを排除できます。 これを行うには、 **noFlickerActivate** フラグを、 [COleControl:: getcontrolflags](../mfc/reference/colecontrol-class.md#getcontrolflags)によって返されるフラグのセットに含めます。 次に例を示します。

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

MFC ActiveX コントロールウィザードを使用してコントロールを作成するときに、[[コントロールの設定](../mfc/reference/control-settings-mfc-activex-control-wizard.md)] ページで [**ちらつきなしのアクティベーション**] オプションを選択すると、このフラグを追加するコードが自動的に生成されます。

ウィンドウなしのアクティベーションを使用している場合、この最適化は無効です。

## <a name="see-also"></a>関連項目

[MFC ActiveX コントロール: 最適化](../mfc/mfc-activex-controls-optimization.md)
