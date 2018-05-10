---
title: ClassFactory クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory
dev_langs:
- C++
helpviewer_keywords:
- ClassFactory class
ms.assetid: f13e6bce-722b-4f18-b7cf-3ffa6345c1db
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6294634652ffc6a53a577ccd75c348ed63c502e7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="classfactory-class"></a>ClassFactory クラス
IClassFactory インターフェイスの基本機能を実装します。  
  
## <a name="syntax"></a>構文  
  
```  
template <  
   typename I0 = Details::Nil,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil  
>  
class ClassFactory : public Details::RuntimeClass<  
   typename Details::InterfaceListHelper<IClassFactory,   
   I0,   
   I1,   
   I2,   
   Details::Nil>::TypeT,   
   RuntimeClassFlags<ClassicCom | InhibitWeakReference>,   
      false>;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `I0`  
 0 番目のインターフェイスです。  
  
 `I1`  
 最初のインターフェイスです。  
  
 `I2`  
 2 番目のインターフェイスです。  
  
## <a name="remarks"></a>コメント  
 利用`ClassFactory`工場出荷時のユーザー定義の実装を提供します。  
  
 次のプログラミング パターンが使用する方法を示します、 [Implements](../windows/implements-structure.md)構造体をクラス ファクトリで複数の 3 つのインターフェイスを指定します。  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ClassFactory::ClassFactory コンストラクター](../windows/classfactory-classfactory-constructor.md)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ClassFactory::AddRef メソッド](../windows/classfactory-addref-method.md)|ClassFactory、現在の参照カウントをインクリメントします。|  
|[ClassFactory::LockServer メソッド](../windows/classfactory-lockserver-method.md)|現在の ClassFactory オブジェクトによって追跡されているオブジェクトの基になる数ずつインクリメントまたはデクリメントします。|  
|[ClassFactory::QueryInterface メソッド](../windows/classfactory-queryinterface-method.md)|パラメーターで指定されたインターフェイスへのポインターを取得します。|  
|[ClassFactory::Release メソッド](../windows/classfactory-release-method.md)|現在の ClassFactory オブジェクト、参照カウントをデクリメントします。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ClassFactory`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)   
 [RuntimeClassType 列挙型](../windows/runtimeclasstype-enumeration.md)