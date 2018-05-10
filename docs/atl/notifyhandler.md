---
title: NotifyHandler |Microsoft ドキュメント
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
ms.openlocfilehash: 74fbdd99c162b4362339d8c1b45ddc281d30eeee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="notifyhandler"></a>NotifyHandler
3 番目のパラメーターで識別される関数の名前、`NOTIFY_HANDLER`メッセージ マップ マクロです。  
  
## <a name="syntax"></a>構文  
  
```  
 
    LRESULT 
    NotifyHandler 
 (
    int idCtrl,  
    LPNMHDR pnmh,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>パラメーター  
 `idCtrl`  
 メッセージを送信するコントロールの識別子。  
  
 *pnmh*  
 アドレス、 [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514)通知コードおよびその他の情報を含む構造体。 このパラメーターを持つより大きな構造体をポイントするいくつかの通知メッセージについて、 **NMHDR**構造はその最初のメンバーとして。  
  
 `bHandled`  
 メッセージ マップ セット`bHandled`に**TRUE**する前に*NotifyHandler*と呼びます。 場合*NotifyHandler* 、メッセージを完全に処理しませんに設定する必要があります`bHandled`に**FALSE**を示すメッセージがさらに処理を必要があります。  
  
## <a name="return-value"></a>戻り値  
 メッセージの処理の結果。 正常終了した場合は 0 を返します。  
  
## <a name="remarks"></a>コメント  
 メッセージ マップでこのメッセージ ハンドラーを使用しての例は、次を参照してください。 [NOTIFY_HANDLER](reference/message-map-macros-atl.md#notify_handler))。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウの実装](../atl/implementing-a-window.md)   
 [メッセージ マップ](../atl/message-maps-atl.md)   
 [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583)

