---
title: Rebar コントロールとバンド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- rebar controls [MFC], working with bands in
- bands, in rebar controls
ms.assetid: b647e7a5-9ea7-48b1-8e5f-096d104748f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b1fac5f83f19fab37604a14e239cf505891c737f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349852"
---
# <a name="rebar-controls-and-bands"></a>Rebar コントロールとバンド
Rebar コントロールの主な目的は、子ウィンドウ、ダイアログのコモン コントロール、メニューのツールバー、およびなどのコンテナーとして動作することです。 このコンテインメントが「バンド」の概念によってサポートされています。 各 rebar バンド グリップ バー、ビットマップ、テキスト ラベル、および子ウィンドウの任意の組み合わせを含めることができます。  
  
 クラス`CReBarCtrl`が多くのメンバー関数を使用して取得するには、および特定 rebar バンドの情報を操作できます。  
  
-   [GetBandCount](../mfc/reference/crebarctrl-class.md#getbandcount) rebar コントロールでの現在のバンドの数を取得します。  
  
-   [GetBandInfo](../mfc/reference/crebarctrl-class.md#getbandinfo)を初期化、 **REBARBANDINFO**指定バンドからの情報を含む構造体。 対応する[SetBandInfo](../mfc/reference/crebarctrl-class.md#setbandinfo)メンバー関数。  
  
-   [GetRect](../mfc/reference/crebarctrl-class.md#getrect)指定バンドの外接する四角形を取得します。  
  
-   [な](../mfc/reference/crebarctrl-class.md#getrowcount)rebar コントロールでの帯域外行の数を取得します。  
  
-   [IDToIndex](../mfc/reference/crebarctrl-class.md#idtoindex)指定バンドのインデックスを取得します。  
  
-   [GetBandBorders](../mfc/reference/crebarctrl-class.md#getbandborders)バンドの境界線を取得します。  
  
 操作、に加えていくつかのメンバー関数は、特定の rebar バンドを操作できるものです。  
  
 [InsertBand](../mfc/reference/crebarctrl-class.md#insertband)と[DeleteBand](../mfc/reference/crebarctrl-class.md#deleteband)を追加および rebar バンドを削除します。 [MinimizeBand](../mfc/reference/crebarctrl-class.md#minimizeband)と[MaximizeBand](../mfc/reference/crebarctrl-class.md#maximizeband)特定 rebar バンドの現在のサイズに影響します。 [MoveBand](../mfc/reference/crebarctrl-class.md#moveband)特定 rebar バンドのインデックスを変更します。 [ShowBand](../mfc/reference/crebarctrl-class.md#showband)表示またはユーザーから rebar バンドを非表示します。  
  
 次の例では、ツールバー バンドを追加することを示します (`m_wndToolBar`)、既存の rebar コントロール (`m_wndReBar`)。 初期化することによって、帯域外が説明されている、`rbi`構造と呼び出すことで、`InsertBand`メンバー関数。  
  
 [!code-cpp[NVC_MFCControlLadenDialog#27](../mfc/codesnippet/cpp/rebar-controls-and-bands_1.cpp)]  
  
## <a name="see-also"></a>関連項目  
 [CReBarCtrl の使い方](../mfc/using-crebarctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

