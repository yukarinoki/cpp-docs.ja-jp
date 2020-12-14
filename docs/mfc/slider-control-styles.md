---
description: '詳細情報: スライダーコントロールスタイル'
title: スライダー コントロールのスタイル
ms.date: 11/04/2016
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
ms.openlocfilehash: cec057683862212a4d999ec7d0488c5f2a0837cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216913"
---
# <a name="slider-control-styles"></a>スライダー コントロールのスタイル

スライダーコントロール ([csliderctrl 使い方](../mfc/reference/csliderctrl-class.md)) は、垂直方向または水平方向のどちらかを持つことができます。 どちらの側にも目盛りを設定できます。 また、連続する値の範囲を指定するために使用することもできます。 これらのプロパティは、スライダーコントロールを作成するときに指定するスライダーコントロールスタイルを使用して制御されます。

TBS_HORZ と TBS_VERT のスタイルによって、スライダーコントロールの向きが決まります。 向きを指定しない場合、スライダーコントロールは水平方向に向きます。

TBS_AUTOTICKS スタイルは、値の範囲内の各インクリメントに目盛りを持つスライダーコントロールを作成します。 これらの目盛りは、 [SetRange](../mfc/reference/csliderctrl-class.md#setrange) メンバー関数を呼び出すと自動的に追加されます。 TBS_AUTOTICKS を指定しない場合は、 [Settic](../mfc/reference/csliderctrl-class.md#settic) や [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)などのメンバー関数を使用して、目盛りの位置を指定できます。 目盛りを表示しないスライダーコントロールを作成するには、TBS_NOTICKS スタイルを使用します。

スライダーコントロールのいずれかまたは両方の側に目盛りを表示できます。 水平スライダーコントロールの場合は、TBS_BOTTOM または TBS_TOP スタイルを指定できます。 垂直スライダーコントロールの場合は、TBS_RIGHT または TBS_LEFT スタイルを指定できます。 (TBS_BOTTOM と TBS_RIGHT が既定の設定です)。スライダーコントロールの両側の目盛りについては、TBS_BOTH スタイルを指定します。

スライダーコントロールは、作成時に TBS_ENABLESELRANGE スタイルを指定した場合にのみ、選択範囲を表示できます。 スライダーコントロールにこのスタイルが設定されている場合、選択範囲の開始位置と終了位置にある目盛りは、(垂直ダッシュではなく) 三角形として表示され、選択範囲が強調表示されます。 たとえば、選択範囲は、単純なスケジューリングアプリケーションで役立つ場合があります。 ユーザーは、スケジュールされた会議時間を識別するために、1日の時間に相当する目盛りの範囲を選択できます。

既定では、スライダーコントロールのスライダーの長さは、選択範囲の変化に応じて変化します。 スライダーコントロールの TBS_FIXEDLENGTH スタイルが設定されている場合、選択範囲が変更されてもスライダーの長さは変わりません。 TBS_NOTHUMB スタイルを持つスライダーコントロールには、スライダーは含まれません。

## <a name="see-also"></a>関連項目

[CSliderCtrl の使い方](../mfc/using-csliderctrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
