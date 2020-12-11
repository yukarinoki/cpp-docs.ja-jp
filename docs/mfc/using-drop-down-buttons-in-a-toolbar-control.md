---
description: 詳細については、「ツールバーコントロールでの Drop-Down ボタンの使用」を参照してください。
title: ツール バー コントロールでのドロップダウン ボタンの使い方
ms.date: 11/04/2016
f1_keywords:
- TBN_DROPDOWN
- TBSTYLE_EX_DRAWDDARROWS
helpviewer_keywords:
- CToolBarCtrl class [MFC], drop-down buttons
- toolbars [MFC], drop-down buttons
- drop-down buttons in toolbars
- TBSTYLE_EX_DRAWDDARROWS
- TBN_DROPDOWN notification [MFC]
ms.assetid: b859f758-d2f6-40d9-9c26-0ff61993b9b2
ms.openlocfilehash: a37f39397f6b6f66bed1ad1d2fbd9530b55f3d7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154462"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>ツール バー コントロールでのドロップダウン ボタンの使い方

ツールバーには、標準のプッシュボタンに加えて、ドロップダウンボタンを含めることもできます。 ドロップダウンボタンは、通常、下向き矢印が付いていることによって示されます。

> [!NOTE]
> 接続された下矢印は TBSTYLE_EX_DRAWDDARROWS 拡張スタイルが設定されている場合にのみ表示されます。

ユーザーがこの矢印をクリックすると (またはボタン自体が矢印がない場合)、TBN_DROPDOWN 通知メッセージが toolbar コントロールの親に送信されます。 この通知を処理し、ポップアップメニューを表示することができます。Internet Explorer の動作に似ています。

次の手順は、ポップアップメニューを含むドロップダウンツールバーボタンを実装する方法を示しています。

### <a name="to-implement-a-drop-down-button"></a>ドロップダウンボタンを実装するには

1. `CToolBarCtrl`オブジェクトが作成されたら、次のコードを使用して TBSTYLE_EX_DRAWDDARROWS スタイルを設定します。

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. ドロップダウンボタンとなる新規 ([Insertbutton](../mfc/reference/ctoolbarctrl-class.md#insertbutton) または [addbuttons](../mfc/reference/ctoolbarctrl-class.md#addbuttons)) または既存の ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) ボタンの TBSTYLE_DROPDOWN スタイルを設定します。 次の例は、オブジェクトの既存のボタンを変更する方法を示してい `CToolBarCtrl` ます。

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. ツールバーオブジェクトの親クラスに TBN_DROPDOWN ハンドラーを追加します。

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. 新しいハンドラーで、適切なポップアップメニューを表示します。 次のコードは、1つのメソッドを示しています。

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
