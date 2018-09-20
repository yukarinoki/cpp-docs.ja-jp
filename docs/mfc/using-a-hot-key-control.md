---
title: ホット キー コントロールを使用して |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: be0d27016204724672c23f04fdee38f01b69e6a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372291"
---
# <a name="using-a-hot-key-control"></a>ホット キー コントロールの使い方

ホット キー コントロールの一般的な使用方法では、次のパターンに従います。

- コントロールが作成されます。 コントロールがダイアログ ボックスのテンプレートで指定されている場合、ダイアログ ボックスが作成されると作成は自動です。 (必要、 [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md)ホット キー コントロールに対応するダイアログ クラスのメンバーです)。また、使用することができます、[作成](../mfc/reference/chotkeyctrl-class.md#create)メンバー関数は、すべてのウィンドウの子ウィンドウとして、コントロールを作成します。

- コントロールの既定値を設定する場合は、呼び出し、 [SetHotKey](../mfc/reference/chotkeyctrl-class.md#sethotkey)メンバー関数。 特定のシフト状態を禁止する場合は、呼び出す[SetRules](../mfc/reference/chotkeyctrl-class.md#setrules)します。 これを行う適切な時刻は] ダイアログ ボックスで、[コントロール] ダイアログ ボックスの[OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog)関数。

- ユーザーは、ホット キー コントロールにフォーカスがある場合は、ホット キーの組み合わせを押すと、コントロールと対話します。 ユーザー、何らかの方法であることを示しますこのタスク完了すると、おそらく ダイアログ ボックスのボタンをクリックしています。

- メンバー関数を使用するときに、プログラムには、ユーザーのホット キーが選択されている通知、 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey)ホット キー コントロールから、仮想キーと shift キーの状態の値を取得します。

- 説明する方法のいずれかを使用して、ホット キーを設定することができます、ユーザーが選択したキーがわかったら、[ホット キーの設定](../mfc/setting-a-hot-key.md)します。

- ホット キー コントロールがダイアログ ボックスでは、場合、および`CHotKeyCtrl`オブジェクトが自動的に破棄されます。 かどうか、する必要があることに、両方のコントロールを確認し、`CHotKeyCtrl`オブジェクトが破棄されました。

## <a name="see-also"></a>関連項目

[CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)

