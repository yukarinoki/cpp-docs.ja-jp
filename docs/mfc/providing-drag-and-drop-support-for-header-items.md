---
description: '詳細情報: ヘッダー項目に対してドラッグアンドドロップのサポートを提供する'
title: ヘッダー項目に対するドラッグ アンド ドロップのサポート
ms.date: 11/04/2016
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
ms.openlocfilehash: ed42f61220ee2033dbc36e11c18664be3968dddd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248789"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>ヘッダー項目に対するドラッグ アンド ドロップのサポート

ヘッダー項目に対するドラッグアンドドロップのサポートを提供するには、HDS_DRAGDROP スタイルを指定します。 ヘッダー項目に対するドラッグアンドドロップのサポートにより、ユーザーはヘッダーコントロールのヘッダー項目を並べ替えることができます。 既定の動作では、ドラッグされているヘッダー項目の半透明のドラッグイメージと、ヘッダー項目が削除されたときの新しい位置の視覚的なインジケーターが提供されます。

一般的なドラッグアンドドロップ機能と同様に、HDN_BEGINDRAG および HDN_ENDDRAG 通知を処理することで、既定のドラッグアンドドロップ動作を拡張できます。 [CHeaderCtrl:: CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage)メンバー関数をオーバーライドして、ドラッグイメージの外観をカスタマイズすることもできます。

> [!NOTE]
> リストコントロールの埋め込みヘッダーコントロールに対してドラッグアンドドロップのサポートを提供する場合は、「 [リストコントロールスタイルの変更](../mfc/changing-list-control-styles.md) 」トピックの「拡張スタイル」セクションを参照してください。

## <a name="see-also"></a>関連項目

[CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)
