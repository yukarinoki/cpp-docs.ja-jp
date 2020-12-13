---
description: 詳細については、「リストコントロールスタイルの変更」を参照してください。
title: リスト コントロール スタイルの変更
ms.date: 11/04/2016
helpviewer_keywords:
- styles [MFC], CListCtrl
- CListCtrl class [MFC], styles
- CListCtrl class [MFC], changing styles
ms.assetid: be74a005-0795-417c-9056-f6342aa74b26
ms.openlocfilehash: a6712baf5ea1e161ec1fd73e25ea01fedd650670
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339736"
---
# <a name="changing-list-control-styles"></a>リスト コントロール スタイルの変更

リストコントロール ([CListCtrl](reference/clistctrl-class.md)) のウィンドウスタイルは、作成後いつでも変更できます。 ウィンドウのスタイルを変更することで、コントロールが使用するビューの種類を変更できます。 たとえば、エクスプローラーをエミュレートするために、コントロールを異なるビュー (アイコンビュー、リストビューなど) に切り替えるためのメニュー項目またはツールバーボタンを指定できます。

たとえば、ユーザーがメニュー項目を選択したときに、 [Getwindowlong](/windows/win32/api/winuser/nf-winuser-getwindowlongw) を呼び出して、コントロールの現在のスタイルを取得し、 [SetWindowLong](/windows/win32/api/winuser/nf-winuser-setwindowlongw) を呼び出してスタイルをリセットすることができます。 詳細については、「Windows SDK での [リストビューコントロールの使用](/windows/win32/Controls/using-list-view-controls) 」を参照してください。

使用可能なスタイルは、[ [作成](reference/clistctrl-class.md#create)中に一覧表示されます。 スタイル **LVS_ICON**、 **LVS_SMALLICON**、 **LVS_LIST**、および **LVS_REPORT** は、4つのリストコントロールビューを指定します。

## <a name="extended-styles"></a>拡張スタイル

リストコントロールの標準スタイルに加えて、拡張スタイルと呼ばれる別のセットもあります。 Windows SDK の [拡張リストビュースタイル](/windows/win32/Controls/extended-list-view-styles) で説明したこれらのスタイルには、リストコントロールの動作をカスタマイズするための便利な機能がいくつか用意されています。 特定のスタイル (ホバー選択など) の動作を実装するには、必要なスタイルを渡して、 [CListCtrl:: SetExtendedStyle](reference/clistctrl-class.md#setextendedstyle)を呼び出します。 関数呼び出しの例を次に示します。

[!code-cpp[NVC_MFCControlLadenDialog#22](codesnippet/cpp/changing-list-control-styles_1.cpp)]

> [!NOTE]
> ホバー選択を機能させるには、 **LVS_EX_ONECLICKACTIVATE** または **LVS_EX_TWOCLICKACTIVATE** が有効になっている必要もあります。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](using-clistctrl.md)<br/>
[コントロール](controls-mfc.md)
