---
title: ヘッダー項目に対するドラッグ アンド ドロップのサポートを提供する |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HDS_DRAGDROP style
- header items in header controls
- CHeaderCtrl class [MFC], drag and drop support
- HDN_ notifications [MFC]
ms.assetid: 93a152ec-804f-488f-b260-b3a438d0dc0f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 50cd19d4828269d0591afd0b46768e9917b96906
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349345"
---
# <a name="providing-drag-and-drop-support-for-header-items"></a>ヘッダー項目に対するドラッグ アンド ドロップのサポート
ヘッダー項目に対するドラッグ アンド ドロップのサポートを提供する指定、`HDS_DRAGDROP`スタイル。 ヘッダー項目に対するドラッグ アンド ドロップのサポートは、ヘッダー コントロールのヘッダー項目の順序を変更する機能をユーザーに与えます。 既定の動作は、ヘッダー項目が削除された場合、ドラッグされているヘッダー項目の半透明のドラッグ イメージと、新しい位置の視覚インジケーターを提供します。  
  
 一般的なドラッグ アンド ドロップ機能により、処理することにより既定のドラッグ アンド ドロップの動作を拡張することができますと、 **HDN_BEGINDRAG**と**HDN_ENDDRAG**通知します。 オーバーライドすることで、ドラッグ イメージの外観をカスタマイズすることも、 [CHeaderCtrl::CreateDragImage](../mfc/reference/cheaderctrl-class.md#createdragimage)メンバー関数。  
  
> [!NOTE]
>  埋め込みヘッダー内のコントロール リスト コントロールをドラッグ アンド ドロップのサポートを提供する場合は、拡張スタイル」を参照してください、[リスト コントロール スタイルの変更](../mfc/changing-list-control-styles.md)トピックです。  
  
## <a name="see-also"></a>関連項目  
 [CHeaderCtrl の使い方](../mfc/using-cheaderctrl.md)

