---
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CommandHandler
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: fe0871f9778d7a1f74bf74af6030d7f8162d3b79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611849"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` 関数は、メッセージ マップに COMMAND_HANDLER マクロの 3 番目のパラメーターによって識別されます。

## <a name="syntax"></a>構文

```cpp
LRESULT CommandHandler(
    WORD wNotifyCode,
    WORD wID,
    HWND hWndCtl,
    BOOL& bHandled);
```

#### <a name="parameters"></a>パラメーター

*wNotifyCode*<br/>
通知コード。

*wID*<br/>
メニュー項目、コントロール、またはアクセラレータの識別子。

*hWndCtl*<br/>
ウィンドウ コントロールへのハンドル。

*bHandled*<br/>
メッセージ マップ セット*bHandled*する前に TRUE を`CommandHandler`が呼び出されます。 場合`CommandHandler`、メッセージを完全に処理しない設定があります*bHandled*を FALSE に、メッセージは、さらに処理が必要かを示します。

## <a name="return-value"></a>戻り値

メッセージの処理の結果。 成功した場合は 0 を返します。

## <a name="remarks"></a>Remarks

このメッセージ ハンドラーを使用して、メッセージ マップの例は、次を参照してください。 [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler)します。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)<br/>
[メッセージ マップ](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)

