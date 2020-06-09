---
title: プログレス コントロールの操作
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
ms.openlocfilehash: 3e3521a82854a85062f9b06bc33eb268d4b9c7a6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622433"
---
# <a name="manipulating-the-progress-control"></a>プログレス コントロールの操作

プログレスコントロール ([CProgressCtrl](reference/cprogressctrl-class.md)) の現在位置を変更するには、次の3つの方法があります。

- 位置は、事前設定された増分金額によって変更できます。

- 位置は任意の量で変更できます。

- 位置は、特定の値に変更できます。

### <a name="to-change-the-position-by-a-preset-amount"></a>事前設定された金額で位置を変更するには

1. インクリメント量を設定するには、 [Setstep](reference/cprogressctrl-class.md#setstep)メンバー関数を使用します。 既定では、この値は10です。 この値は、通常、コントロールの初期設定の1つとして設定されます。 ステップ値には負の値を指定できます。

1. 位置をインクリメントするには、 [StepIt](reference/cprogressctrl-class.md#stepit)メンバー関数を使用します。 これにより、コントロール自体が再描画されます。

    > [!NOTE]
    >  `StepIt`によって位置がラップされます。 たとえば、1-100 の範囲、20の手順、および90の位置を指定すると、 `StepIt` 位置は10に設定されます。

### <a name="to-change-the-position-by-an-arbitrary-amount"></a>任意の量で位置を変更するには

1. 位置を変更するには、 [OffsetPos](reference/cprogressctrl-class.md#offsetpos)メンバー関数を使用します。 `OffsetPos`負の値を受け取ります。

    > [!NOTE]
    >  `OffsetPos`とは異なり、 `StepIt` は位置をラップしません。 新しい位置は、範囲内に収まるように調整されます。

### <a name="to-change-the-position-to-a-specific-value"></a>位置を特定の値に変更するには

1. 位置を特定の値に設定するには、 [SetPos](reference/cprogressctrl-class.md#setpos)メンバー関数を使用します。 必要に応じて、新しい位置を範囲内に収まるように調整します。

通常、進行状況コントロールは出力のみに使用されます。 新しい値を指定せずに現在の位置を取得するには、 [GetPos](reference/cprogressctrl-class.md#getpos)を使用します。

## <a name="see-also"></a>関連項目

[CProgressCtrl の使い方](using-cprogressctrl.md)<br/>
[制限](controls-mfc.md)
