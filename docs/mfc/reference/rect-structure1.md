---
title: RECT Structure1 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- LPRECT
- RECT
dev_langs:
- C++
helpviewer_keywords:
- RECT structure [MFC]
- LPRECT structure [MFC]
ms.assetid: 1b3160de-64e9-40d1-89eb-af3e0fd6acf0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b61c794b8fa383eeea62459a5a83948ef2efe10
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="rect-structure1"></a>RECT Structure1
`RECT` 構造体は、四角形の左上隅および右下隅の座標を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagRECT {  
    LONG left;  
    LONG top;  
    LONG right;  
    LONG bottom;  
} RECT;  
```  
  
## <a name="members"></a>メンバー  
 `left`  
 四角形の左上隅の X 座標を指定します。  
  
 `top`  
 四角形の左上隅の Y 座標を指定します。  
  
 `right`  
 四角形の右下隅の X 座標を指定します。  
  
 `bottom`  
 四角形の右下隅の Y 座標を指定します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** windef.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)
