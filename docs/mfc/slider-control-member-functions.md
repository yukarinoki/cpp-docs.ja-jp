---
description: '詳細情報: スライダーコントロールのメンバー関数'
title: スライダー コントロールのメンバー関数
ms.date: 11/04/2016
helpviewer_keywords:
- CSliderCtrl class [MFC], methods
- slider controls [MFC], member functions
ms.assetid: dbde49ee-7306-4d14-a6ce-d09aa198178f
ms.openlocfilehash: 57108872a779bc4876be89afd5b81008f69a0837
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216900"
---
# <a name="slider-control-member-functions"></a>スライダー コントロールのメンバー関数

アプリケーションは、スライダーコントロールのメンバー関数を呼び出して、スライダーコントロール ([csliderctrl 使い方](../mfc/reference/csliderctrl-class.md)) に関する情報を取得し、その特性を変更することができます。

スライダーの位置 (つまり、ユーザーが選択した値) を取得するには、 [GetPos](../mfc/reference/csliderctrl-class.md#getpos) メンバー関数を使用します。 スライダーの位置を設定するには、 [SetPos](../mfc/reference/csliderctrl-class.md#setpos) メンバー関数を使用します。 メンバー関数を使用すると、 `VerifyPos` スライダーが最小値と最大値の間にあることをいつでも確認できます。

スライダーコントロールの範囲は、スライダーコントロールが表すことができる連続した値のセットです。 ほとんどのアプリケーションは、最初に作成されるときに、 [SetRange](../mfc/reference/csliderctrl-class.md#setrange) メンバー関数を使用してスライダーコントロールの範囲を設定します。 アプリケーションでは、 [SetRangeMax](../mfc/reference/csliderctrl-class.md#setrangemax) および [SetRangeMin](../mfc/reference/csliderctrl-class.md#setrangemin) メンバー関数を使用して、スライダーコントロールが作成された後に範囲を動的に変更できます。 範囲を動的に変更できるアプリケーションは、通常、ユーザーがスライダーコントロールの操作を終了したときに最終的な範囲の設定を取得します。 これらの設定を取得するには、 [GetRange](../mfc/reference/csliderctrl-class.md#getrange)、 [GetRangeMax](../mfc/reference/csliderctrl-class.md#getrangemax)、および [GetRangeMin](../mfc/reference/csliderctrl-class.md#getrangemin) の各メンバー関数を使用します。

アプリケーションでは、TBS_AUTOTICKS スタイルを使用して、スライダーコントロールの目盛りを自動的に表示することができます。 ただし、アプリケーションで目盛りの位置または頻度を制御する必要がある場合は、いくつかのメンバー関数を使用できます。

目盛りの位置を設定するには、アプリケーションで [Settic](../mfc/reference/csliderctrl-class.md#settic) メンバー関数を使用します。 [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)メンバー関数を使用すると、アプリケーションは、スライダーコントロールの範囲内の一定の間隔で表示される目盛りを設定できます。 たとえば、アプリケーションでは、このメンバー関数を使用して、1 ~ 100 の範囲で10目盛りだけを表示できます。

目盛りに対応する範囲のインデックスを取得するには、 [gettic](../mfc/reference/csliderctrl-class.md#gettic) メンバー関数を使用します。 [Getの配列](../mfc/reference/csliderctrl-class.md#getticarray)メンバー関数は、これらのインデックスの配列を取得します。 クライアント座標で、目盛りの位置を取得するには、 [Getて pos](../mfc/reference/csliderctrl-class.md#getticpos) メンバー関数を使用します。 アプリケーションでは、 [GetNumTics](../mfc/reference/csliderctrl-class.md#getnumtics) メンバー関数を使用して目盛りの数を取得できます。

[ClearTics](../mfc/reference/csliderctrl-class.md#cleartics)メンバー関数は、スライダーコントロールのすべての目盛りを削除します。

アプリケーションが TB_LINEDOWN または TB_LINEUP 通知メッセージを受信したときのスライダーの移動距離は、スライダーコントロールの線のサイズによって決まります。 同様に、ページサイズによって、TB_PAGEDOWN および TB_PAGEUP 通知メッセージへの応答が決定されます。 アプリケーションでは、 [Getlinesize](../mfc/reference/csliderctrl-class.md#getlinesize)、 [setlinesize](../mfc/reference/csliderctrl-class.md#setlinesize)、 [GetPageSize](../mfc/reference/csliderctrl-class.md#getpagesize)、および [setpagesize](../mfc/reference/csliderctrl-class.md#setpagesize) メンバー関数を使用して、行およびページサイズの値を取得および設定できます。

アプリケーションでは、メンバー関数を使用して、スライダーコントロールの寸法を取得できます。 [GetThumbRect](../mfc/reference/csliderctrl-class.md#getthumbrect)メンバー関数は、スライダーの外接する四角形を取得します。 [Getchannelrect](../mfc/reference/csliderctrl-class.md#getchannelrect)メンバー関数は、スライダーコントロールのチャネルの外接する四角形を取得します。 (チャネルは、スライダーが移動する領域であり、範囲が選択されている場合は強調表示を含みます)。

スライダーコントロールに TBS_ENABLESELRANGE スタイルが指定されている場合、ユーザーは連続した値の範囲を選択できます。 多数のメンバー関数を使用すると、選択範囲を動的に調整できます。 [Setselection](../mfc/reference/csliderctrl-class.md#setselection)メンバー関数は、選択範囲の開始位置と終了位置を設定します。 ユーザーが選択範囲の設定を完了すると、アプリケーションは [Getselection](../mfc/reference/csliderctrl-class.md#getselection) メンバー関数を使用して設定を取得できます。 ユーザーの選択をクリアするには、 [Clearsel](../mfc/reference/csliderctrl-class.md#clearsel) メンバー関数を使用します。

## <a name="see-also"></a>関連項目

[CSliderCtrl の使い方](../mfc/using-csliderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
