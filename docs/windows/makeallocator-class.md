---
title: MakeAllocator クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 38724e6371f5c0ae508fc18e4bc75dc2287dbe19
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878061"
---
# <a name="makeallocator-class"></a>MakeAllocator クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
  
template<  
   typename T,  
   bool hasWeakReferenceSupport =   
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
 class MakeAllocator;  
  
template<typename T>  
class MakeAllocator<T, false>;  
  
template<typename T>  
class MakeAllocator<T, true>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 型の名前。  
  
 `hasWeakReferenceSupport`  
 `true` 弱い参照をサポートするオブジェクトのメモリを割り当てられません`false`弱参照でサポートされていないオブジェクトのメモリを割り当てられません。  
  
## <a name="remarks"></a>コメント  
 弱い参照のサポートの有無のアクティブ化可能なクラスのメモリを割り当てます。  
  
 ユーザー定義のメモリ割り当てのモデルを実装する MakeAllocator クラスをオーバーライドします。  
  
 MakeAllocator は通常、構築時にオブジェクトをスローした場合は、メモリ リークを防ぐために使用されます。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[MakeAllocator::MakeAllocator コンストラクター](../windows/makeallocator-makeallocator-constructor.md)|MakeAllocator クラスの新しいインスタンスを初期化します。|  
|[MakeAllocator::~MakeAllocator デストラクター](../windows/makeallocator-tilde-makeallocator-destructor.md)|MakeAllocator クラスの現在のインスタンスの初期化を解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[MakeAllocator::Allocate メソッド](../windows/makeallocator-allocate-method.md)|メモリが割り当てられ、現在 MakeAllocator オブジェクトに関連付けます。|  
|[MakeAllocator::Detach メソッド](../windows/makeallocator-detach-method.md)|によって割り当てられたメモリの関連付けを解除、 [Allocate](../windows/makeallocator-allocate-method.md) MakeAllocator、現在のメソッドです。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `MakeAllocator`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** implements.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)