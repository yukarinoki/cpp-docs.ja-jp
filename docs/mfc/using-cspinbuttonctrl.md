---
title: CSpinButtonCtrl の使い方
ms.date: 11/04/2016
helpviewer_keywords:
- up-down controls [MFC], spin button control
- up-down controls
- spin button control
- CSpinButtonCtrl class [MFC], using
ms.assetid: a91db36b-e11e-42ef-8e89-51915cc486d2
ms.openlocfilehash: 6f72601d3813f36e4a99b9ab04f2e9383c58df94
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366482"
---
# <a name="using-cspinbuttonctrl"></a>CSpinButtonCtrl の使い方

*スピン ボタン*コントロール (*アップダウン*コントロールとも呼ばれます) は、ユーザーがクリックして値を調整できる一対の矢印を提供します。 この値は *、現在の位置*と呼ばれます。 位置はスピンボタンの範囲内に留まります。 ユーザーが上矢印をクリックすると、位置は最大値に向かって移動します。ユーザーが下矢印をクリックすると、位置は最小方向に移動します。

スピン ボタン コントロールは、[クラス](../mfc/reference/cspinbuttonctrl-class.md)によって MFC で表されます。

> [!NOTE]
> 既定では、スピン ボタンの範囲の最大値はゼロ (0) に設定され、最小値は 100 に設定されます。 最大値が最小値より小さいため、上矢印をクリックすると位置が小さくなり、下矢印をクリックすると値が増えます。 これらの値を調整するには[、CSpinButtonCtrl::SetRange を](../mfc/reference/cspinbuttonctrl-class.md#setrange)使用します。

通常、現在の位置はコンパニオン コントロールに表示されます。 コンパニオン コントロールは *、"相棒ウィンドウ"* と呼ばれます。 スピン ボタン コントロールの図解については、「Windows SDK[のアップダウン コントロールについて](/windows/win32/Controls/up-down-controls)」を参照してください。

スピン コントロールとエディット コントロールのダイアログ ボックスを作成するには、Visual Studio で、まずエディット コントロールをダイアログ ボックスまたはウィンドウにドラッグしてから、スピン コントロールをドラッグします。 スピン コントロールを選択し、**その [自動バディ**] プロパティと **[バディ整数を設定]** プロパティを **[True]** に設定します。 また **、Alignment**プロパティを設定します。**右揃え**が最も一般的です。 これらの設定では、タブ オーダーのエディット コントロールの直前にエディット コントロールが直接表示されるため、編集コントロールは関連ウィンドウとして設定されます。 エディット コントロールは整数を表示し、スピン コントロールはエディット コントロールの右側に埋め込まれます。 オプションで、スピン コントロールの有効な範囲を設定するには[、CSpinButtonCtrl::SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange)メソッドを使用します。 スピン コントロールと関連ウィンドウの間で通信するイベント ハンドラーは、データを直接交換するため必要ありません。 たとえば、一連のウィンドウやダイアログ ボックスをページに移動するなど、スピン コントロールを使用する場合は、UDN_DELTAPOS メッセージのハンドラーを追加してカスタム アクションを実行します。

## <a name="what-do-you-want-to-know-more-about"></a>何についてもっと知りたいのですか?

- [スピン ボタンのスタイル](../mfc/spin-button-styles.md)

- [スピン ボタンのメンバー関数](../mfc/spin-button-member-functions.md)

## <a name="see-also"></a>関連項目

[コントロール](../mfc/controls-mfc.md)
