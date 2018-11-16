---
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- NotifyHandler
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 72c8fa3a0773a67c32a0652eb048885564a734be
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2018
ms.locfileid: "51694609"
---
# <a name="notifyhandler"></a>NotifyHandler

メッセージ マップで NOTIFY_HANDLER マクロの 3 番目のパラメーターで識別される関数の名前。

## <a name="syntax"></a>構文

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>パラメーター

*idCtrl*<br/>
メッセージを送信するコントロールの識別子です。

*pnmh*<br/>
アドレス、 [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr)通知コードおよび追加情報を格納する構造体。 このパラメーターを持つより大きな構造体をポイントするいくつかの通知メッセージの`NMHDR`その最初のメンバーとして構造体。

*bHandled*<br/>
メッセージ マップ セット*bHandled*する前に TRUE を*NotifyHandler*が呼び出されます。 場合*NotifyHandler* 、メッセージを完全に処理しない設定があります*bHandled*に**FALSE**を示すメッセージがさらに処理を必要があります。

## <a name="return-value"></a>戻り値

メッセージの処理の結果。 成功した場合は 0 を返します。

## <a name="remarks"></a>Remarks

このメッセージ ハンドラーを使用して、メッセージ マップの例は、次を参照してください。 [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler))。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)<br/>
[メッセージ マップ](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
