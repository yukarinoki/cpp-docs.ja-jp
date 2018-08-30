---
title: RGNDATA 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- RGNDATA
dev_langs:
- C++
helpviewer_keywords:
- RGNDATA structure [MFC]
ms.assetid: 72257c00-f440-4dca-979e-9b6b5b2d5f2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c539feaac9cac5bca3a41868cc03379a63bf6bb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204360"
---
# <a name="rgndata-structure"></a>RGNDATA 構造体
`RGNDATA`構造には、ヘッダーとリージョンを構成する四角形の配列が含まれています。 これらの四角形、並べ替えられた上部から下、左から右は重複しません。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _RGNDATA { /* rgnd */  
    RGNDATAHEADER rdh;  
    char Buffer[1];  
} RGNDATA;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rdh*  
 指定します、 [RGNDATAHEADER](/windows/desktop/api/wingdi/ns-wingdi-_rgndataheader)構造体。 (この構造体の詳細については、Windows SDK を参照してください)。この構造体のメンバーでは、リージョン (かどうかは四角形または台形)、領域、四角形構造体を格納しているバッファーのサイズを構成する四角形の数の種類を指定しにします。  
  
 *Buffer*  
 含む、任意のサイズのバッファーを指定します、 [RECT](../../mfc/reference/rect-structure1.md)リージョンを構成します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CRgn::CreateFromData](../../mfc/reference/crgn-class.md#createfromdata)   
 [CRgn::GetRegionData](../../mfc/reference/crgn-class.md#getregiondata)

