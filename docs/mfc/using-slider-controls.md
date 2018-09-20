---
title: スライダー コントロールを使用して |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d0496a15b289ec055fd2706975603f25cef13938
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388837"
---
# <a name="using-slider-controls"></a>スライダー コントロールの使い方

スライダー コントロールの一般的な使用方法では、次のパターンに従います。

- コントロールが作成されます。 コントロールがダイアログ ボックスのテンプレートで指定されている場合、ダイアログ ボックスが作成されると作成は自動です。 (必要、 [CSliderCtrl](../mfc/reference/csliderctrl-class.md)スライダー コントロールに対応するダイアログ クラスのメンバーです)。また、使用することができます、[作成](../mfc/reference/csliderctrl-class.md#create)メンバー関数は、すべてのウィンドウの子ウィンドウとして、コントロールを作成します。

- コントロールの値を設定するさまざまなセットのメンバー関数を呼び出します。 変更行うことができますにはには、スライダーの最小値と最大位置を設定、目盛りの描画、選択範囲を設定およびスライダーの位置が含まれます。 これを行う適切な時刻は] ダイアログ ボックスで、[コントロール] ダイアログ ボックスの[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)関数。

- ユーザー コントロールと対話をさまざまな通知メッセージを送信します。 コントロールからスライダーの値を抽出するには呼び出すことによって、 [GetPos](../mfc/reference/csliderctrl-class.md#getpos)メンバー関数。

- コントロールに完了するが適切に破棄されるかどうかを確認する必要があります。 スライダー コントロールがダイアログ ボックスでは、場合、および`CSliderCtrl`オブジェクトが自動的に破棄されます。 かどうか、する必要があることに、両方のコントロールを確認し、`CSliderCtrl`オブジェクトが破棄されました。

## <a name="see-also"></a>関連項目

[CSliderCtrl の使い方](../mfc/using-csliderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

