---
title: ComPtrRef クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef
dev_langs:
- C++
helpviewer_keywords:
- ComPtrRef class
ms.assetid: d6bdfd20-e977-45b4-9ac1-1b8efbdb77de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c45aa289b4b41ddfaf141dcaf790734284af7c8
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643551"
---
# <a name="comptrref-class"></a>ComPtrRef クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```cpp  
template <  
   typename T  
>  
class ComPtrRef : public ComPtrRefBase<T>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *T*  
 A [ComPtr\<T >](../windows/comptr-class.md)ことによって表されるだけでなく、インターフェイスから派生した型または型、`ComPtr`します。  
  
## <a name="remarks"></a>Remarks  
 型のオブジェクトへの参照を表す`ComPtr<T>`します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRef::ComPtrRef コンストラクター](../windows/comptrref-comptrref-constructor.md)|新しいインスタンスを初期化、 **ComPtrRef**クラス、指定されたポインター **ComPtrRef**オブジェクト。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRef::GetAddressOf メソッド](../windows/comptrref-getaddressof-method.md)|現在によって表されるインターフェイスへのポインターのアドレスを取得**ComPtrRef**オブジェクト。|  
|[ComPtrRef::ReleaseAndGetAddressOf メソッド](../windows/comptrref-releaseandgetaddressof-method.md)|現在の削除**ComPtrRef**オブジェクト、ポインター-に-、- へポインターを返します、インターフェイスによって表される、 **ComPtrRef**オブジェクト。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[ComPtrRef::operator InterfaceType** 演算子](../windows/comptrref-operator-interfacetype-star-star-operator.md)|現在の削除**ComPtrRef**オブジェクト、ポインター-に-、- へポインターを返します、インターフェイスによって表される、 **ComPtrRef**オブジェクト。|  
|[ComPtrRef::operator T* 演算子](../windows/comptrref-operator-t-star-operator.md)|値を返します、 [ptr _](../windows/comptrrefbase-ptr-data-member.md) ComPtrRef オブジェクトを現在のデータ メンバー。|  
|[ComPtrRef::operator void** 演算子](../windows/comptrref-operator-void-star-star-operator.md)|現在の削除**ComPtrRef**オブジェクト、によって表されるインターフェイスへのポインターをキャスト、 **ComPtrRef**オブジェクト、ポインターでへのポインター-として**void**、し、キャストのポインターを返します。|  
|[ComPtrRef::operator* 演算子](../windows/comptrref-operator-star-operator.md)|現在によって表されるインターフェイスへのポインターを取得します。 **ComPtrRef**オブジェクト。|  
|[ComPtrRef::operator== 演算子](../windows/comptrref-operator-equality-operator.md)|示す 2 つかどうか**ComPtrRef**オブジェクトが等しい。|  
|[ComPtrRef::operator!= 演算子](../windows/comptrref-operator-inequality-operator.md)|示す 2 つかどうか**ComPtrRef**オブジェクトが等しくないです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `ComPtrRefBase`  
  
 `ComPtrRef`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)