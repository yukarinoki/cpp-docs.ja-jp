---
description: 詳細については、「ツールヒントコントロールの操作」を参照してください。
title: ツール ヒント コントロールの操作
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], manipulating tool tip attributes
- tool tips [MFC], attributes
ms.assetid: 3600afe5-712a-4b56-8456-96e85fe879af
ms.openlocfilehash: f04a2a9fe7d9b32d4b0fab1c6fea0d82f48cbf1a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281068"
---
# <a name="manipulating-the-tool-tip-control"></a>ツール ヒント コントロールの操作

クラスに `CToolTipCtrl` は、 `CToolTipCtrl` オブジェクトとツールヒントウィンドウのさまざまな属性を制御するメンバー関数のグループが用意されています。

ツールヒントウィンドウの初期、ポップアップ、および再表示の期間は、 [Getdelaytime](reference/ctooltipctrl-class.md#getdelaytime) と [setdelaytime](reference/ctooltipctrl-class.md#setdelaytime)の呼び出しを使用して設定および取得できます。

ツールヒントウィンドウの外観を変更するには、次の関数を使用します。

- [Getmargin](reference/ctooltipctrl-class.md#getmargin) と [setmargin](reference/ctooltipctrl-class.md#setmargin) は、ツールヒントの境界線とツールヒントのテキストとの間の幅を取得して設定します。

- [Getmax? width](reference/ctooltipctrl-class.md#getmaxtipwidth) と [SetMaxTipWidth](reference/ctooltipctrl-class.md#setmaxtipwidth) は、ツールヒントウィンドウの最大の幅を取得して設定します。

- [Gettipbkcolor](reference/ctooltipctrl-class.md#gettipbkcolor) および [settipbkcolor](reference/ctooltipctrl-class.md#settipbkcolor) は、ツールヒントウィンドウの背景色を取得して設定します。

- [Gettip textcolor](reference/ctooltipctrl-class.md#gettiptextcolor) および [settip textcolor](reference/ctooltipctrl-class.md#settiptextcolor) ツールヒントウィンドウのテキストの色を取得して設定します。

WM_LBUTTONXXX メッセージなどの重要なメッセージがツールヒントコントロールに通知されるようにするには、メッセージをツールヒントコントロールに中継する必要があります。 このリレーに最適な方法は、[所有者] ウィンドウの関数で [CToolTipCtrl:: RelayEvent](reference/ctooltipctrl-class.md#relayevent)を呼び出すことです `PreTranslateMessage` 。 次の例は、考えられる1つのメソッドを示しています (ツールヒントコントロールが呼び出されていると仮定し `m_ToolTip` ます)。

[!code-cpp[NVC_MFCControlLadenDialog#41](codesnippet/cpp/manipulating-the-tool-tip-control_1.cpp)]

ツールヒントウィンドウをすぐに削除するには、 [Pop](reference/ctooltipctrl-class.md#pop) メンバー関数を呼び出します。

## <a name="see-also"></a>関連項目

[CToolTipCtrl の使い方](using-ctooltipctrl.md)<br/>
[コントロール](controls-mfc.md)
