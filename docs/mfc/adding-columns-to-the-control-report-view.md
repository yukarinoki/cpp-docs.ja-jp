---
title: コントロールへの列の追加 (レポート ビュー)
ms.date: 11/04/2016
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
ms.openlocfilehash: d414c5f597628576916c5091fa63a4bf673c8c44
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394832"
---
# <a name="adding-columns-to-the-control-report-view"></a>コントロールへの列の追加 (レポート ビュー)

> [!NOTE]
>  次の手順は、いずれかには、 [CListView](../mfc/reference/clistview-class.md)または[CListCtrl](../mfc/reference/clistctrl-class.md)オブジェクト。

リスト コントロールがレポートの表示とリスト コントロールの各項目のさまざまなサブ項目を整理するためのメソッドを提供する列が表示されます。 この組織は、リスト コントロール内の列と、リスト コントロール項目のサブ項目間の一対一の対応で実装されます。 サブ項目の詳細については、次を参照してください。[コントロールへの項目の追加](../mfc/adding-items-to-the-control.md)します。 レポート ビューで、リスト コントロールの例は、Windows 95 および Windows 98 のエクスプ ローラーの詳細ビューによって提供されます。 最初の列には、フォルダー、ファイルのアイコン、およびラベルが表示されます。 ファイルのサイズ、ファイルの種類、最終変更日、日付およびなど、他の列が一覧表示します。

コントロールがある場合にのみ列が表示されている場合でも、いつでもリスト コントロールに列を追加できる、`LVS_REPORT`スタイル ビットがオンにします。

各列に関連付けられているヘッダー項目 (を参照してください[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) オブジェクト、列にラベルを列のサイズを変更することができます。

リスト コントロールでは、レポート ビューをサポートする場合は、リスト コントロールの項目で可能な各サブ項目の列を追加する必要があります。 準備して列を追加、 [LV_COLUMN](/windows/desktop/api/commctrl/ns-commctrl-taglvcolumna)構造とを呼び出すし[InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn)します。 (ヘッダー項目とも呼ばれます) 必要な列を追加した後、それらを並べ替えることができますメンバー関数および埋め込みのヘッダー コントロールに属しているスタイルを使用します。 詳細については、次を参照してください。[ヘッダー コントロール項目の並べ替え](../mfc/ordering-items-in-the-header-control.md)します。

> [!NOTE]
>  リスト コントロールが作成された場合、 **LVS_NOCOLUMNHEADER**列を挿入しようとすると、スタイルは無視されます。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
