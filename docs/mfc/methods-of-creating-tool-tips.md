---
title: ツール ヒントの作成方法
ms.date: 11/04/2016
helpviewer_keywords:
- CToolTipCtrl class [MFC], creating tool tips
- tool tips [MFC], tool tip controls
- tool tips [MFC], creating
ms.assetid: b015e9f4-ddfb-49a4-a5a6-fa2d45e4d328
ms.openlocfilehash: 26f31705068df009e906d50451efa9ea6572d7e6
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/09/2020
ms.locfileid: "84625453"
---
# <a name="methods-of-creating-tool-tips"></a>ツール ヒントの作成方法

MFC には、ツールヒントコントロール ( [CWnd](reference/cwnd-class.md)、 [CToolBarCtrl](reference/ctoolbarctrl-class.md)、 [CToolTipCtrl](reference/ctooltipctrl-class.md) 、および[CMFCToolTipCtrl](reference/cmfctooltipctrl-class.md)) を作成および管理するための3つのクラスが用意されています。 これらのクラスのツールヒントメンバー関数は、Windows コモンコントロール API をラップします。 クラス `CToolBarCtrl` とクラス `CToolTipCtrl` は、クラスから派生 `CWnd` します。

`CWnd`には、ヒントヒント、[キャンセル](reference/cwnd-class.md#canceltooltips)ツールヒント、 [FilterToolTipMessage](reference/cwnd-class.md#filtertooltipmessage)、および[OnToolHitTest](reference/cwnd-class.md#ontoolhittest)の 4[つのメンバー](reference/cwnd-class.md#enabletooltips)関数が用意されています。 ツールヒントの実装方法の詳細については、これらの個々のメンバー関数を参照してください。

を使用してツールバーを作成した場合は `CToolBarCtrl` 、そのツールバーのツールヒントを、 [gettooltips](reference/ctoolbarctrl-class.md#gettooltips)および[settooltips](reference/ctoolbarctrl-class.md#settooltips)というメンバー関数を使用して直接実装できます。 ツールヒントの実装方法の詳細については、これらの個々のメンバー関数と[ツールヒントの通知の処理](handling-tool-tip-notifications.md)に関する説明を参照してください。

クラスは、 `CToolTipCtrl` Windows コモンツールヒントコントロールの機能を提供します。 1つのツールヒントコントロールで、複数のツールに関する情報を提供できます。 ツールは、子ウィンドウやコントロールなどのウィンドウ、またはウィンドウのクライアント領域内のアプリケーション定義の四角形領域のいずれかです。 [CMFCToolTipCtrl](reference/cmfctooltipctrl-class.md)クラスはから派生 `CToolTipCtrl` し、追加の視覚スタイルと機能を提供します。

## <a name="see-also"></a>関連項目

[CToolTipCtrl の使い方](using-ctooltipctrl.md)<br/>
[制限](controls-mfc.md)
