---
title: MINMAXINFO 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- MINMAXINFO
dev_langs:
- C++
helpviewer_keywords:
- MINMAXINFO structure [MFC]
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf9a6e6a1397b9361df5372af09be8e61d997e62
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/02/2018
ms.locfileid: "37337815"
---
# <a name="minmaxinfo-structure"></a>MINMAXINFO 構造体
`MINMAXINFO`構造体には、ウィンドウの最大サイズと位置、および追跡の最小値と最大サイズに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagMINMAXINFO {  
    POINT ptReserved;  
    POINT ptMaxSize;  
    POINT ptMaxPosition;  
    POINT ptMinTrackSize;  
    POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *ptReserved*  
 内部使用のために予約されています。  
  
 *ptMaxSize*  
 最大の幅 (point.x) と、ウィンドウの最大の高さ (point.y) を指定します。  
  
 *ptMaxPosition*  
 最大表示されたウィンドウ (point.x) の左側の位置と最大化ウィンドウ (point.y) の上端の位置を指定します。  
  
 *ptMinTrackSize*  
 最小のトラッキングの幅 (point.x) と、ウィンドウの高さ (point.y) の追跡の最小値を指定します。  
  
 *ptMaxTrackSize*  
 トラッキングの幅 (point.x) の最大値、およびウィンドウの高さ (point.y) を追跡する最大値を指定します。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../../mfc/reference/cwnd-class.md#ongetminmaxinfo)

