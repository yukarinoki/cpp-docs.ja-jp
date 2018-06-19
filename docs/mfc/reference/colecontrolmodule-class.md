---
title: COleControlModule クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- OleControlModule
dev_langs:
- C++
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 597639145385f4aabcba0e83fef855f7a0779f9b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369740"
---
# <a name="colecontrolmodule-class"></a>COleControlModule クラス
OLE コントロール モジュール オブジェクトを派生するための基底クラスです。  
  
## <a name="syntax"></a>構文  
  
```  
class COleControlModule : public CWinApp  
```  
  
## <a name="remarks"></a>コメント  
 このクラスは、コントロール モジュールを初期化するためのメンバー関数を提供します。 Microsoft Foundation classes を使用する各 OLE コントロール モジュールがから派生した 1 つのオブジェクトを含めることができますのみ`COleControlModule`です。 その他の C++ のグローバル オブジェクトが構築されるときに、このオブジェクトが構築されます。 宣言、派生`COleControlModule`グローバル レベルのオブジェクト。  
  
 使用する方法について、`COleControlModule`クラスを参照してください、 [CWinApp](../../mfc/reference/cwinapp-class.md)クラス」および「 [ActiveX コントロール](../../mfc/mfc-activex-controls.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxctl.h  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル TESTHELP](../../visual-cpp-samples.md)   
 [階層図](../../mfc/hierarchy-chart.md)



