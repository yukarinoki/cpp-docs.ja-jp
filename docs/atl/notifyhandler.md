---
description: '詳細情報: NotifyHandler'
title: NotifyHandler
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
ms.openlocfilehash: 1c08eaa91962fa9f6acf330de89334ad1224e582
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97159376"
---
# <a name="notifyhandler"></a>NotifyHandler

メッセージマップ内の NOTIFY_HANDLER マクロの3番目のパラメーターで識別される関数の名前。

## <a name="syntax"></a>構文

```cpp
LRESULT NotifyHandler(
    int idCtrl,
    LPNMHDR pnmh,
    BOOL& bHandled);
```

#### <a name="parameters"></a>パラメーター

*idCtrl*<br/>
メッセージを送信するコントロールの識別子。

*pnmh*<br/>
通知コードと追加情報を含む [NMHDR](/windows/win32/api/richedit/ns-richedit-nmhdr) 構造体のアドレス。 一部の通知メッセージでは、このパラメーターは、構造体が最初のメンバーとなる、より大きな構造体を指し `NMHDR` ます。

*bHandled*<br/>
メッセージマップは、 *Notifyhandler* が呼び出される前に、 *BHANDLED* を TRUE に設定します。 *Notifyhandler* がメッセージを完全に処理しない場合は、 *Bhandled* を **FALSE** に設定して、メッセージにさらに処理が必要であることを示す必要があります。

## <a name="return-value"></a>戻り値

メッセージ処理の結果。 成功した場合は0。

## <a name="remarks"></a>解説

メッセージマップでこのメッセージハンドラーを使用する例については、「 [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler))」を参照してください。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)<br/>
[メッセージ マップ](../atl/message-maps-atl.md)<br/>
[WM_NOTIFY](/windows/win32/controls/wm-notify)
