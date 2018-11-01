---
title: ユーザー定義のハンドラー
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.handlers
helpviewer_keywords:
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_MESSAGE macro [MFC]
- user-defined handlers [MFC]
ms.assetid: 99478294-bef0-4ba7-a369-25a6abdcdb62
ms.openlocfilehash: 4d2102668b7cc964e6fe3bffdcc6931a2961a737
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50562254"
---
# <a name="user-defined-handlers"></a>ユーザー定義のハンドラー

関数プロトタイプに対応するマップ エントリを次に示します。

|マップ エントリ|関数プロトタイプ|
|---------------|------------------------|
|ON_MESSAGE (\<メッセージ >、 \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM, LPARAM)。|
|ON_REGISTERED_MESSAGE ( \<nMessageVariable >、 \<memberFxn >)|afx_msg LRESULT memberFxn (WPARAM, LPARAM)。|
|ON_THREAD_MESSAGE (\<メッセージ >、 \<memberFxn >)|afx_msg void memberFxn (WPARAM, LPARAM)。|
|ON_REGISTERED_THREAD_MESSAGE ( \<nMessageVariable >、 \<memberFxn >)|afx_msg void memberFxn (WPARAM, LPARAM)。|

## <a name="see-also"></a>関連項目

[メッセージ マップ](../../mfc/reference/message-maps-mfc.md)<br/>
[WM_ で始まるメッセージのハンドラー](../../mfc/reference/handlers-for-wm-messages.md)

