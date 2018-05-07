---
title: プログレス コントロールの操作 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 415061306c5e743b9ed95ee5c7105133d2e4d340
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="manipulating-the-progress-control"></a>プログレス コントロールの操作
プログレス コントロールの現在位置を変更する方法を次の 3 つが ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md))。  
  
-   位置は、事前設定された増分で変更できます。  
  
-   位置は、任意の大きさによって変更できます。  
  
-   位置は、特定の値に変更できます。  
  
### <a name="to-change-the-position-by-a-preset-amount"></a>プリセットの量での位置を変更するには  
  
1.  使用して、 [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)インクリメント値を設定するメンバー関数。 既定では、この値は 10 です。 通常、この値は、コントロールの初期設定の 1 つとして設定します。 ステップ値を負の値にすることができます。  
  
2.  使用して、 [StepIt](../mfc/reference/cprogressctrl-class.md#stepit)の位置をインクリメントするメンバー関数。 これにより、自動的に再描画するコントロール。  
  
    > [!NOTE]
    >  `StepIt` ラップする位置になります。 たとえば、20、ステップと 90 の場合、位置 1 の-100 の範囲を指定`StepIt`位置を 10 に設定されます。  
  
### <a name="to-change-the-position-by-an-arbitrary-amount"></a>任意の大きさで位置を変更するには  
  
1.  使用して、 [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos)位置を変更するメンバー関数。 `OffsetPos` 負の値を受け入れます。  
  
    > [!NOTE]
    >  `OffsetPos`、とは異なり`StepIt`、位置は折り返されません。 新しい位置を調整して、範囲内で維持されます。  
  
### <a name="to-change-the-position-to-a-specific-value"></a>特定の値に位置を変更するには  
  
1.  使用して、 [SetPos](../mfc/reference/cprogressctrl-class.md#setpos)位置を特定の値に設定するメンバー関数。 必要に応じて、新しい位置は範囲に収まるように調整されます。  
  
 通常、進行状況コントロールは、出力に対してのみ使用されます。 新しい値を指定せず、現在の位置を取得する[GetPos](../mfc/reference/cprogressctrl-class.md#getpos)です。  
  
## <a name="see-also"></a>関連項目  
 [CProgressCtrl の使い方](../mfc/using-cprogressctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

