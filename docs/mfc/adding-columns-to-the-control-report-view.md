---
title: 制御 (レポート ビュー) に列を追加 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CListCtrl class [MFC], adding columns
- report view in CListCtrl class [MFC]
- views [MFC], report
- columns [MFC], adding to CListCtrl
- CListCtrl class [MFC], report view
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 975d65119ba0ae24b236d96cbe67e73b70be6bac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33341830"
---
# <a name="adding-columns-to-the-control-report-view"></a>コントロールへの列の追加 (レポート ビュー)
> [!NOTE]
>  いずれかに、次の手順が適用されます、 [CListView](../mfc/reference/clistview-class.md)または[CListCtrl](../mfc/reference/clistctrl-class.md)オブジェクト。  
  
 リスト コントロールは、レポート ビューでは、ときに、各リスト コントロール項目のさまざまなサブ項目を整理するためのメソッドを提供する、列が表示されます。 リスト コントロール内の列と、リスト コントロール項目のサブ項目間の一対一の対応では、この組織が実装されます。 サブ項目の詳細については、次を参照してください。[コントロールへの項目の追加](../mfc/adding-items-to-the-control.md)です。 レポート ビューでのリスト コントロールの例は、Windows 95 および Windows 98 エクスプ ローラーの詳細ビューによって提供されます。 最初の列には、フォルダー、ファイルのアイコンとラベルが一覧表示します。 ファイルのサイズ、ファイルの種類、最後に変更された日付およびなど、他の列が一覧表示します。  
  
 コントロールがある場合にのみ列が表示されている場合でも、列は、いつでもリスト コントロールに追加できる、`LVS_REPORT`スタイル ビットがオンにします。  
  
 各列が関連付けられているヘッダー項目 (を参照してください[CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) オブジェクトを列にラベルし、列のサイズを変更することができます。  
  
 リスト コントロールでは、レポート ビューをサポートする場合は、リスト コントロール項目の考えられる各サブ項目の列を追加する必要があります。 列を追加するには、準備、 [LV_COLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743)構造とへの呼び出しを行う[InsertColumn](../mfc/reference/clistctrl-class.md#insertcolumn)です。 (ヘッダー項目とも呼ばれます) 必要な列を追加した後、それらを並べ替えることができますメンバー関数および埋め込みのヘッダー コントロールに属しているスタイルを使用します。 詳細については、次を参照してください。[ヘッダー コントロール項目の並べ替え](../mfc/ordering-items-in-the-header-control.md)です。  
  
> [!NOTE]
>  リスト コントロールが作成された場合、 **LVS_NOCOLUMNHEADER**列に挿入しようとすると、スタイルは無視されます。  
  
## <a name="see-also"></a>関連項目  
 [CListCtrl の使い方](../mfc/using-clistctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

