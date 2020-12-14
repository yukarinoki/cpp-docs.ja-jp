---
description: '詳細情報: スピンボタンのメンバー関数'
title: スピン ボタンのメンバー関数
ms.date: 11/04/2016
helpviewer_keywords:
- spin button control, methods
- CSpinButtonCtrl class [MFC], methods
ms.assetid: a08a26fd-b803-4cbe-a509-395fa357d057
ms.openlocfilehash: 6a03ab33d29634ed85d807eb5b51edfdef310d65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216835"
---
# <a name="spin-button-member-functions"></a>スピン ボタンのメンバー関数

スピンコントロール ([CSpinButtonCtrl](../mfc/reference/cspinbuttonctrl-class.md)) には、いくつかのメンバー関数が用意されています。 スピンボタンの次の属性を変更するには、これらの関数を使用します。

- **アクセラレーション** ユーザーが矢印ボタンを押したときに位置が変化する速度を調整できます。 アクセラレーションを操作するには、 [SetAccel](../mfc/reference/cspinbuttonctrl-class.md#setaccel) および [GetAccel](../mfc/reference/cspinbuttonctrl-class.md#getaccel) メンバー関数を使用します。

- **ベース** 関連ウィンドウのキャプションに位置を表示するために使用するベース (10 または 16) を変更することができます。 ベースを操作するには、 [getbase](../mfc/reference/cspinbuttonctrl-class.md#getbase) および [setbase](../mfc/reference/cspinbuttonctrl-class.md#setbase) メンバー関数を使用します。

- 関連 **ウィンドウ** 関連ウィンドウは動的に設定できます。 どのコントロールが関連ウィンドウであるかを照会または変更するには、 [getbuddy](../mfc/reference/cspinbuttonctrl-class.md#getbuddy) および [setbuddy](../mfc/reference/cspinbuttonctrl-class.md#setbuddy) メンバー関数を使用します。

- **位置** クエリを実行して位置を変更することができます。 位置を直接操作するには、 [GetPos](../mfc/reference/cspinbuttonctrl-class.md#getpos) および [SetPos](../mfc/reference/cspinbuttonctrl-class.md#setpos) メンバー関数を使用します。 関連するコントロールのキャプションが変更されている可能性があるため (たとえば、buddy がエディットコントロールである場合)、は `GetPos` 現在のキャプションを取得し、それに応じて位置を調整します。

- **範囲** スピンボタンの最大位置と最小位置を変更できます。 既定では、最大値は0に設定され、最小値は100に設定されます。 既定の最大値は既定の最小値よりも小さいので、矢印ボタンの操作は "カウンタ-直観的" になります。 通常は、 [SetRange](../mfc/reference/cspinbuttonctrl-class.md#setrange) メンバー関数を使用して範囲を設定します。 範囲をクエリするには、 [GetRange](../mfc/reference/cspinbuttonctrl-class.md#getrange)を使用します。

## <a name="see-also"></a>関連項目

[CSpinButtonCtrl の使い方](../mfc/using-cspinbuttonctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
