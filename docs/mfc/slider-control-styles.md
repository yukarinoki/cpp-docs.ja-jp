---
title: スライダー コントロールのスタイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fa099e050bd460756ff9e2584d37f9e628293f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380547"
---
# <a name="slider-control-styles"></a>スライダー コントロールのスタイル
スライダー コントロール ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) 垂直または水平方向の方向を持つことができます。 いずれかの側では、目盛りはことができます、側またはどちらもします。 また、連続する値の範囲を指定するも使用できます。 これらのプロパティは、スライダー コントロールを作成する場合を指定するスライダー コントロールのスタイルを使用して制御されます。  
  
 `TBS_HORZ`と`TBS_VERT`スタイルは、スライダー コントロールの向きを決定します。 印刷の向きを指定しない場合、スライダー コントロールを横向きにします。  
  
 `TBS_AUTOTICKS`スタイルは、値の範囲内の各インクリメントに目盛りをあるスライダー コントロールを作成します。 呼び出すと、これらの目盛りが自動的に追加されます、 [SetRange](../mfc/reference/csliderctrl-class.md#setrange)メンバー関数。 指定しない場合`TBS_AUTOTICKS`などのメンバー関数を使用することができます[SetTic](../mfc/reference/csliderctrl-class.md#settic)と[SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)目盛りの位置を指定します。 目盛りを表示しないスライダー コントロールを作成する際、`TBS_NOTICKS`スタイル。  
  
 スライダー コントロールのいずれかまたは両方の側では、目盛りを表示できます。 水平スライダー コントロールを指定できます、`TBS_BOTTOM`または`TBS_TOP`スタイル。 スライダー コントロールを指定できます、`TBS_RIGHT`または`TBS_LEFT`スタイル。 (`TBS_BOTTOM`と`TBS_RIGHT`既定の設定です)。任意の方向にスライダー コントロールの両方の側に目盛りは、指定、`TBS_BOTH`スタイル。  
  
 指定した場合にのみ、スライダー コントロールが選択範囲を表示できます、`TBS_ENABLESELRANGE`作成するときにスタイルを設定します。 スライダー コントロールがこのスタイルを持つは、選択範囲の開始と終了位置にある目盛りは (垂直のダッシュ) ではなく三角形として表示され、選択範囲が強調表示されます。 たとえば、選択範囲は、単純なスケジュールのアプリケーションで便利な可能性があります。 ユーザーは、ミーティングの時間を識別する日の時間に対応する目盛りの範囲を選択できます。  
  
 既定では、スライダー コントロールのスライダーの長さは、選択範囲の変化に応じて異なります。 スライダー コントロールがある場合、 **TBS_FIXEDLENGTH**スタイル、スライダーの長さはそのまま同じ場合でも、選択範囲を変更します。 スライダー コントロールを持つ、 **TBS_NOTHUMB**スタイルは、スライダーは含まれません。  
  
## <a name="see-also"></a>関連項目  
 [CSliderCtrl の使い方](../mfc/using-csliderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

