---
title: NotifyHandler |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- NotifyHandler
dev_langs:
- C++
helpviewer_keywords:
- NotifyHandler function
ms.assetid: 5ff953ec-de35-42bc-8b3c-d384d636c139
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdf9ad03df6a342d47919eb576227422f687d15b
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "43755632"
---
# <a name="notifyhandler"></a>NotifyHandler

メッセージ マップで NOTIFY_HANDLER マクロの 3 番目のパラメーターで識別される関数の名前。

## <a name="syntax"></a>構文

```  
LRESULT NotifyHandler(
    int idCtrl,  
    LPNMHDR pnmh,  
    BOOL& bHandled);
```

#### <a name="parameters"></a>パラメーター

*idCtrl*  
メッセージを送信するコントロールの識別子です。

*pnmh*  
アドレス、 [NMHDR](/windows/desktop/api/richedit/ns-richedit-_nmhdr)通知コードおよび追加情報を格納する構造体。 このパラメーターを持つより大きな構造体をポイントするいくつかの通知メッセージの`NMHDR`その最初のメンバーとして構造体。

*bHandled*  
メッセージ マップ セット*bHandled*する前に TRUE を*NotifyHandler*が呼び出されます。 場合*NotifyHandler* 、メッセージを完全に処理しない設定があります*bHandled*に**FALSE**を示すメッセージがさらに処理を必要があります。

## <a name="return-value"></a>戻り値

メッセージの処理の結果。 成功した場合は 0 を返します。

## <a name="remarks"></a>Remarks

このメッセージ ハンドラーを使用して、メッセージ マップの例は、次を参照してください。 [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler))。

## <a name="see-also"></a>関連項目

[ウィンドウの実装](../atl/implementing-a-window.md)   
[メッセージ マップ](../atl/message-maps-atl.md)   
[WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)
