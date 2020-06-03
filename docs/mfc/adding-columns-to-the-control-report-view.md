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
ms.openlocfilehash: 34d7b62985748b9b9d741c083ec9b34fce06b309
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370872"
---
# <a name="adding-columns-to-the-control-report-view"></a>コントロールへの列の追加 (レポート ビュー)

> [!NOTE]
> 次のプロシージャは[、CListView](../mfc/reference/clistview-class.md)または[CListCtrl](../mfc/reference/clistctrl-class.md)のいずれかのオブジェクトに適用されます。

リスト コントロールがレポート ビューに表示されている場合、各リスト コントロール項目のさまざまなサブ項目を整理する方法を提供する列が表示されます。 この編成は、リスト コントロール内の列と、リスト コントロール項目の関連するサブ項目との間に 1 対 1 の対応関係を持って実装されます。 サブ項目の詳細については、「[コントロールへの項目の追加](../mfc/adding-items-to-the-control.md)」を参照してください。 レポート ビューのリスト コントロールの例は、Windows 95 および Windows 98 エクスプローラの [詳細] ビューで提供されています。 最初の列には、フォルダ、ファイル アイコン、ラベルが表示されます。 その他の列には、ファイルサイズ、ファイルの種類、最終更新日などが表示されます。

列は、リスト コントロールにいつでも追加できますが、コントロールのスタイル ビットがオンになっている場合にのみ、列が`LVS_REPORT`表示されます。

各列には、列にラベルを付け、ユーザーが列のサイズを変更できるようにするヘッダー項目[(CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)を参照) オブジェクトが関連付けられています。

リスト コントロールがレポート ビューをサポートしている場合は、リスト コントロール アイテムのサブ項目ごとに列を追加する必要があります。 [LVCOLUMN](/windows/win32/api/commctrl/ns-commctrl-lvcolumnw)構造体を準備し[、InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn)を呼び出して列を追加します。 必要な列 (ヘッダー項目とも呼ばれます) を追加した後、埋め込みヘッダー コントロールに属するメンバー関数とスタイルを使用して列を並べ替えることができます。 詳細については、「ヘッダー[コントロールでのアイテムの順序付け](../mfc/ordering-items-in-the-header-control.md)」を参照してください。

> [!NOTE]
> リスト コントロールが**LVS_NOCOLUMNHEADER**スタイルで作成された場合、列を挿入しようとすると無視されます。

## <a name="see-also"></a>関連項目

[CListCtrl の使い方](../mfc/using-clistctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
