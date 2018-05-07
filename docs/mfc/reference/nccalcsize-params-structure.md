---
title: NCCALCSIZE_PARAMS 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- NCCALCSIZE_PARAMS
dev_langs:
- C++
helpviewer_keywords:
- NCCALCSIZE_PARAMS structure [MFC]
ms.assetid: 3424cd9f-806a-4089-82fb-414187589edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07db612cb6dbde0dd762cf709ac6040bbd836c4b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
---
# <a name="nccalcsizeparams-structure"></a>NCCALCSIZE_PARAMS 構造体
`NCCALCSIZE_PARAMS`構造体には、アプリケーションが処理中に使用できる情報が含まれています、`WM_NCCALCSIZE`サイズ、位置、およびウィンドウのクライアント領域の有効な内容を計算するメッセージ。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagNCCALCSIZE_PARAMS {  
    RECT rgrc[3];  
    PWINDOWPOS lppos;  
} NCCALCSIZE_PARAMS;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *rgrc*  
 四角形の配列を指定します。 最初には、移動またはサイズが変更されたウィンドウの新しい座標が含まれています。 2 つ目には、これが移動またはサイズを変更する前に、ウィンドウの座標が含まれています。 3 番目には、これが移動またはサイズを変更する前に、ウィンドウのクライアント領域の座標が含まれています。 子ウィンドウをウィンドウには、座標は、親ウィンドウのクライアント領域と相対的はします。 ウィンドウがトップレベル ウィンドウの場合は、座標は、画面に対して相対的です。  
  
 *lppos*  
 指す、 [WINDOWPOS](../../mfc/reference/windowpos-structure1.md)ウィンドウを移動またはサイズ変更の原因となった操作で指定されたサイズと位置の値を格納する構造体。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnNcCalcSize](../../mfc/reference/cwnd-class.md#onnccalcsize)

