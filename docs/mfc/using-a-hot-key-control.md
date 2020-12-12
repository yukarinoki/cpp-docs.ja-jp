---
description: 詳細については、「ホットキーコントロールの使用」を参照してください。
title: ホット キー コントロールの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- CHotKeyCtrl class [MFC], using
- hot key controls
ms.assetid: cdd6524b-cc43-447f-b151-164273559685
ms.openlocfilehash: 078cd4b3d4746723d5996959edad20dd44e9abec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202705"
---
# <a name="using-a-hot-key-control"></a>ホット キー コントロールの使い方

通常、ホットキーコントロールの使用方法は次のパターンに従います。

- コントロールが作成されます。 ダイアログボックステンプレートでコントロールが指定されている場合、ダイアログボックスが作成されると、作成が自動的に作成されます。 (ホットキーコントロールに対応する [CHotKeyCtrl](../mfc/reference/chotkeyctrl-class.md) メンバーが dialog クラスに存在している必要があります)。または、 [create](../mfc/reference/chotkeyctrl-class.md#create) member 関数を使用して、ウィンドウの子ウィンドウとしてコントロールを作成することもできます。

- コントロールの既定値を設定する場合は、 [Sethotkey](../mfc/reference/chotkeyctrl-class.md#sethotkey) メンバー関数を呼び出します。 特定のシフト状態を禁止する場合は、 [SetRules](../mfc/reference/chotkeyctrl-class.md#setrules)を呼び出します。 ダイアログボックス内のコントロールについては、ダイアログボックスの [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 関数を使用することをお勧めします。

- ユーザーは、ホットキーコントロールにフォーカスがあるときにホットキーの組み合わせを押すことによって、コントロールと対話します。 その後、ユーザーは、ダイアログボックスのボタンをクリックして、このタスクが完了したことを示します。

- ユーザーがホットキーを選択したことがプログラムに通知されたら、メンバー関数 [GetHotKey](../mfc/reference/chotkeyctrl-class.md#gethotkey) を使用して、ホットキーコントロールから仮想キーとシフト状態の値を取得する必要があります。

- ユーザーが選択したキーがわかれば、「 [ホットキーの設定](../mfc/setting-a-hot-key.md)」で説明されているいずれかの方法を使用してホットキーを設定できます。

- ホットキーコントロールがダイアログボックス内にある場合、そのコントロールは `CHotKeyCtrl` 自動的に破棄されます。 それ以外の場合は、コントロールとオブジェクトの両方が正しく破棄されていることを確認する必要があり `CHotKeyCtrl` ます。

## <a name="see-also"></a>関連項目

[CHotKeyCtrl の使い方](../mfc/using-chotkeyctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
