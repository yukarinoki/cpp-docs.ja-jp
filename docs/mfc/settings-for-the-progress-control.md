---
description: '詳細情報: プログレスコントロールの設定'
title: プログレス コントロールの設定
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
ms.openlocfilehash: 0cf3caa5e7b87062b1714f8e5e350840157ff7ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217069"
---
# <a name="settings-for-the-progress-control"></a>プログレス コントロールの設定

プログレスコントロール ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) の基本設定は、範囲と現在の位置です。 この範囲は、操作の期間全体を表します。 現在の位置は、アプリケーションが操作の完了に向けた進行状況を表します。 範囲または位置を変更すると、プログレスコントロール自体が再描画されます。

既定では、範囲は 0-100 に設定され、初期位置は0に設定されます。 プログレスコントロールの現在の範囲設定を取得するには、 [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) メンバー関数を使用します。 範囲を変更するには、 [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) メンバー関数を使用します。

位置を設定するには、 [SetPos](../mfc/reference/cprogressctrl-class.md#setpos)を使用します。 新しい値を指定せずに現在の位置を取得するには、 [GetPos](../mfc/reference/cprogressctrl-class.md#getpos)を使用します。 たとえば、現在の操作の状態に対してのみクエリを実行することができます。

プログレスコントロールの現在位置をステップ実行するには、 [StepIt](../mfc/reference/cprogressctrl-class.md#stepit)を使用します。 各ステップの量を設定するには、 [Setstep](../mfc/reference/cprogressctrl-class.md#setstep)を使用します。

## <a name="see-also"></a>関連項目

[CProgressCtrl の使い方](../mfc/using-cprogressctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
