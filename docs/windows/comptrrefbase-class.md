---
title: ComPtrRefBase クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRefBase class
ms.assetid: 6d344c1a-cc13-4a3f-8a0d-f167ccb9348f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0342500fc41c650967e17919ebdc9605d4261cb5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464244"
---
# <a name="comptrrefbase-class"></a>ComPtrRefBase クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename T  
>  
class ComPtrRefBase;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 A [ComPtr\<T >](../windows/comptr-class.md)ことによって表されるだけでなく、インターフェイスから派生した型または型、 **ComPtr**します。  
  
## <a name="remarks"></a>Remarks  
 基本クラスを表します、 [ComPtrRef](../windows/comptrref-class.md)クラス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`InterfaceType`|テンプレート パラメーターの型のシノニム*T*します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRefBase::operator IInspectable** 演算子](../windows/comptrrefbase-operator-iinspectable-star-star-operator.md)|現在ではキャスト[ptr _](../windows/comptrrefbase-ptr-data-member.md)データ メンバーをポインターを-、-ポインター - IInspectable インターフェイス。|  
|[ComPtrRefBase::operator IUnknown** 演算子](../windows/comptrrefbase-operator-iunknown-star-star-operator.md)|現在ではキャスト[ptr _](../windows/comptrrefbase-ptr-data-member.md)データ メンバーをポインターを-、-ポインターの IUnknown インターフェイス。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|name|説明|  
|----------|-----------------|  
|[ComPtrRefBase::ptr_ データ メンバー](../windows/comptrrefbase-ptr-data-member.md)|現在のテンプレート パラメーターで指定された型へのポインター。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ComPtrRefBase`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)