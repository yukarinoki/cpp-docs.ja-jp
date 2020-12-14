---
description: 詳細については、「ツリーコントロールの通知メッセージ」を参照してください。
title: ツリー コントロールの通知メッセージ
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
ms.openlocfilehash: 899b6469a2de9a076dd33e62c5023f502448d45f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263986"
---
# <a name="tree-control-notification-messages"></a>ツリー コントロールの通知メッセージ

ツリーコントロール ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) は、次の通知メッセージを WM_NOTIFY メッセージとして送信します。

|通知メッセージ|説明|
|--------------------------|-----------------|
|TVN_BEGINDRAG|ドラッグアンドドロップ操作の開始を通知します|
|TVN_BEGINLABELEDIT|埋め込み先のラベル編集の開始を通知します|
|TVN_BEGINRDRAG|マウスの右ボタンを使用して、ドラッグアンドドロップ操作の開始を通知します。|
|TVN_DELETEITEM|特定の項目が削除されたことを通知します。|
|TVN_ENDLABELEDIT|ラベル編集の終了を通知します|
|TVN_GETDISPINFO|項目を表示するためにツリーコントロールが必要とする情報を要求します。|
|TVN_ITEMEXPANDED|親項目の子項目のリストが展開または折りたたまれていることを通知します。|
|TVN_ITEMEXPANDING|親項目の子項目のリストが展開または折りたたまれようとしていることを通知します。|
|TVN_KEYDOWN|キーボードイベントを通知します|
|TVN_SELCHANGED|選択内容がある項目から別の項目に変更されたことを通知します。|
|TVN_SELCHANGING|選択内容がある項目から別の項目に変更されようとしていることを通知します。|
|TVN_SETDISPINFO|アイテムに対して保持されている情報を更新する通知|

## <a name="see-also"></a>関連項目

[CTreeCtrl の使い方](../mfc/using-ctreectrl.md)<br/>
[コントロール](../mfc/controls-mfc.md)
