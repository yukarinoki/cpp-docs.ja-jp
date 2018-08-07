---
title: Runtimeclass::getiids メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClass::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 87f51d39bf1ff8c7d4271797dcaa23278ac2e747
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608444"
---
# <a name="runtimeclassgetiids-method"></a>RuntimeClass::GetIids メソッド
インターフェイス Id を現在の実装を含むことのできる配列を取得します**RuntimeClass**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
### <a name="parameters"></a>パラメーター  
 *iidCount*  
 ときにこの操作が完了すると、配列内の要素の合計数*iid*します。  
  
 *iid*  
 この操作が完了時は、インターフェイス Id の配列へのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は s_ok を返します。それ以外の場合、E_OUTOFMEMORY します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [RuntimeClass クラス](../windows/runtimeclass-class.md)