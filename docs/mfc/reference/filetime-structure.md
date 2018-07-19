---
title: FILETIME 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- FILETIME
dev_langs:
- C++
helpviewer_keywords:
- FILETIME structure [MFC]
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b0d1128442300d3f6fc153733be8b23b9d69444d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375883"
---
# <a name="filetime-structure"></a>FILETIME 構造体
`FILETIME`構造体は 1601 年 1 月 1 日以降の 100 ナノ秒間隔の数を表す 64 ビット値。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _FILETIME {  
    DWORD dwLowDateTime;   /* low 32 bits */  
    DWORD dwHighDateTime;  /* high 32 bits */  
} FILETIME, *PFILETIME, *LPFILETIME;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *dwLowDateTime*  
 下位 32 ビットのファイル時刻を指定します。  
  
 *dwHighDateTime*  
 高 32 ビットのファイル時刻を指定します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** windef.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

