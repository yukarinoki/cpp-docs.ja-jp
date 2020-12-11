---
description: '詳細情報: MessageHandler'
title: MessageHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
ms.openlocfilehash: d369b94721e57eb4adc704570bc09d1aae184fe1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159506"
---
# <a name="messagehandler"></a>MessageHandler

`MessageHandler` メッセージマップ内の MESSAGE_HANDLER マクロの2番目のパラメーターで識別される関数の名前を指定します。

## <a name="syntax"></a>構文

```cpp
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
追加のメッセージ固有情報。

*lParam*<br/>
追加のメッセージ固有情報。

*bHandled*<br/>
が呼び出される前に、メッセージマップによって *Bhandled* が TRUE に設定 `MessageHandler` されます。 `MessageHandler`がメッセージを完全に処理しない場合は、 *BHANDLED* を FALSE に設定して、メッセージにさらに処理が必要であることを示す必要があります。

## <a name="return-value"></a>戻り値

メッセージ処理の結果。 成功した場合は0。

## <a name="remarks"></a>解説

メッセージマップでこのメッセージハンドラーを使用する例については、「 [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler)」を参照してください。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)<br/>
[メッセージ マップ](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
