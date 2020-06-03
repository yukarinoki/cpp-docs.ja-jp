---
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
ms.openlocfilehash: 0bc4df4c07ec4b8bc5b488925cbb140609302186
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365064"
---
# <a name="using-drop-down-buttons-in-a-toolbar-control"></a>ツール バー コントロールでのドロップダウン ボタンの使い方

標準のプッシュ ボタンに加えて、ツール バーにはドロップダウン ボタンを使用することもできます。 ドロップダウン ボタンは通常、付属の下矢印の存在によって示されます。

> [!NOTE]
> アタッチされた下向き矢印は、TBSTYLE_EX_DRAWDDARROWS拡張スタイルが設定されている場合にのみ表示されます。

ユーザーがこの矢印 (または矢印が存在しない場合はボタン自体) をクリックすると、TBN_DROPDOWN通知メッセージがツール バー コントロールの親に送信されます。 この通知を処理して、ポップアップ メニューを表示できます。は、インターネット エクスプローラの動作と同様です。

次の手順は、ポップアップ メニューを使用してドロップダウン ツール バー ボタンを実装する方法を示しています。

### <a name="to-implement-a-drop-down-button"></a>ドロップダウン ボタンを実装するには

1. オブジェクトを`CToolBarCtrl`作成したら、次のコードを使用してTBSTYLE_EX_DRAWDDARROWSスタイルを設定します。

   [!code-cpp[NVC_MFCControlLadenDialog#36](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_1.cpp)]

1. ドロップダウン ボタンに設定する新しいボタン[([挿入]](../mfc/reference/ctoolbarctrl-class.md#insertbutton)ボタンまたは[[ボタンの追加](../mfc/reference/ctoolbarctrl-class.md#addbuttons)] ) または既存の ([SetButtonInfo](../mfc/reference/ctoolbarctrl-class.md#setbuttoninfo)) ボタンにTBSTYLE_DROPDOWNスタイルを設定します。 次の例は、オブジェクト内の既存のボタンを`CToolBarCtrl`変更する方法を示しています。

   [!code-cpp[NVC_MFCControlLadenDialog#37](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_2.cpp)]

1. ツール バー オブジェクトの親クラスにTBN_DROPDOWN ハンドラーを追加します。

   [!code-cpp[NVC_MFCControlLadenDialog#38](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_3.cpp)]

1. 新しいハンドラで、適切なポップアップメニューを表示します。 次のコードは、1 つのメソッドを示しています。

   [!code-cpp[NVC_MFCControlLadenDialog#39](../mfc/codesnippet/cpp/using-drop-down-buttons-in-a-toolbar-control_4.cpp)]

## <a name="see-also"></a>関連項目

[CToolBarCtrl の使い方](../mfc/using-ctoolbarctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
