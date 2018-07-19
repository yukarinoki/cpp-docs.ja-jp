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
ms.openlocfilehash: f76fbe9f85d978a5c2865b48720588b620508a07
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951053"
---
# <a name="slider-control-styles"></a>スライダー コントロールのスタイル
スライダー コントロール ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) 垂直または水平方向の方向を持つことができます。 いずれかの側では、目盛りはことができます、側またはどちらもします。 また、連続する値の範囲を指定するも使用できます。 これらのプロパティは、スライダー コントロールを作成する場合を指定するスライダー コントロールのスタイルを使用して制御されます。  
  
 TBS_HORZ と TBS_VERT のスタイルは、スライダー コントロールの向きを決定します。 印刷の向きを指定しない場合、スライダー コントロールを横向きにします。  
  
 TBS_AUTOTICKS スタイルでは、値の範囲が、各インクリメントに目盛りをスライダー コントロールを作成します。 呼び出すと、これらの目盛りが自動的に追加されます、 [SetRange](../mfc/reference/csliderctrl-class.md#setrange)メンバー関数。 TBS_AUTOTICKS を指定しない場合、メンバー関数をなど、使用できる[SetTic](../mfc/reference/csliderctrl-class.md#settic)と[SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)目盛りの位置を指定します。 目盛りを表示しないスライダー コントロールを作成するには、TBS_NOTICKS スタイルを使用できます。  
  
 スライダー コントロールのいずれかまたは両方の側では、目盛りを表示できます。 水平スライダー コントロールの TBS_BOTTOM または TBS_TOP のスタイルを指定できます。 スライダー コントロールの TBS_RIGHT または TBS_LEFT のスタイルを指定できます。 (TBS_BOTTOM と TBS_RIGHT は既定の設定) です。任意の方向にスライダー コントロールの両方の側に目盛りは、TBS_BOTH スタイルを指定します。  
  
 スライダー コントロールは、作成するときに、TBS_ENABLESELRANGE スタイルを指定する場合にのみ、選択範囲を表示できます。 スライダー コントロールがこのスタイルを持つは、選択範囲の開始と終了位置にある目盛りは (垂直のダッシュ) ではなく三角形として表示され、選択範囲が強調表示されます。 たとえば、選択範囲は、単純なスケジュールのアプリケーションで便利な可能性があります。 ユーザーは、ミーティングの時間を識別する日の時間に対応する目盛りの範囲を選択できます。  
  
 既定では、スライダー コントロールのスライダーの長さは、選択範囲の変化に応じて異なります。 スライダー コントロールに TBS_FIXEDLENGTH スタイルがある場合は、スライダーの長さは同じ選択範囲が変更された場合でもです。 TBS_NOTHUMB スタイルを持つスライダー コントロールでは、スライダーは含まれません。  
  
## <a name="see-also"></a>関連項目  
 [CSliderCtrl の使い方](../mfc/using-csliderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

