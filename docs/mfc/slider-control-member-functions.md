---
title: スライダー コントロールのメンバー関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3793ca47aa0537d5ca8d6858c165fc2c5ac64943
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="slider-control-member-functions"></a>スライダー コントロールのメンバー関数
アプリケーションをスライダー コントロールのメンバー関数を呼び出すスライダー コントロールの概要情報を取得する ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) とその特性を変更します。  
  
 (つまり、ユーザーが選択した値) のスライダーの位置を取得するには、使用、 [GetPos](../mfc/reference/csliderctrl-class.md#getpos)メンバー関数。 スライダーの位置を設定するには、使用、 [SetPos](../mfc/reference/csliderctrl-class.md#setpos)メンバー関数。 いつでも行うこともできます、`VerifyPos`メンバー関数をスライダーが最小と最大値の間にあるかどうかを確認します。  
  
 スライダー コントロールの範囲は、スライダー コントロールを表すことができる連続した値のセットです。 ほとんどのアプリケーションを使用して、 [SetRange](../mfc/reference/csliderctrl-class.md#setrange)が最初に作成されるときに、スライダー コントロールの範囲を設定します。 アプリケーションできますを動的に変更の範囲を使用して、スライダー コントロールを作成した後、 [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax)と[SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin)メンバー関数。 ユーザーがスライダー コントロールの操作を完了すると、通常動的に変更する範囲を許可するアプリケーションは最終的な範囲の設定を取得します。 これらの設定を取得するを使用して、 [GetRange](../mfc/reference/csliderctrl-class.md#getrange)、 [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax)、および[GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin)メンバー関数。  
  
 アプリケーションで使用できます、`TBS_AUTOTICKS`スタイルをスライダー コントロールの目盛りは、自動的に表示します。 アプリケーションは、位置またはティックの頻度を制御する必要があります、ただし、多くのメンバー関数が使用できます。  
  
 目盛りの位置を設定するアプリケーションで使用できます、 [SetTic](../mfc/reference/csliderctrl-class.md#settic)メンバー関数。 [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)メンバー関数は、アプリケーションに目盛りをスライダー コントロールの範囲内で一定の間隔で表示される設定を許可します。 たとえば、アプリケーションでは、1 ~ 100 の範囲の 10 個の目盛りを表示するのにこのメンバー関数を使用できます。  
  
 目盛りに対応する範囲内のインデックスを取得するを使用して、 [GetTic](../mfc/reference/csliderctrl-class.md#gettic)メンバー関数。 [GetTicArray](../mfc/reference/csliderctrl-class.md#getticarray)メンバー関数は、これらのインデックスの配列を取得します。 クライアント座標で表した目盛りの位置を取得するを使用して、 [GetTicPos](../mfc/reference/csliderctrl-class.md#getticpos)メンバー関数。 アプリケーションは、目盛りの数を取得して、 [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics)メンバー関数。  
  
 [ClearTics](../mfc/reference/csliderctrl-class.md#cleartics)メンバー関数では、すべてのスライダー コントロールの目盛りを削除します。  
  
 スライダー コントロールの行サイズは、アプリケーションが受信すると、スライダーが移動する距離を決定する**TB_LINEDOWN**または**TB_LINEUP**通知メッセージです。 同様に、ページ サイズによって決まりますへの応答、 **TB_PAGEDOWN**と**TB_PAGEUP**通知メッセージです。 アプリケーションを取得して、行とページ サイズ設定を使用して、 [GetLineSize](../mfc/reference/csliderctrl-class.md#getlinesize)、 [SetLineSize](../mfc/reference/csliderctrl-class.md#setlinesize)、 [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize)、および[SetPageSize](../mfc/reference/csliderctrl-class.md#setpagesize)メンバー関数。  
  
 アプリケーションは、スライダー コントロールのサイズを取得するのにメンバー関数を使用することができます。 [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect)メンバー関数は、スライダーの外接する四角形を取得します。 [GetChannelRect](../mfc/reference/csliderctrl-class.md#getchannelrect)メンバー関数は、スライダー コントロールのチャネルの外接する四角形を取得します。 (チャネルは、領域、スライダーが移動すると、範囲を選択すると、強調表示を含むです。)  
  
 スライダー コントロールがある場合、`TBS_ENABLESELRANGE`スタイル、ユーザーはそこから連続する値の範囲を選択することができます。 メンバー関数の数は、動的に調整されるように選択範囲を許可します。 [SetSelection](../mfc/reference/csliderctrl-class.md#setselection)メンバー関数は、開始と終了値選択範囲の位置を設定します。 ユーザーは、選択範囲の設定が完了したら、アプリケーション設定を使用して、 [GetSelection](../mfc/reference/csliderctrl-class.md#getselection)メンバー関数。 ユーザーの選択をクリアする、 [ClearSel](../mfc/reference/csliderctrl-class.md#clearsel)メンバー関数。  
  
## <a name="see-also"></a>関連項目  
 [CSliderCtrl の使い方](../mfc/using-csliderctrl.md)   
 [コントロール](../mfc/controls-mfc.md)

