---
title: ABCFLOAT 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- ABCFLOAT
dev_langs:
- C++
helpviewer_keywords:
- ABCFLOAT structure [MFC]
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5be39336f3da839dc9b1c7be6a64db54b59f99bd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="abcfloat-structure"></a>ABCFLOAT 構造体
`ABCFLOAT`構造には、フォントの文字の A、B、および C の幅が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct _ABCFLOAT { /* abcf */  
    FLOAT abcfA;  
    FLOAT abcfB;  
    FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *abcfA*  
 文字の A の間隔を指定します。 A の間隔は、文字のグリフを描画する前に、現在の位置に追加する距離です。  
  
 *abcfB*  
 文字の B の間隔を指定します。 B の間隔は、文字のグリフの描画の部分の幅です。  
  
 *abcfC*  
 文字の C 間隔を指定します。 C の間隔は、文字のグリフの右側に空白文字を提供する現在の位置に追加する距離です。  
  
## <a name="remarks"></a>コメント  
 A、B、および C の幅は、フォントのベース ラインに沿って測定されます。 文字の文字インクリメント (合計幅) は、A、B、および C のスペースの合計です。 A または C 領域のいずれかのスペーシングまたはオーバー ハングを示す負できます。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** wingdi.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

