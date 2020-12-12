---
description: 詳細については、「スライダーコントロールの使用」を参照してください。
title: スライダー コントロールの使い方
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], using
- slider controls
- slider controls [MFC], using
ms.assetid: 2b1a8ac8-2b17-41e1-aa24-83c1fd737049
ms.openlocfilehash: b9134d76261bf5c15bfef90260394ee6a4c760e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322662"
---
# <a name="using-slider-controls"></a>スライダー コントロールの使い方

スライダーコントロールの一般的な使用方法は、次のパターンに従います。

- コントロールが作成されます。 ダイアログボックステンプレートでコントロールが指定されている場合、ダイアログボックスが作成されると、作成が自動的に作成されます。 (スライダーコントロールに対応する [csliderctrl 使い方](../mfc/reference/csliderctrl-class.md) メンバーがダイアログクラスに存在している必要があります)。または、 [create](../mfc/reference/csliderctrl-class.md#create) member 関数を使用して、ウィンドウの子ウィンドウとしてコントロールを作成することもできます。

- さまざまな Set メンバー関数を呼び出して、コントロールの値を設定します。 加えられる変更には、スライダーの最小位置と最大位置の設定、目盛りの描画、選択範囲の設定、およびスライダーの位置変更が含まれます。 ダイアログボックス内のコントロールについては、ダイアログの [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) 関数を使用することをお勧めします。

- ユーザーがコントロールと対話すると、さまざまな通知メッセージが送信されます。 [GetPos](../mfc/reference/csliderctrl-class.md#getpos)メンバー関数を呼び出すことによって、コントロールからスライダー値を抽出できます。

- コントロールが完成したら、適切に破棄されていることを確認する必要があります。 スライダーコントロールがダイアログボックス内にある場合、そのコントロールは `CSliderCtrl` 自動的に破棄されます。 それ以外の場合は、コントロールとオブジェクトの両方が正しく破棄されていることを確認する必要があり `CSliderCtrl` ます。

## <a name="see-also"></a>関連項目

[CSliderCtrl の使い方](../mfc/using-csliderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
