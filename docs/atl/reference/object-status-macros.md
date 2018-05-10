---
title: オブジェクトの状態に関するマクロ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eddfc28c659d0c1eb54794d8fc76a9f3a4f9e73b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="object-status-macros"></a>オブジェクトの状態に関するマクロ
このマクロは、ActiveX コントロールに属しているフラグを設定します。  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|設定する、ATL の ActiveX コントロールで使用される、**入ります**フラグ。|  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlcom.h  

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS  
 ATL の ActiveX コントロールで使用すると、入りますフラグを設定できます。  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>パラメーター  
 *miscstatus*  
 該当するすべての入りますフラグです。  
  
### <a name="remarks"></a>コメント  
 このマクロを使用すると、ActiveX コントロールの入りますフラグを設定します。 参照してください[IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521)詳細についてはします。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
