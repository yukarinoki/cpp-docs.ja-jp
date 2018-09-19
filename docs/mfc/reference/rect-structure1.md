---
title: RECT Structure1 |Microsoft Docs
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
ms.openlocfilehash: 2e71459a1c22b9295c5c88ce29da9e494660fa26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046304"
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
`left`<br/>
四角形の左上隅の X 座標を指定します。  
  
`top`<br/>
四角形の左上隅の Y 座標を指定します。  
  
`right`<br/>
四角形の右下隅の X 座標を指定します。  
  
`bottom`<br/>
四角形の右下隅の Y 座標を指定します。  
  
## <a name="example"></a>例  
 [!code-cpp[NVC_MFC_Utilities#38](../../mfc/codesnippet/cpp/rect-structure1_1.cpp)]  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** windef.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRect クラス](../../atl-mfc-shared/reference/crect-class.md)
