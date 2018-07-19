---
title: オブジェクトの状態に関するマクロ |Microsoft Docs
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
ms.openlocfilehash: e3657e7076bf67a5a3870d7d127cc150f976ecde
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883659"
---
# <a name="object-status-macros"></a>オブジェクトの状態に関するマクロ
このマクロは、ActiveX コントロールに属しているフラグを設定します。  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|ATL の ActiveX コントロールにおける入りますフラグを設定するために使用します。|  

## <a name="requirements"></a>必要条件  
 **ヘッダー:** atlcom.h  

##  <a name="declare_olemisc_status"></a>  DECLARE_OLEMISC_STATUS  
 ATL の ActiveX コントロールにおける入りますフラグを設定するために使用します。  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>パラメーター  
 *miscstatus*  
 該当するすべて入りますフラグ。  
  
### <a name="remarks"></a>Remarks  
 このマクロは、ActiveX コントロールの入りますフラグの設定に使用されます。 参照してください[IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521)の詳細。  
  
### <a name="example"></a>例  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>関連項目  
 [[マクロ]](../../atl/reference/atl-macros.md)
