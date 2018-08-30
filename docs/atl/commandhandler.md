---
title: CommandHandler |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CommandHandler
dev_langs:
- C++
helpviewer_keywords:
- CommandHandler function
ms.assetid: 662bc7bf-4a10-42b3-986d-d8bae4f63551
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ad124f0819dbfd9cfd0117cb91fbcffba05a400
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201277"
---
# <a name="commandhandler"></a>CommandHandler
`CommandHandler` 関数は、メッセージ マップに COMMAND_HANDLER マクロの 3 番目のパラメーターによって識別されます。  
  
## <a name="syntax"></a>構文  
  
```  
 
    LRESULT 
    CommandHandler 
 (
    WORD wNotifyCode,  
    WORD wID,  
    HWND hWndCtl,  
    BOOL& bHandled);
```  
  
#### <a name="parameters"></a>パラメーター  
 *wNotifyCode*  
 通知コード。  
  
 *wID*  
 メニュー項目、コントロール、またはアクセラレータの識別子。  
  
 *hWndCtl*  
 ウィンドウ コントロールへのハンドル。  
  
 *bHandled*  
 メッセージ マップ セット*bHandled*する前に TRUE を`CommandHandler`が呼び出されます。 場合`CommandHandler`、メッセージを完全に処理しない設定があります*bHandled*を FALSE に、メッセージは、さらに処理が必要かを示します。  
  
## <a name="return-value"></a>戻り値  
 メッセージの処理の結果。 成功した場合は 0 を返します。  
  
## <a name="remarks"></a>Remarks  
 このメッセージ ハンドラーを使用して、メッセージ マップの例は、次を参照してください。 [COMMAND_HANDLER](reference/message-map-macros-atl.md#command_handler)します。  
  
## <a name="see-also"></a>関連項目  
 [ウィンドウの実装](../atl/implementing-a-window.md)   
 [メッセージ マップ](../atl/message-maps-atl.md)   
 [WM_NOTIFY](https://msdn.microsoft.com/library/windows/desktop/bb775583)

