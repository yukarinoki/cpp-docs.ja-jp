---
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: 1acd56357f9ce234e3c479fd8fa88c1ed8407878
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818233"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler` メッセージ マップに MESSAGE_HANDLER マクロの 2 番目のパラメーターで識別される関数の名前です。

## <a name="syntax"></a>構文

```
LRESULT MessageHandler(
    UINT uMsg,
    WPARAM wParam,
    LPARAM lParam,
    BOOL& bHandled);
```

### <a name="parameters"></a>パラメーター

*uMsg*<br/>
メッセージを指定します。

*wParam*<br/>
追加のメッセージに固有の情報。

*lParam*<br/>
追加のメッセージに固有の情報。

*bHandled*<br/>
メッセージ マップ セット*bHandled*する前に TRUE を`MessageHandler`が呼び出されます。 場合`MessageHandler`、メッセージを完全に処理しない設定があります*bHandled*を FALSE に、メッセージは、さらに処理が必要かを示します。

## <a name="return-value"></a>戻り値

メッセージの処理の結果。 成功した場合は 0 を返します。

## <a name="remarks"></a>Remarks

このメッセージ ハンドラーを使用して、メッセージ マップの例は、[MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler)を参照してください。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)<br/>
[メッセージ マップ](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/desktop/controls/wm-notify)
