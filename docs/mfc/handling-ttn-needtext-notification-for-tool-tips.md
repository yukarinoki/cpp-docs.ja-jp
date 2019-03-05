---
title: ツール ヒント用 TTN_NEEDTEXT 通知の処理
ms.date: 11/04/2016
f1_keywords:
- TTN_NEEDTEXT
helpviewer_keywords:
- TTN_NEEDTEXT message [MFC]
- notifications [MFC], tool tips
- tool tips [MFC], notifications
ms.assetid: d0370a65-21ba-4676-bcc5-8cf851bbb15c
ms.openlocfilehash: 97db98322cd7c0d14e46f54a055bbc646c90d785
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57268994"
---
# <a name="handling-ttnneedtext-notification-for-tool-tips"></a>ツール ヒント用 TTN_NEEDTEXT 通知の処理

一部として[ツール ヒントを有効にする](../mfc/enabling-tool-tips.md)、処理する、 **TTN_NEEDTEXT**オーナー ウィンドウのメッセージ マップに次のエントリを追加することによってメッセージ。

[!code-cpp[NVC_MFCControlLadenDialog#40](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_1.cpp)]

*memberFxn*<br/>
このボタンのテキストが必要なときに呼び出されるメンバー関数。

ツール ヒントの ID は常に 0 です。

次のようにクラス定義でハンドラー関数を宣言します。

[!code-cpp[NVC_MFCControlLadenDialog#53](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_2.h)]

斜体のパラメーターは。

*ID*<br/>
通知を送信したコントロールの識別子。 使用しません。 コントロールの id から取得されますが、 **NMHDR**構造体。

*pNMHDR*<br/>
ポインター、 [NMTTDISPINFO](/windows/desktop/api/commctrl/ns-commctrl-tagnmttdispinfoa)構造体。 この構造体についても説明でさらに[体](../mfc/tooltiptext-structure.md)します。

*pResult*<br/>
結果コードへのポインターを返す前に設定できます。 **TTN_NEEDTEXT**ハンドラーを無視することができます、 *pResult*パラメーター。

フォーム ビューの通知ハンドラーの例。

[!code-cpp[NVC_MFCControlLadenDialog#54](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_3.cpp)]

呼び出す`EnableToolTips`(から取得したこのフラグメント`OnInitDialog`)。

[!code-cpp[NVC_MFCControlLadenDialog#55](../mfc/codesnippet/cpp/handling-ttn-needtext-notification-for-tool-tips_4.cpp)]

## <a name="see-also"></a>関連項目

[CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)
