---
title: ヘッダー項目に対するドラッグ アンド ドロップのサポート
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: 8dfaabf3da62c216d3da662f59c57b63e695d9ad
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371160"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>ヘッダー項目に対するドラッグ アンド ドロップのサポート

ヘッダー項目のドラッグ アンド ドロップのサポートを提供するには、HDS_DRAGDROPスタイルを指定します。 ヘッダー項目のドラッグ アンド ドロップのサポートにより、ヘッダー コントロールのヘッダー項目を並べ替えることができます。 既定の動作では、ドラッグされるヘッダー項目の半透明のドラッグ イメージと、ヘッダー項目がドロップされた場合は、新しい位置を示す視覚的なインジケーターが提供されます。

一般的なドラッグ アンド ドロップ機能と同様に、HDN_BEGINDRAGとHDN_ENDDRAG通知を処理することで、既定のドラッグ アンド ドロップ動作を拡張できます。 また、[メンバー](../mfc/reference/cheaderctrl-class.md#createdragimage)関数をオーバーライドして、ドラッグ イメージの外観をカスタマイズすることもできます。

> [!NOTE]
> リスト コントロールの埋め込みヘッダー コントロールに対してドラッグ アンド ドロップのサポートを提供する場合は、「[リスト コントロール スタイルの変更](../mfc/changing-list-control-styles.md)」の「拡張スタイル」セクションを参照してください。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)
