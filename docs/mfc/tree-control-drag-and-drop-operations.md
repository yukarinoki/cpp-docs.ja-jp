---
title: ツリー コントロールのドラッグ アンド ドロップ操作
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
ms.openlocfilehash: c7febeec513d8004df2bd1cc42e4e97e027e9f17
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57286310"
---
# <a name="tree-control-drag-and-drop-operations"></a>ツリー コントロールのドラッグ アンド ドロップ操作

ツリー コントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md))、ユーザーが項目のドラッグを開始すると、通知を送信します。 コントロールから送信、 [TVN_BEGINDRAG](/windows/desktop/Controls/tvn-begindrag)通知メッセージ、ユーザーがマウスの左ボタンを持つ項目をドラッグし、 [TVN_BEGINRDRAG](/windows/desktop/Controls/tvn-beginrdrag)ユーザーがドラッグを開始するときに通知メッセージ右側のボタン。 ツリー コントロール ツリーのコントロールに TVS_DISABLEDRAGDROP スタイルを指定することによりこれらの通知を送信することを防止できます。

呼び出して、ドラッグ操作中に表示するイメージを取得する、 [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage)メンバー関数。 ツリー コントロールでは、ドラッグされている項目のラベルに基づくドラッグ ビットマップを作成します。 ツリー コントロールのイメージ リストを作成します、ビットマップを追加しへのポインターを返します、 [CImageList](../mfc/reference/cimagelist-class.md)オブジェクト。

実際には、項目をドラッグするコードを用意する必要があります。 通常、イメージ リストの関数のドラッグの機能を使用して、処理、 [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove)と[WM_LBUTTONUP](/windows/desktop/inputdev/wm-lbuttonup) (または[WM_RBUTTONUP](/windows/desktop/inputdev/wm-rbuttonup))ドラッグ操作が開始された後に送信されるメッセージ。 イメージ リストの関数の詳細については、[CImageList](../mfc/reference/cimagelist-class.md)で、 *MFC リファレンス*と[イメージ リスト](/windows/desktop/controls/image-lists)Windows SDK にを参照してください。 ツリー コントロールの項目をドラッグすることの詳細については、[ツリー ビュー項目のドラッグ](/windows/desktop/Controls/tree-view-controls)、Windows SDK にもを参照してください。

ツリー コントロール項目のドラッグ アンド ドロップ操作のターゲットにする場合は、ターゲット項目を上にマウス カーソルが時に知っておく必要があります。 呼び出すことによって調べることができます、 [HitTest](../mfc/reference/ctreectrl-class.md#hittest)メンバー関数。 いずれかをポイントし、整数、またはのアドレスを指定する、 [TVHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvhittestinfo)マウス カーソルの現在の座標を含む構造体。 関数から制御が戻るとき、整数または構造体は、ツリーのコントロールに対する相対的なマウス カーソルの位置を示すフラグを格納します。 カーソルがツリー コントロールで項目の上にある場合は、構造体には、同様の項目のハンドルが含まれています。

ドラッグ アンド ドロップ操作の対象の項目は呼び出すことによってを指定することができます、 [SetItem](../mfc/reference/ctreectrl-class.md#setitem)メンバー関数は、状態を設定する、`TVIS_DROPHILITED`値。 この状態にある項目をドラッグ アンド ドロップ ターゲットを示すために使用するスタイルで描画します。

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
