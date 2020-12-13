---
description: '詳細情報: CommandHandler'
title: CommandHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
ms.openlocfilehash: 746048dd83088cac8316cf6e0140644956c21b4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153285"
---
# <a name="commandhandler"></a>CommandHandler

`CommandHandler` は、メッセージマップ内の COMMAND_HANDLER マクロの3番目のパラメーターで識別される関数です。

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
ウィンドウコントロールを指定するハンドル。

*bHandled*<br/>
が呼び出される前に、メッセージマップによって *Bhandled* が TRUE に設定 `CommandHandler` されます。 `CommandHandler`がメッセージを完全に処理しない場合は、 *BHANDLED* を FALSE に設定して、メッセージにさらに処理が必要であることを示す必要があります。

## <a name="return-value"></a>戻り値

メッセージ処理の結果。 成功した場合は0。

## <a name="remarks"></a>解説

メッセージマップでこのメッセージハンドラーを使用する例については、「 [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler)」を参照してください。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)<br/>
[メッセージ マップ](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
