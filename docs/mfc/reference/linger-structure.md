---
title: LINGER 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LINGER
dev_langs:
- C++
helpviewer_keywords:
- LINGER structure [MFC]
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f19ab7e05b4e27a3b00576339d0b60b37bdba4a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33374345"
---
# <a name="linger-structure"></a>LINGER 構造体
`LINGER`構造が操作に使用される、 **SO_LINGER**と**SO_DONTLINGER**のオプション`CAsyncSocket::GetSockOpt`です。  
  
## <a name="syntax"></a>構文  
  
```  
struct linger {  
    u_short l_onoff;            // option on/off  
    u_short l_linger;           // linger time  
};  
```  
  
## <a name="remarks"></a>コメント  
 設定、 **SO_DONTLINGER**オプションを使用するメンバー関数でのブロッキング**閉じる**未送信のデータを送信するを待っているときにします。 設定は、このオプションを設定**SO_LINGER**で**こと**を 0 に設定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winsock2.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)   
 [CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)

