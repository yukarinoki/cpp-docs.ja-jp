---
title: MessageHandler |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- MessageHandler
dev_langs:
- C++
helpviewer_keywords:
- MessageHandler function
ms.assetid: 8a0acf97-1b0d-4226-91b9-75446634a03c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74a5e50eae425340bcb0f9a455422b43db0be0b2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43207111"
---
# <a name="messagehandler"></a>MessageHandler
`MessageHandler` メッセージ マップに MESSAGE_HANDLER マクロの 2 番目のパラメーターで識別される関数の名前です。  
  
## <a name="syntax"></a>構文  
  
```  
 
    LRESULT 
    MessageHandler 
 (
    UINT uMsg,  
    WPARAM wParam,  
    LPARAM lParam,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>パラメーター  
 *uMsg*  
 メッセージを指定します。  
  
 *wParam*  
 追加のメッセージに固有の情報。  
  
 *lParam*  
 追加のメッセージに固有の情報。  
  
 *bHandled*  
 メッセージ マップ セット*bHandled*する前に TRUE を`MessageHandler`が呼び出されます。 場合`MessageHandler`、メッセージを完全に処理しない設定があります*bHandled*を FALSE に、メッセージは、さらに処理が必要かを示します。  
  
## <a name="return-value"></a>戻り値  
 メッセージの処理の結果。 成功した場合は 0 を返します。  
  
## <a name="remarks"></a>Remarks  
 このメッセージ ハンドラーを使用して、メッセージ マップの例は、次を参照してください。 [MESSAGE_HANDLER](reference/message-map-macros-atl.md#message_handler)します。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウの実装](../atl/implementing-a-window.md)   
 [メッセージ マップ](../atl/message-maps-atl.md)   
 [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)

