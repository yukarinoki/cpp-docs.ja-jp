---
title: デバイス コンテキストに関するグローバル関数 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8944ecdb4f9996800264986a7a687df6020b0591
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209934"
---
# <a name="device-context-global-functions"></a>デバイス コンテキストに関するグローバル関数
この関数は、特定のデバイスのデバイス コンテキストを作成します。  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|デバイス コンテキストを作成します。|  
  
##  <a name="atlcreatetargetdc"></a>  AtlCreateTargetDC  
 指定されたデバイスのデバイス コンテキストを作成、 [DVTARGETDEVICE](/windows/desktop/api/objidl/ns-objidl-tagdvtargetdevice)構造体。  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>パラメーター  
 *hdc*  
 [in]デバイス コンテキスト、または NULL の既存のハンドル。  
  
 *ptd*  
 [in]ポインター、`DVTARGETDEVICE`対象デバイスに関する情報を含む構造体。  
  
### <a name="return-value"></a>戻り値  
 指定されたデバイスのデバイス コンテキストへのハンドルを返します、`DVTARGETDEVICE`します。 デバイスが指定されていない場合は、既定のディスプレイ デバイスにハンドルを返します。  
  
### <a name="remarks"></a>Remarks  
 構造体が NULL の場合と*hdc*が NULL で、既定のディスプレイ デバイスのデバイス コンテキストを作成します。  
  
 場合*hdc*が NULL でないと*ptd*が null の場合、既存の関数を返します*hdc*します。  

## <a name="requirements"></a>要件  
 **ヘッダー:** atlwin.h  
   
## <a name="see-also"></a>関連項目  
 [関数](../../atl/reference/atl-functions.md)
