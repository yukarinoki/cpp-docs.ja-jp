---
title: Classfactory::lockserver メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- LockServer method
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee858346fdb70e136edfbc562c2dfffb1f63e462
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652372"
---
# <a name="classfactorylockserver-method"></a>ClassFactory::LockServer メソッド
ずつインクリメントまたはデクリメントし、現在追跡されるオブジェクトの基になる数**ClassFactory**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
### <a name="parameters"></a>パラメーター  
 *群れ*  
 **true**追跡対象のオブジェクトの数をインクリメントします。 **false**追跡対象のオブジェクトの数をデクリメントします。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、E_FAIL します。  
  
## <a name="remarks"></a>Remarks  
 **ClassFactory**の基になるインスタンス内のオブジェクトの追跡、[モジュール](../windows/module-class.md)クラス。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ClassFactory クラス](../windows/classfactory-class.md)