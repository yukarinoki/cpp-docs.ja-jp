---
title: ヘッダー項目に対するドラッグ アンド ドロップのサポート
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: 21ff14982baac93fac1cf3ee441353c079f4f760
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602970"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>ヘッダー項目に対するドラッグ アンド ドロップのサポート

ヘッダー項目に対するドラッグ アンド ドロップのサポートを提供するには、HDS_DRAGDROP 形式を指定します。 ヘッダー項目に対するドラッグ アンド ドロップのサポートにより、ユーザーは、ヘッダー コントロールのヘッダー項目の順序を変更できます。 既定の動作は、ヘッダー項目が削除された場合、ドラッグされているヘッダー項目の半透明のドラッグ イメージと、新しい位置のビジュアル インジケーターを提供します。

共通のドラッグ アンド ドロップ機能を備えたとしてに HDN_BEGINDRAG と HDN_ENDDRAG 通知を処理することによって既定のドラッグ アンド ドロップ動作を拡張できます。 オーバーライドすることで、ドラッグのイメージの外観をカスタマイズすることも、 [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage)メンバー関数。

> [!NOTE]
>  リスト コントロールの埋め込みヘッダー コントロールのドラッグ アンド ドロップのサポートを提供する場合は、拡張スタイル セクションを参照してください、[リスト コントロール スタイルの変更](../mfc/changing-list-control-styles.md)トピック。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)

