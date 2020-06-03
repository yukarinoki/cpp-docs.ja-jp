---
title: リスト コントロール スタイルの変更
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: 5f45e0549c3fc0f5747f8dd12a6310fafd7dd7bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370814"
---
# <a name="changing-list-control-styles"></a>リスト コントロール スタイルの変更

リスト コントロールのウィンドウ スタイル ([CListCtrl](../mfc/reference/clistctrl-class.md)) は、作成後いつでも変更できます。 ウィンドウ スタイルを変更すると、コントロールで使用されるビューの種類が変更されます。 たとえば、エクスプローラをエミュレートするには、メニュー項目やツール バー ボタンを用意して、アイコン ビューやリスト ビューなど、さまざまなビュー間でコントロールを切り替えることができます。

たとえば、ユーザーがメニュー項目を選択したときに[、GetWindowLong](/windows/win32/api/winuser/nf-winuser-getwindowlongw)を呼び出してコントロールの現在のスタイルを取得し[、SetWindowLong](/windows/win32/api/winuser/nf-winuser-setwindowlongw)を呼び出してスタイルをリセットできます。 詳細については、Windows SDK[の「リスト ビュー コントロールの使用](/windows/win32/Controls/using-list-view-controls)」を参照してください。

使用可能なスタイルは、[[作成](../mfc/reference/clistctrl-class.md#create)] に一覧表示されます。 **スタイルLVS_ICON**、 **LVS_SMALLICON**、 **LVS_LIST**、および**LVS_REPORT** 4 つのリスト コントロール ビューを指定します。

## <a name="extended-styles"></a>拡張スタイル

リスト コントロールの標準スタイルに加えて、拡張スタイルと呼ばれる別のセットがあります。 Windows SDK の[「拡張リスト ビュー スタイル](/windows/win32/Controls/extended-list-view-styles)」で説明されているこれらのスタイルには、リスト コントロールの動作をカスタマイズする便利なさまざまな機能が用意されています。 特定のスタイルの動作 (ホバー選択など) を実装するには、必要なスタイルを渡して[CListCtrl::SetExtendedStyle](../mfc/reference/clistctrl-class.md#setextendedstyle)を呼び出します。 次の例は、関数呼び出しを示しています。

[!code-cpp[NVC_MFCControlLadenDialog#22](../mfc/codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
> ホバー選択を機能させるには **、LVS_EX_ONECLICKACTIVATE**または**LVS_EX_TWOCLICKACTIVATE**をオンにする必要があります。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
