---
title: ClassFactory クラス |Microsoft Docs
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
ms.openlocfilehash: 97c07b5cf97578c49da9d4a72b5a232b559ec0ab
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463867"
---
# <a name="classfactory-class"></a>ClassFactory クラス
`IClassFactory` インターフェイスの基本機能を実装します。  
  
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
 *I0*  
 0 番目のインターフェイスです。  
  
 *I1*  
 最初のインターフェイス。  
  
 *I2*  
 2 番目のインターフェイス。  
  
## <a name="remarks"></a>Remarks  
 利用`ClassFactory`工場出荷時のユーザー定義の実装を提供します。  
  
 次のプログラミングのパターンが使用する方法を示します、[実装](../windows/implements-structure.md)構造体をクラス ファクトリを複数の 3 つのインターフェイスを指定します。  
  
 `struct MyFactory : ClassFactory<Implements<I1, I2, I3>, I4, I5>`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[ClassFactory::ClassFactory コンストラクター](../windows/classfactory-classfactory-constructor.md)||  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[ClassFactory::AddRef メソッド](../windows/classfactory-addref-method.md)|ClassFactory の現在のオブジェクトの参照カウントをインクリメントします。|  
|[ClassFactory::LockServer メソッド](../windows/classfactory-lockserver-method.md)|現在の ClassFactory オブジェクトによって追跡されるオブジェクトの基になる数ずつインクリメントまたはデクリメントします。|  
|[ClassFactory::QueryInterface メソッド](../windows/classfactory-queryinterface-method.md)|パラメーターで指定されたインターフェイスへのポインターを取得します。|  
|[ClassFactory::Release メソッド](../windows/classfactory-release-method.md)|現在の ClassFactory オブジェクトの参照カウントをデクリメントします。|  
  
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